<template>
    <div>
        <h1>Commander</h1>
        <h2>Les produits disponibles</h2>
        <!-- <p v-for="product in products">
            {{product.name}} - {{product.price}}
        </p> -->
        <div class="card-deck">
                    <Product v-for="(product, index) in products"
                    :key="index"
                    v-bind:name="product.name"
                    :price="product.price"
                    :img="product.img"
                    role="menu"
                    v-on:cart="addProduct(product)"/>
        </div>
        <h2>Votre panier</h2>
     
        <div class="card-deck">
                    <Product v-for="(product, index) in cart"
                    :key="index"
                    v-bind:name="product.name"
                    role="cart"
                    :price="product.price.toFixed(2)"
                    :quantity="product.quantity"
                    v-on:cart="addProduct(product)"
                    v-on:soustract="soustractProduct(product)"
                    v-on:remove="removeProduct(product)"
                     
                    />
        </div>

        <div class="card bg-light text-dark m-3" style="width: 18rem;">
               <h5 class="card-body">Total : {{total(cart)}}€</h5>
               <button v-if="cart.length>0" class="btn" @click="finish">Valider ma commande</button>
        </div>
    </div>
</template>

<script>
import Product from '../components/Product.vue'
    export default {
  components: { Product },
        data() {
            return{
                products : [
                    {name:"Menu Royal Deluxe", price:8.7,img:"menu"},
                    {name:"Menu Big Tasty", price:10.5,img:"menu"},
                    {name:"Big Mac", price:5,img:"bigmac"},
                    {name:"Cheeseburger", price:2.7,img:"cheeseburger"},
                    {name:"McNuggets", price:3.5,img:"mcnuggets"},
                    {name:"Frites", price:2,img:"frites"},
                    {name:"Coca-Cola", price:2.9,img:"coca-cola"},
                    {name:"Evian", price:3.5,img:"evian"},
                    {name:"Mc Flurry", price:4.2,img:"mcflurry"},
                    {name:"Donut", price:2.5,img:"donut"},
                    ],
                cart: [{name:"Frites",price:2, quantity:1} ],
                
            }
        },
        methods:{
            addProduct(product){
                if(this.cart.some(elem=>elem.name===product.name)){
                    this.cart.map((elem,index)=>{
                        if(elem.name===product.name){
                            elem.quantity+=1;
                        }
                    })
                }else{
                    this.cart.push({name:product.name, price:product.price, quantity:1})
                    }
            }, soustractProduct(product){
                if(this.cart.some(elem=>elem.name===product.name)){
                    this.cart.map((elem,index)=>{
                        if(elem.name===product.name){
                            if(elem.quantity===1){
                                this.cart.splice(product,1)
                            }else{
                                elem.quantity-=1;
                            }
             
                        }
                    })
                }
            },removeProduct(product){

            this.cart.splice(product,1)

            },total(cart){
                let total=0;
                this.cart.map((product,index)=>{
                    total+=(product.price*product.quantity)

                })
             return total.toFixed(2)
            }, finish(){
                alert("Merci d'avoir passer commande chez Mc Donald's Nuxt!\nVotre commande arrive dans 20 minutes.")
            }
        }

    }
</script>

<style scoped>

</style>