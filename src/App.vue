<template>
  <div id="app">
    <ProductList @delete:product="deleteProduct" :products="products"/>
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue'

export default {
  name: 'App',
  components: {
    ProductList
  },
  data(){
    return {
      products:[
        {id:1, categoryId:1, productName:'Laptop', quantityPerUnit:'Acer Laptop', unitPrice:5000, unitsInStock:2},
        {id:2, categoryId:1, productName:'Mouse', quantityPerUnit:'Acer Mouse', unitPrice:50, unitsInStock:4},
        {id:3, categoryId:2, productName:'Keyboard', quantityPerUnit:'Acer Keyboard', unitPrice:50, unitsInStock:6}
        ]
    }
  },
  methods:{
    deleteProduct(product){
      this.products = this.products.filter(
        productToFilter=>productToFilter.id !== product.id
      )
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
