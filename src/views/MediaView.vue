<template>
  <div>
    <div>
      <video v-if="trailer" :src="trailerUrl"></video>
      <img v-else :src="tumbUrl" :alt="tumbAlt" />
    </div>
    <div>
      <div>
        Prime image
        <span><img src="" alt="" /></span>
      </div>
      <div>
        <span>{{ award }}</span>
        <span>{{ lastedDays }}</span>
      </div>
      <div>
        <h1>{{ title }}</h1>
      </div>
      <div>
        <p>{{ description }}</p>
        <ul>
          <li>{{ imdbReview }}</li>
          <li>{{ movieTime }}</li>
          <li>{{ releaseYear }}</li>

          <FilmsBadges />
        </ul>
        <ul>
          <li>{{ movieGenre }}</li>
        </ul>
        <span>{{ prime }}</span>
        <div>
          <div>
            <span>
              <PlayButton />
            </span>
            <PurchaseButtons :buy-price="20" :rent-price="20" />

            <ActionButtons />
          </div>
          <ul>
            <li>{{ trailer }}</li>
            <li>{{ addList }}</li>
            <li>{{ like }}</li>
            <li>{{ notForMe }}</li>
            <li>{{ download }}</li>
            <li>{{ watchParty }}</li>
            <li>{{ share }}</li>
          </ul>
        </div>
      </div>
      <div>
        <router-link to="">Ralated</router-link>
        <router-link to="">Datails</router-link>
      </div>
    </div>
  </div>
</template>

<script>
// import FilmsBadges from '@/components/mediaAttribute/FilmsBadges.vue';
// import PlayButton from '@/components/buttons-components/PlayButton.vue';
// import ActionButtons from '@/components/buttons-components/ActionButtons.vue';
import PurchaseButtons from "@/components/buttons-components/PurchaseButtons.vue";
import { push } from "core-js/core/array";

export default {
  data() {
    return {
      media: "",

      trailer: true,
      trailerUrl: "",

      tumbUrl: "",
      tumbAlt: "",

      prime: "",
      season: "Season 1",
      episode: "",

      title: "",

      releaseYear: "",
      movieTime: "",
      imdbReview: "",

      parentalRating: "",
      award: "",
      description: "",
    };
  },
  components: {
    // FilmsBadges,
    // PlayButton,
    // ActionButtons,
    PurchaseButtons,
  },
  methods: {
    pushJson() {
      fetch("../assets/json/PussInBoots-TheLastWish.json")
        .then((r) => r.json())
        .then((r) => {
          this.media = r;
        });
    },
  },
  created() {
    this.pushJson();
  },
};
</script>

<style>
</style>