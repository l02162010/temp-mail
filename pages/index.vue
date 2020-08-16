<template>
  <div>
    <div class="flex flex-col my-5 sm:mb-10 sm:mt-0 justify-center items-center w-full bg-sun min-h-250 ">
      <div class="text-2xl font-semibold pt-5">
        Your Temporary Email Address
      </div>
      <MailDropDown class="pt-5" :value="currentMail" :list="mailList" @selected="handleSelectedMail" />
      <div class="flex flex-wrap justify-center sm:justify-around pt-3">
        <FuncBtn class="mt-3 w-2/5 sm:w-auto">
          <img class="mr-2" src="~@/assets/images/icon/file.png" alt="" srcset="">
          Copy
        </FuncBtn>
        <FuncBtn class="mt-3 w-2/5 sm:w-auto">
          <img class="mr-1" src="~@/assets/images/icon/refresh.png" alt="" srcset="">
          Refresh
        </FuncBtn>
        <FuncBtn class="mt-3 w-2/5 sm:w-auto">
          <img class="mr-1" src="~@/assets/images/icon/add.png" alt="" srcset="">
          New
        </FuncBtn>
        <FuncBtn class="mt-3 w-2/5 sm:w-auto">
          <img class="mr-1" src="~@/assets/images/icon/qrcode.png" alt="" srcset="">
          QR Code
        </FuncBtn>
      </div>
      <div class="px-3 text-sm font-semibold py-5 text-center sm:w-2/5">
        Tempail provides you with temp mail addresses which expire after 1 Hours.
        You can sign up to websites, social media (facebook,twitter)
        and read the  incoming emails.
      </div>
    </div>
    <div class="container">
      <div class="flex flex-col mx-3 my-10 sm:mx-0 sm:flex-row border-2 border-dashed-image">
        <div
          class="flex flex-col items-center sm:w-1/3 border-b-2 sm:border-b-0 sm:border-r-2 border-dashed-image p-5 min-h-350 max-h-350 overflow-scroll"
          :class="{'justify-center': receiveMails && receiveMails.length === 0}"
        >
          <div v-if="receiveMails && receiveMails.length === 0">
            Your emails will display here
          </div>
          <div v-for="n in 500" v-else :key="n">
            {{ n }}
          </div>
        </div>
        <div class="flex justify-center items-center sm:w-2/3 p-5 min-h-350 max-h-350">
          <img src="~/assets/images/empty-mail.png" alt="" srcset="">
        </div>
      </div>
      <div class="flex flex-col my-10 sm:mb-20 justify-center items-center w-full min-h-250">
        <div class="title text-3xl pb-5 font-bold">
          Popular Articles
        </div>
        <div class="flex flex-col sm:flex-row justify-around w-full">
          <div v-for="n in 3" :key="n" class="p-3 sm:p-0" :class="{'sm:pr-3': n !== 3}">
            <div class="articleImage max-w-full">
              <img class="object-cover" src="https://images.unsplash.com/photo-1596307509444-8448c605d6da?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80" alt="" srcset="">
            </div>
            <div class="articleTitle text-xl pt-3 cursor-pointer hover:text-gray-600">
              From Jerry Falwell Jr. to Dr. Drew: 5 Coronavirus doubters
            </div>
            <div class="articleCreatetime text-xs pt-3">
              March 19, 2020
            </div>
            <div class="articleDescription text-sm pt-3">
              With more states across America ordering millions
              to stayhome, and Britain...
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MailDropDown from '@/components/MailDropDown'
export default {
  components: {
    MailDropDown
  },
  data () {
    return {
      receiveMails: [],
      currentReceiveMail: null,
      mailList: [{
        text: 'awdqwasdasd@gmail.com',
        value: '123@gmail.com'
      },
      {
        text: '456@gmail.com',
        value: '456@gmail.com'
      },
      {
        text: '789@gmail.com',
        value: '789@gmail.com'
      },
      {
        text: '234@gmail.com',
        value: '234@gmail.com'
      }, {
        text: '345@gmail.com',
        value: '345@gmail.com'
      }],
      currentMail: '123@gmail.com'
    }
  },
  methods: {
    handleSelectedMail (mail) {
      this.currentMail = mail
    }
  }
}
</script>

<style lang="postcss" scoped>
/* Sample `apply` at-rules with Tailwind CSS

  */
  .container {
    @apply min-h-screen flex flex-col justify-around mx-auto;
  }
</style>
