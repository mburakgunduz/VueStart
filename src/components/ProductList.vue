<template>
  <div>
      <p v-if="products.length==0">Ürün listesi boş</p>
      <table class="table">
          <thead>
              <th>Id</th>
              <th>Ürün Adı</th>
              <th>Kategori</th>
              <th>Açıklama</th>
              <th>Birim Fiyatı</th>
              <th>Stok Adedi</th>
              <th></th>              
          </thead>
          <tbody>
              <tr v-for="product in products" :key="product.id">
                  <td>{{product.id}}</td>
                  <td>{{product.productName}}</td>
                  <td>{{product.categoryId}}</td>
                  <td>{{product.quantityPerUnit}}</td>
                  <td>{{product.unitPrice}}</td>
                  <td>{{product.unitsInStock}}</td>
                  <td><button class="btn btn-sm btn-danger" @click="handleDelete(product)">Sil</button></td>
              </tr>
          </tbody>
      </table>
      {{products.length}}
  </div>
</template>
<script>
export default {
    name:"product-list",
    props:{
        products:Array
    },
    methods:{
        handleDelete(){
            this.$emit("delete:product",product)
        },
        handleUpdate(){

        }
    }
};
</script>

<style scoped>
</style>