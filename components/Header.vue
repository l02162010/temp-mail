<template>
  <div
    class="flex justify-around sm:justify-between items-center mx-auto py-5
            sm:max-w-screen-sm md:max-w-screen-md lg:max-w-screen-lg xl:max-w-screen-xl"
    style="height:90px"
  >
    <MobileHamburger ref="mobileHamburger" class="flex w-1/3 sm:hidden" @isOpen="handleIsMobileNavOpen" />
    <div class="text-xl font-bold flex justify-center sm:justify-start w-1/3">
      TEMP MAIL
    </div>
    <div v-if="isMobileNavOpen" class="mobileNav absolute sm:hidden">
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
        class="text-gray-600 px-4 cursor-pointer hover:text-gray-800"
        @click="goto(p.value)"
      >
        {{ p.text }}
      </div>
    </div>
    <DropDown class="flex justify-end w-1/3 pr-3 sm:pr-0" :value="currentLang" :list="langList" @selected="handleLang" />
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
