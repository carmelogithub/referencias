<template>
    <h2>Componente práctica</h2>
    <p>{{unidades}}</p>
    <p>{{token}} <button v-show="token">login</button></p>
    <button @click="getProductos">consultar</button>
</template>

<script>
export default {
  name: 'Practica',
  props: {
    unidades: Number,
    token:Boolean
  },
  data(){
      return{
          productos:[]
      }

  },
  methods:{
      async getProductos(){
          let response=await this.$http.get("https://my-json-server.typicode.com/Nelzio/ecommerce-fake-json/products");
          //console.log(response);
          this.productos=response.data;
          console.log(this.productos);

      }
  }
}
</script>