<template>
  <div>

    <!-- My thought process... playlist section  would hold the titles to the song, which are linked to a button click-->
    <!-- that button click would trigger the information in the chooseSong function and display it in the playing section -->

    <!-- I know I am missing how this all works together and I think I am mixing the old way concept with the new way concepts -->
    
    <section ref="playlist" v-for="song in song_info" :key="song[`song_id`]">
      <h4 @click="chooseSong" >{{ song[`title`] }}</h4>
    </section>
    <section v-if="song_info === true">
      <article ref="playing" v-for="song in song_info" :key="song[`song_id`]">
        <h2>{{song[`title`]}}</h2> 
      </article>
       
  
    </section>
  </div>
</template>

<script>
export default {
  methods: {
    chooseSong() {
     if(this.song_info === true) {
      for (let i = 0; i < this.song_info.length; i++) {
        
        (this.ref[`playing`][`innerHTML`] = `
            <h2>${this.song_info[`title`]}</h2>`),
          `<h3>${this.song_info[`artist`]}</h3>`;
      }
     }
    },
  },

  data() {
    return {
      song_info: [
        {
          title: `Imagine`,
          artist: `John Lennon`,
          song_id: `71`,
          img_url: `value`,
        },
        {
          title: `Ramble On`,
          artist: `Led Zeppelin`,
          song_id: `69`,
          img_url: `value`,
        },
        {
          title: `Santeria`,
          artist: `Sublime`,
          song_id: `96`,
          img_url: `value`,
        },
        {
          title: `Californication`,
          artist: `Red Hot Chilli Peppers`,
          song_id: `99`,
          img_url: `value`,
        },
        {
          title: `Riding for a fall`,
          artist: `Mad Caddies`,
          song_id: `07`,
          img_url: `value`,
        },
        {
          title: `Warmness on the soul`,
          artist: `Avenged 7x`,
          song_id: `01`,
          img_url: `value`,
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>