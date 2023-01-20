<template>

  <q-page class="my-padding-x q-ml-sm q-pa-sm ">

    <div class="row q-col-gutter-md">


      <div class="col-md-9 col-xs-12 ">

        <q-card class="my-card" flat>
          <img src="image-web-3-desktop.jpg" height="230">

          <q-card-section class="row justify-around">
            <div class="text-h3 col-sm-5 col-xs-12 text-weight-bold">The Bright Future of Web 3.0</div>

            <div class="q-gutter-sm col-md-5 col-xs-12">
              <div class="text-caption">We dive into the next evolution of the web that claims to put the power of the platforms back into the hands of the people. But is it really fulfilling its promise?</div>
              <q-btn
                class=" my-btn-color text-white q-mt-lg"
                label="Read more"
                unelevated
                flat
                square
              />
            </div>
          </q-card-section>

        </q-card>

      </div>

      <div class="col-md-3 col-xs-12">

        <q-card
          class="my-card text-white q-pa-none q-ma-none"
          style="background: #141129"
          flat
        >
          <q-card-section class="q-mb-lg q-pb-none">
            <div class="text-h4 text-weight-bold text-amber-4">New</div>
          </q-card-section>

          <q-card-section class="q-pa-none q-ma-none">

            <q-card-section   v-for="(mytext, i) in mytexts" :key="i">

              <div class="text-subtitle2 q-my-none q-px-none text-white font-weight-bold titleCard">{{ mytext.title }}</div>
              <div class="text-caption q-my-none q-px-none text-grey-5">{{ mytext.content }}</div>

              <q-separator
                size="1px"
                color="grey-5"
                class="q-mt-md q-pb-none q-mb-none"
                v-if="i< mytexts.length - 1"
              />

            </q-card-section>



          </q-card-section>



        </q-card>

      </div>

    </div>

    <div class="row">

      <q-card
        class="my-card-2 q-mt-md col col-md-4 col-xs-12"
        flat
        v-for="(item, i) in myTextCard2"
        :key="i"
      >

        <q-card-section horizontal>

          <q-card-section class="col-4 flex flex-center q-mt-none">
            <q-img
              :src="item.image"
              width="80px"
            />
          </q-card-section>

          <q-card-section class="q-pt-md">
            <div class="text-h5 text-grey-4 text-weight-bold q-ma-none q-pa-none">{{ item.title }}</div>
            <div class=" title-card-2 text-subtitle1 my-card-text-color text-weight-bold">{{ item.subtitle }}</div>
            <div class="text-caption text-grey">
              {{ item.content }}
            </div>
          </q-card-section>


        </q-card-section>

      </q-card>

    </div>

  </q-page>
</template>

<script setup>

  import { ref, onMounted } from 'vue'

  const mytexts = ref([
    {
      title: 'Hydrogen VS Electrics Cars',
      content: 'Will hydrogen-fueled cars catch up to EVs?'
    },
    {
      title: 'The Downsides of AI Artistry',
      content: 'What are the possible adverse effetcs of on-demand AI image generation?'
    },
    {
      title: 'Is VC Funding Drying Up?',
      content: 'Private funding by VC firms is down 50% YOY. We take a look at what that means.'
    },
  ])

  const myTextCard2 = ref([
    {
      title: '01',
      subtitle: 'Reviving Retro PCs',
      content: 'What happens chen old PCs are given modern upgrades?',
      image: 'image-retro-pcs.jpg'
    },
    {
      title: '02',
      subtitle: 'Top 10 Laptops of 2022',
      content: 'Our best picks for various needs and budgets.',
      image: 'image-top-laptops.jpg'
    },
    {
      title: '03',
      subtitle: 'The Growth of Gaming',
      content: 'How the pandemic has sparked fresh opportunities.',
      image: 'image-gaming-growth.jpg'
    },
  ])



</script>

<style lang="scss">

  .titleCard{
    cursor: pointer;
    margin-top: -15px;

    &:hover{
      color: $amber-4!important;
    }
  }

  .title-card-2{
    cursor: pointer;
    &:hover{
      color: rgb(203, 78, 78);
    }
  }

  .my-btn-color {
    background-color: #141129;
  }

  .my-card{
    max-width:100%;
    border-radius: none!important;
  }

  .my-card-2{
    width: 35%;
  }

  .my-card-text-color{
    color: #141129;

    &:hover{
      color: rgb(203, 78, 78)!important;
    }
  }

  .q-card{
    border-radius: 0!important;
  }

  .q-btn:hover {
    background-color: rgb(203, 78, 78)!important;
  }
</style>
