<template>
  <div class="ui cards" style="margin: 10px">
    <div class="ui icon input" style="width: 100%">
      <!--<input type="text" placeholder="Search..." v-model="searchQuery" />-->
      <input type="text" placeholder="Search..." />
      <i class="search icon"></i>
    </div>
    <div
      class="card ui fluid"
      v-for="product in searchedProducts"
      :key="product.id"
      style="margin: 0"
    >
      <div class="content">
        <img class="right floated mini ui image" :src="product.imageURL" />
        <div class="header">{{ product.title }}</div>
        <div class="meta">
          {{ product.upc }} | {{ product.weight }} Kg |
          {{ product.itemsperpack }} pack
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import firebase from "firebase";
//import { onMounted, reactive, ref, computed } from "vue";
import { onMounted, reactive } from "vue";
export default {
  setup() {
    const products = reactive([]);
    //const searchQuery = ref("");
    onMounted(async () => {
      try {
        const productsSnap = await firebase
          .firestore()
          .collection("products")
          .get();
        productsSnap.forEach((doc) => {
          products.push(doc.data());
        });
      } catch (e) {
        console.log("Error Loading Products");
      }
    });
    //const searchedProducts = computed(() => {
    //  return products.value.filter((product) => {
    //    return (
    //      product.title
    //        .toLowerCase()
    //        .indexOf(searchQuery.value.toLowerCase()) != -1
    //    );
    //  });
    //});
    
    return { products }; // add searchedProducts
  },
};
</script>
