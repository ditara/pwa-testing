<template>
<b-row class="row-category">
    <b-col class="col-md-12 mt-5 mb-4">
        <Title :strtitle="ttl"/>
    </b-col>
    <b-col class="col-md-4" v-for="(data, index) in datacategory" :key="index">
        <b-card
            v-bind:img-src="data.strCategoryThumb"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="mb-2"
        >
            <h6 class="category-text">{{ data.strCategory }}</h6>
            <b-card-text>{{ data.strCategoryDescription | truncate(50, '...')}}</b-card-text>
        </b-card>
    </b-col>
</b-row>
</template>
<script>
import axios from 'axios';
import Title from './Title.vue';

export default {
  data() {
    return {
      ttl: 'Categories',
      tgs: 'Category',
      datacategory: [],
    };
  },
  components: {
    Title,
  },
  async created() {
    const BASEURI = 'https://www.themealdb.com/api/json/v1/1/categories.php';
    axios.get(BASEURI).then((result) => {
      this.datacategory = result.data.categories;
    });
  },
  filters: {
    truncate(value, length, suffix) {
      if (value.length > length) {
        return value.substring(0, length) + suffix;
      }
      return value;
    },
  },
};
</script>
<style>
.row-category {
    background-color: none;
    padding: 50px;
}
.category-text {
    text-align: center;
}
</style>
