<template>
  <div class="relative drop-down">
    <button class="relative z-10 block h-8 w-8 rounded-full overflow-hidden border-2 border-gray-600 focus:outline-none" @click="isOpen = !isOpen">
      {{ convertToText(value) }}
    </button>
    <button v-if="isOpen" tabindex="-1" class="fixed inset-0 h-full w-full opacity-100 cursor-default focus:outline-none" @click="isOpen = false" />
    <div v-if="isOpen" class="absolute text-center mt-2 py-2 w-auto bg-white rounded-lg shadow-xl option">
      <div
        v-for="item in list"
        :key="item.value"
        class="block whitespace-no-wrap cursor-pointer px-4 py-2 text-gray-800 hover:bg-indigo-500 hover:text-white"
        @click="selected(item.value)"
      >
        {{ item.text }}
      </div>
    </div>
  </div>
</template>

<script>
// list type
// [
//   { text: '', value }
// ]
export default {
  props: {
    value: {
      type: [String, Number],
      required: true
    },
    list: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      isOpen: false
    }
  },
  beforeMount () {
    const handleEscape = (e) => {
      if (e.key === 'Esc' || e.key === 'Escape') {
        this.isOpen = false
      }
    }

    document.addEventListener('keydown', handleEscape)

    this.$once('hook:beforeDestroy', () => {
      document.removeEventListener('keydown', handleEscape)
    })
  },
  methods: {
    convertToText (value) {
      let displayText = '請選擇'
      if (this.list && this.list.length > 0) {
        displayText = this.list.find((item) => {
          return item.value === this.value
        }).text
      }
      return displayText
    },
    selected (value) {
      this.$emit('selected', value)
      this.isOpen = false
    }
  }
}
</script>
<style scoped>
.drop-down .option {
  top: 16px;
}
</style>
