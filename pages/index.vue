<template>
   <div style="text-align : center " class="white--text">
  <img src="https://uploads.scratch.mit.edu/users/avatars/36012852.png" alt=""><br>
  <input class="white--text" type="text" v-model="textSearch " />
  <button @click="searchData()">ค้นหา</button>
  <li  v-for="data in List" :key="data.mal_id">
        <nuxt-link :to="{ name: 'product-id', params: { id: data } }">
          {{data.title}}
        </nuxt-link>
      </li>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      List: null,
      textSearch: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get("https://api.jikan.moe/v3/search/anime?q="+this.textSearch+"limit=25")
        .then((response) => {
          this.List = response.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
}
</script>
<style>
</style>