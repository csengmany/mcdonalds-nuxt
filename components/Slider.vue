<template>
    <div class="slider">
            <button @click="prev()" type="button" class="btn btn-left">
                <img src="../assets/images/chevron-left.svg" alt="chevron left">
            </button>
            <div class="container-slides" :style="{transform:`translateX(${index}px)`,transition:`${transition}`}">
                <img src="../assets/images/bigmac.png" alt="big mac" class="img-slider">
                <img src="../assets/images/frites.png" alt="frites" class="img-slider">
                <img src="../assets/images/mcflurry.png" alt="mc flurry" class="img-slider">
            </div>
            <button @click="next()" type="button" class="btn btn-right">
                <img  src="../assets/images/chevron-right.svg" alt="chevron left">
            </button>
    </div>
    
</template>

<script>
export default {
    name: "Slider",
    data: function(){
        return{
            index: 0,
            transition: "transform 0.2 ease"
        }
    },
    methods: {
        next(){
            if (this.index === -600) {
                this.transition="none";
                this.index = 0;
            }else{
                this.transition="transform 0.2 ease";
                this.index -= 300;
            }

        },

         prev(){
            if (this.index ===0) {
                this.transition="none";
                this.index=-600;
            }else{
                this.transition="transform 0.2 ease";
                this.index+=300;
            }

        }
    }

}
</script>

<style  scoped>
button {
    background: white;
}
img {
    margin-right: 20px;
    height: 15px;    
}
.img-slider{
    width:300px;
    height: auto;
}
.slider {
    width: 340px;
    height: auto;
    margin:0 auto ;
    overflow: hidden;
    position: relative;

    display: flex;
    justify-content: flex-start;
    align-items: center;
 }
.container-slides{
    display: flex;
}
.btn {
    outline: none;
    border : none;
    width: 30px;
    height: 30px;
    border-radius: 50%;

    display: block;
    position: absolute;
    z-index: 10;
    cursor: pointer;


    overflow: hidden;
    justify-content: center;
    align-items: center;

}
.btn-left{
    top: 50%;
    left:10px;
    transform: translateY(-50%);
}
.btn-right{
    top: 50%;
    right:10px;
    transform: translateY(-50%);
}

</style>