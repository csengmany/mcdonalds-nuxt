<template>
    <div class="card bg-light text-dark m-3" style="width: 18rem;">

        <img v-if="role==='menu'" :src="require('../assets/images/'+img+'.png')" >

        <div class="card-body">
            <h5 class="card-title">{{name}}</h5>
            <p class="card-text">{{Number(price).toFixed(2)}}€</p>
            <button v-if="role==='menu'" @click="$emit('cart', name, price)" class="btn btn success"> Commander</button>  
            <div v-if="role==='cart'">
              <span >x{{quantity}}</span>  <span  class="btn-quantity" @click="$emit('cart', name, price)"><img src="@/assets/images/add.svg" alt="add"></span><span @click="$emit('soustract', name, price)" class="btn-quantity"><img  src="@/assets/images/soustract.svg" alt="soustract"></span>
               <font-awesome-icon @click="$emit('remove', name, price)" class="trash" :icon="['fas', 'trash']"/>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "Product",
  props: ["name", "price","role", "img","quantity"],
};
</script>

<style>
.card {
  min-width: 150px;
  max-width: 100%;
}
.btn  {
  background: green;
  color: white;
}
.card-body{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.btn-quantity img{
  height: 17px;
  cursor: pointer;
}

.card-body:last-child span{
  margin-right: 5px;
}
.trash{
  color: #108775;
  cursor: pointer;
}

</style>
