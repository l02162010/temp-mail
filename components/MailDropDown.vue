<template>
  <div class="relative drop-down">
    <button class="flex justify-center items-center w-full bg-black text-white z-10 block w-8 py-1 px-5 focus:outline-none rounded-full" @click="isOpen = !isOpen">
      <span class="text-sm pr-3 font-bold"> {{ convertToText(value) }}</span>
      <img class="w-4 h-4 mt-1 mr-3 text-white" src="~@/assets/images/icon/down-arrow.svg" alt="" srcset="">
      <span class="rounded-full border-2 w-8">10</span>
    </button>
    <button v-if="isOpen" tabindex="-1" class="fixed inset-0 h-full w-full opacity-100 cursor-default focus:outline-none" @click="isOpen = false" />
    <div v-if="isOpen" class="absolute w-full text-center mt-2 py-2 w-auto bg-white shadow-xl option">
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
//   { text: '', value: '' }
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
.drop-down{
  min-width: 250px;
}
.drop-down .option {
  top: 49px;
}
</style>
