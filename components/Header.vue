<template>
  <div class="flex justify-between items-center mx-auto py-5 max-w-screen-xl">
    <MobileHamburger ref="mobileHamburger" class="flex sm:hidden" @isOpen="handleIsMobileNavOpen" />
    <div class="text-xl font-bold flex justify-center">
      TEMP MAIL
    </div>
    <div v-show="isMobileNavOpen" class="mobileNav absolute sm:hidden">
      <div
        v-for="p in pageList"
        :key="p.value"
        class="text-gray-600 pr-3 cursor-pointer hover:text-gray-800"
        @click="goto(p.value)"
      >
        {{ p.text }}
      </div>
    </div>
    <div class="desktopNav hidden sm:flex justify-center w-1/3">
      <div
        v-for="p in pageList"
        :key="p.value"
        class="text-gray-600 pr-3 cursor-pointer hover:text-gray-800"
        @click="goto(p.value)"
      >
        {{ p.text }}
      </div>
    </div>
    <DropDown class="flex justify-center" :value="currentLang" :list="langList" @selected="handleLang" />
  </div>
</template>
<script>
import DropDown from '@/components/DropDown'
export default {
  components: {
    DropDown
  },
  data () {
    return {
      currentLang: 'EN',
      pageList: [
        { text: 'HOME', value: 'index' },
        { text: 'ARTICLE', value: 'articles' },
        { text: 'PRIVACY', value: 'privacy' }
      ],
      langList: [
        { text: 'EN', value: 'EN' },
        { text: '繁中', value: 'zh_tw' },
        { text: '简中', value: 'zh_cn' }
      ],
      isMobileNavOpen: false
    }
  },
  methods: {
    handleLang (currentLang) {
      this.currentLang = currentLang
    },
    handleIsMobileNavOpen (val) {
      this.isMobileNavOpen = val
    },
    goto (pathName) {
      this.$nextTick(() => {
        this.$refs.mobileHamburger.close()
      })
      this.$router.push({ name: pathName })
    }
  }
}
</script>
<style>
.mobileNav {
  top: 70px;
  right: 0px;
  width: 100%;
  padding: 15px;
  background: #ffffff;
  z-index: 2;
}
</style>
