<template>
  <div class="container">
    <div class="flex flex-col sm:flex-row sm:mt-10">
      <div class="w-full sm:w-1/2 p-3 sm:pl-0 sm:pr-10">
        <div class="font-bold text-2xl">
          Coronavirus spreads
          to sub-Saharan Africa
        </div>
        <div class="flex items-center pt-3">
          <img src="~/assets/images/icon/calendar.png" class="h-4 w-4 mr-2" alt="" srcset="">
          <span>March 19, 2020</span>
        </div>
        <div class="flex items-center pt-2">
          <img src="~/assets/images/icon/user.png" class="h-4 w-4 mr-2" alt="" srcset="">
          <span>Janna Smith</span>
        </div>
        <div class="flex items-center pt-2">
          <img src="~/assets/images/icon/view.png" class="h-4 w-4 mr-2" alt="" srcset="">
          <span>403 views</span>
        </div>
        <div class="ad mt-2">
          ad
        </div>
      </div>
      <img class="order-first sm:order-none w-full sm:w-1/2 object-cover max-h-350" src="https://images.unsplash.com/photo-1596307509444-8448c605d6da?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80" alt="" srcset="">
    </div>
    <div class="flex flex-col sm:flex-row mt-10 mb-8">
      <div class="w-full sm:w-2/3 text-sm p-3 sm:p-5 sm:pl-0">
        <p>
          With more states across America ordering millions to stay home, and Britain joining the rest of Europe in shuttering nonessential businesses and placing its population under what one newspaper called “house arrest”, voices of disquiet over the economic cost of such measures grew louder, even as public health experts warned that relaxing restrictions could significantly increase the death toll.

          Only one week after the White House released guidelines for all Americans to keep their distance, President Trump said it could soon be time to consider a more targeted approach.

          Life is fragile and economies are fragile,” the president said on Monday. “America will again and soon be open for business.
        </p>
        <p>
          Millions have already lost their jobs and the foundations of the global economy have been shaken. Mortgage markets showed signs of crumbling, companies struggled to sell debt and stresses plagued the entire financial system.

          The Federal Reserve promised to buy as much government-backed debt as needed to bolster the markets on Monday, but stocks on Wall Street still fell.
        </p>

        <p>
          There were hopeful signs on Tuesday, however, as Wall Street made early gains after Asian and European markets rebounded smartly. Lawmakers in Washington expressed optimism that they would reach a deal on a nearly $2 trillion stimulus bill. Public health officials continued to warn of impending disaster in the absence of stronger restrictions on movement, saying the uncontrolled spread of the virus could overwhelm health care systems around the world.

          In New York, where 157 people have died and 2,600 remain hospitalized, officials raced to prepare for a coming tsunami of patients. Dr. Deborah L. Birx, the White House coronavirus response coordinator, said the “attack rate” — the percentage of the population infected with the virus — was nearly one in 1,000 in the New York area, five times higher than in other parts of the country.

          To all of my friends and colleagues in New York, this is the group that needs to absolutely social distance and self-isolate at this time
        </p>

        <p>
          Across the Atlantic, even as the crisis grew in Spain and France and Britain prepared for worse days to come, health officials could point to the first glimpses of hope. Two weeks after Italy was completely locked down, its number of new cases and deaths declined for two days in a row. The number of patients in the hospitals in Lombardy, the region that is by far the hardest hit in Italy, fell as well, to 9,266 from 9,439.

          We can say that today is the first positive day, said Giulio Gallera, Lombardy’s leading health official. “It’s not the moment to sing victory, but we finally see light at the end of the tunnel.

          The Spanish army has found elderly people abandoned in several nursing homes, raising alarm for those most vulnerable and in need of care with much of life in the country shut down. The government will be “forceful” in its response to those who abandon older people, Margarita Robles, Spain’s defense minister, said Monday in an interview with Telecinco, a Spanish television channel. Officials did not say how many had died or whether residents had succumbed to coronavirus-related illness or a lack of care.

          Ms. Robles said that emergency military units dispatched to disinfect nursing homes had found there some residents “absolutely abandoned, if not dead in their beds.”
        </p>

        <p>
          The defense ministry said that dead bodies had been found in multiple nursing homes that had discharged large number of employees in the wake of the outbreaks, but did not provide further details, El País, a daily broadsheet, reported.
        </p>
      </div>
      <div class="w-full sm:w-1/3 p-3 sm:pr-0 sm:py-5">
        <div class="shareBox flex justify-between">
          <span class="italic font-semibold">share</span>
          <div class="flex items-center">
            <img src="~/assets/images/icon/fb.png" class="h-4 w-4 object-contain mr-5 cursor-pointer" alt="" srcset="">
            <img src="~/assets/images/icon/twitter.png" class="h-4 w-4 object-contain mr-5 cursor-pointer" alt="" srcset="">
            <img src="~/assets/images/icon/reddit.png" class="h-4 w-4 object-contain mr-5 cursor-pointer" alt="" srcset="">
          </div>
        </div>
        <div class="border-b-2 my-8" />
        <div class="ad">
          ad
        </div>
        <div class="border-b-2 my-8" />
        <div class="LatestUpdatesBox">
          <div class="italic text-lg w-fit pb-1 mb-2 border-b-2 border-sun">
            Latest Updates
          </div>
          <div v-for="n in 3" :key="n" class="article flex items-center py-3">
            <img class="h-20 mr-3 object-cover" src="https://images.unsplash.com/photo-1596307509444-8448c605d6da?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80" alt="" srcset="">
            <div>
              <div class="italic cursor-pointer hover:text-gray-600">
                Coronavirus spreads to
                sub-Saharan Africa
              </div>
              <div class="text-xs pt-2">
                March 19, 2020
              </div>
            </div>
          </div>
        </div>
        <div class="border-b-2 my-8" />
        <div class="ad">
          ad
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="postcss" scoped>

p {
  padding: 10px 0;
}

.container {
  @apply min-h-screen flex flex-col mx-auto;
}

.ad {
  width: 100%;
  min-height: 150px;
  background-color: #d3d3d3;
  padding: 10px;
}

.w-fit {
  width: fit-content;
}

.max-h-350 {
  max-height: 350px;
}

</style>
