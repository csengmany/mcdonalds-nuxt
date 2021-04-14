<template>
  <div>
    <nav class="navbar navbar-dark bg-dark">
      <ul class="nav">
        <li class="nav-item active">
          <nuxt-link class="nav-link" to="/" >
          <img class="mcdo-logo" src="../assets/images/mcdo-logo.jpg" alt="">
          </nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/menus" >Commander</nuxt-link>
        </li>
        <li class="nav-item">
          <nuxt-link class="nav-link" to="/restaurant" >Votre restaurant</nuxt-link>
        </li>
      </ul>
    </nav>
    <div class="container">
        <Nuxt />
    </div>
  <footer>
            <span>
                © {{date}}&nbsp;Cathy Sengmany, built with <Logo class="footer-logo"/>
            </span>
  </footer> 
  </div>
</template>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

a {
  text-decoration: none;
  color: #fff;
}
a:hover {
  color: #04C58E;
}
.nuxt-link-exact-active {
  color: #3b8070;
}
.mcdo-logo {
  height: 60px;
  border-radius: 5px;
}

.nav-item {
  display: flex;
  align-items: center;
}
footer {
  display: flex;
  justify-content: center;
  align-items: center;
}
.nuxt{
  height: 30px;
}
@media(max-width:399px){
  nav{
    flex-direction: column;
     justify-content: center;
     align-items: center;
  }
   .nav{
     flex-direction: column;
     justify-content: center;
     align-items: center;
   }
   footer{
    display: flex;
    justify-content: center;
    align-items: center;
}

.footer-logo{
    height: 20px;
    width: 25px;

}
}
</style>
