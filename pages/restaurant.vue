<template>
<div class="container">
 
    <h1>Votre restaurant</h1>
       <img class="picture" src="../assets/images/macdonalds.jpg" alt="">
    <p>Chaîne emblématique de restauration rapide proposant des menus de burgers-frites, des desserts et milk-shakes.</p>
    <iframe class="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3176.3880960955457!2d6.0832506717817125!3d46.22601384030902!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x478c636e7c8ba715%3A0x54d11ce8bd6920a4!2sMcDonald&#39;s!5e0!3m2!1sfr!2sfr!4v1618418105824!5m2!1sfr!2sfr" width="100" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>

<div>
        <ul>
        <li><strong>Adresse :</strong> Chemin de Riantbosson 19, 1217 Meyrin, Suisse</li>
        <li><strong>Horaires :</strong></li>
        <ul>
            <li>lundi : 10:00-23:00</li>
            <li>mardi : 10:00-23:00</li>
            <li>mercredi : 10:00-23:00</li>
            <li>jeudi : 10:00-23:00</li>
            <li>vendredi : 10:00-23:00</li>
            <li>samedi : 10:00-23:00</li>
            <li>dimanche : 10:00-23:00</li>
        </ul>
        <li><strong>Menu :</strong> <nuxt-link to="/menus">macdonalds.fr</nuxt-link>
        <li><strong>Téléphone :</strong> 01 34 00 00 00</li>
    </ul>
</div>
</div>
</template>

<script>
</script>

<style scoped>
.map {
    width: 100%;
    height: 350px;


    }
.picture {
    min-width: 600px;
    height: 200px;
    object-fit: cover;
    object-position: center;
    }
div {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    }
ul,p{
    text-align: left;
}
li {
    list-style: none;
}
a{
    text-decoration: none;
    font-weight: 400;
    color:black
}
a:hover{
    color:  #04c58e  ;
}
@media(max-width:599px){
    .picture {
    min-width: 100%;
    }
}
</style>