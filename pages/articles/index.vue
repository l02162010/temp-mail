<template>
  <div class="container sm:mt-10 px-3 sm:px-0">
    <div class="font-bold italic text-2xl">
      Articles
    </div>
    <div class="flex flex-col sm:flex-row">
      <div class="w-full sm:w-2/3">
        <div v-for="n in 2" :key="n" class="article py-5">
          <img class="object-cover" src="https://images.unsplash.com/photo-1596307509444-8448c605d6da?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80" alt="" srcset="article background images">
          <div class="font-bold text-lg pt-3 cursor-pointer hover:text-gray-600" @click="goto('123')">
            KTM Marchetti Signs with Larranaga
            and Zanotti for Next Season
          </div>
          <div class="text-sm pt-3">
            Armin Vans - August 7, 2019
          </div>
          <div class=" text-xs text-gray-800 pt-3">
            With more states across America ordering millions to stay home, and Britain joining the rest of Europe in shuttering
            nonessential businesses and placing its population under what one newspaper called "house arrest", voices of disquiet over the economic cost of such measures grew louder, even as public health experts warned that relaxing restrictions could significantly increase the death toll.
          </div>
        </div>
        <div class="pagination flex justify-center mb-8">
          <div class="next py-3 px-5 my-3 hover:bg-gray-400 flex items-center cursor-pointer">
            <img src="~/assets/images/icon/next.png" class="page-icon pre-page" alt="go to next page icon">
          </div>
          <div v-for="n in 5" :key="n" class="pageNumber py-3 px-5 my-3  hover:bg-gray-400 cursor-pointer">
            {{ n }}
          </div>
          <div class="next py-3 px-5 my-3 hover:bg-gray-400 flex items-center cursor-pointer">
            <img src="~/assets/images/icon/next.png" class="page-icon" alt="go to next page icon">
          </div>
        </div>
      </div>
      <div class="w-full sm:w-1/3">
        <div v-for="n in 5" :key="n" class="ad flex justify-center items-center my-3 sm:ml-5">
          AD
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    goto (id) {
      this.$router.push({ name: 'articles-id', params: { id } })
    }
  }
}
</script>

<style lang="postcss" scoped>
 .container {
    @apply min-h-screen flex flex-col justify-start mx-auto;
  }

.ad {
  width: 100%;
  min-height: 150px;
  background-color: #d3d3d3;
  padding: 10px;
}
.page-icon {
  width: 14px;
}
.pre-page {
  transform: scaleX(-1);
}
</style>
