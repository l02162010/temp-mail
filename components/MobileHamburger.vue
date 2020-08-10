<template>
  <div>
    <button
      class="hamburger flex justify-center items-center focus:outline-none"
      :class="{'open': isOpen}"
      @click="isOpen = !isOpen"
    >
      <span class="hamburger__top-bun" />
      <span class="hamburger__bottom-bun" />
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false
    }
  },
  watch: {
    isOpen (val) {
      return this.$emit('isOpen', val)
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
    close () {
      this.isOpen = false
    }
  }
}
</script>

<style>
.hamburger {
  cursor: pointer;
  width: 48px;
  height: 48px;
  transition: all 0.25s;
}

.hamburger__top-bun,
.hamburger__bottom-bun {
  content: '';
  position: absolute;
  width: 24px;
  height: 2px;
  background: #000;
  transform: rotate(0);
  transition: all 0.5s;
}

.hamburger:hover [class*="-bun"] {
  background: #333;
}

.hamburger__top-bun {
  transform: translateY(-5px);
}

.hamburger__bottom-bun {
  transform: translateY(3px);
}

.open {
  transform: rotate(90deg);
  transform: translateY(-1px);
}

.open .hamburger__top-bun {
  transform:
    rotate(45deg)
    translateY(0px);
}

.open .hamburger__bottom-bun {
  transform:
    rotate(-45deg)
    translateY(0px);
}
</style>
