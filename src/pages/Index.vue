<template>
  <q-page>
    <div class="row flex flex-center">
      <div class="col-8 ">
        <carousel>
          <slide
            class="card-carousel--card"
            v-for="(n, index) in items"
            :key="index"
          >
            <q-card class="my-card q-ma-sm">
              <q-responsive :ratio="1">
                <img src="https://placehold.it/200x200" />
              </q-responsive>

              <q-card-section>
                <p v-html="n.name"  class="text-h6"/>

                <q-chip
                  v-for="(n2, index2) in n.tag"
                  :key="index2"
                  v-html="n2"
                />
              </q-card-section>
            </q-card>
          </slide>
        </carousel>
      </div>
    </div>
  </q-page>
</template>

<script>
import { Carousel, Slide } from 'vue-carousel';
export default {
  components: {
    Carousel,
    Slide
  },
  data() {
    return {
      currentOffset: 0,
      windowSize: 3,
      paginationFactor: 220,
      items: [
        {
          name: 'Kin Khao',
          tag: ['Thai']
        },
        {
          name: 'Jū-Ni',
          tag: ['Sushi', 'Japanese', '$']
        },
        {
          name: 'Delfina',
          tag: ['Pizza', 'Casual']
        },
        {
          name: 'San Tung',
          tag: ['Chinese', '$']
        },
        {
          name: 'Anchor Oyster Bar',
          tag: ['Seafood', 'Cioppino']
        },
        {
          name: 'Locanda',
          tag: ['Italian']
        },
        {
          name: 'Garden Creamery',
          tag: ['Ice cream']
        }
      ]
    };
  }
};
</script>

