<script setup>

  import { ref, onMounted } from 'vue'

  const isMetamaskSupported = ref(false)
  const address = ref('')

  onMounted(() => {
    isMetamaskSupported.value = typeof window.ethereum !== 'undefined'
  })

  async function connect() {
    const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' })
    address.value = accounts[0]
  }

</script>

<template>

  <!-- <button v-if="isMetamaskSupported" @click="connect">Sign In with Metamask</button>

  <p v-else>Install Metamask extension</p>

  <p>{{ address.substring(0, 8) + '...' }}</p> -->

    <header>
      <nav class="barnav">
        <img src="../assets/img/CUYTOPIA_logo_3.svg">
         
        <ul class="lista">
          <li>Home</li>
          <li>Roadmap</li>
          <li>Team</li>
          <li>FAQ</li>
        </ul>
        <button>CONNECT</button>
      </nav>
    </header>


    <main class="banner">
      <div class="wrapper">
        <img src="../assets/img/banner.png">
        <div class="texts">
          <h1 class="title">
            A SOLARPUNK <br>
            GUINEA PIG NFT <br>
            PFP PROJECT
          </h1> <br>
          <p class="subtitle">
            Long time ago, in a galaxy know  <br>
            as the milky way, guinea pigs where the guardians of planet earth
          </p>
        </div>
      </div>
    </main> <br><br><br><br>

    <div class="card">
      <img src="../assets/img/card.png">

      <p class="card-title">MEET THE CUYTOPIANS</p> <br>
      <p class="card-subtitle">This is the the start of a solarpunk adventure and own a digital guinea pig</p> <br><br>

      <button  v-if="isMetamaskSupported" @click="connect">CONNECT</button>

      <p>{{ address.substring(0, 8) + '...' }}</p>

    </div> <br><br><br><br>

    
    <div class="mosaico">
      <p>text</p>
    </div>

    <footer>
      <ul>
        <li>Discord</li>
        <li> <a href="https://twitter.com/CuyTopia">Twitter</a></li>
        
      </ul>
      <p>Made with 💗 in Peru</p>
    </footer>

</template>



<style>
  

  @import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@200;400;700&family=Titillium+Web:wght@900&display=swap');

  /*Reset*/
  html,
  body,
  p,
  ol,
  ul,
  li,
  dl,
  dt,
  dd,
  blockquote,
  figure,
  fieldset,
  legend,
  textarea,
  pre,
  iframe,
  hr,
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    margin: 0;
    padding: 0;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    font-size: 100%;
    font-weight: normal;
  }

  ul {
    list-style: none;
  }

  button,
  input,
  select {
    margin: 0;
  }

  html {
    box-sizing: border-box;
  }

  *,
  *::before,
  *::after {
    box-sizing: inherit;
  }

  img,
  video {
    height: auto;
    max-width: 100%;
  }

  iframe {
    border: 0;
  }

  table {
    border-collapse: collapse;
    border-spacing: 0;
  }

  td,
  th {
    padding: 0;
  }



  html, body {
    margin: 0;
    height: 100%;
    width: 100%;
    -webkit-font-smoothing: antialiased;
  }

  /*css presonalizado*/

  p, body {
    font-family: 'Roboto Mono', monospace;
    font-size: 16px;
  }

  h1 {
    font-family: 'Titillium Web';
    font-style: normal;
    font-weight: 900;
    font-size: 67px;
    line-height: 70px;
  }

  button {
    background: #FFFDF1;
    border: 3px solid #000000;
    box-shadow: -2px 4px 0px #333333;
    border-radius: 5px;
    font-family: 'Titillium Web';
    font-style: normal;
    font-weight: 900;
    font-size: 16px;
    line-height: 24px;
    display: flex;
    align-items: center;
    text-align: center;
    height: 40px;
    
  }


  .barnav {
    display: flex;
    justify-content: space-between;
    background-color: #FFD400;
    padding: 5px 20px;
    align-items: center;
    height: 80px;
  }



  .lista>li {
     list-style: none; 
    display: inline;
    justify-content: right;
    font-family: 'Roboto Mono';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 32px;

  }


  /**************** Banner *********************/
  .banner {
    background: #30458F;
    color: white;
  }

  .banner .wrapper {
    padding: 24px;
  }

  .banner .wrapper img {
    max-width: 240px;
    display: table;
    margin: auto;
  }

  @media (min-width: 950px) {
    .banner .wrapper {
      display: flex;
      justify-content: space-between;
      max-width: 1200px;
      margin: auto;
      padding: 0 24px;
    }
    .banner .wrapper .texts {
      margin-top: 50px;
    }
    
    .banner .wrapper img {
      max-width: 460px;
    }
  }

  .banner .wrapper .title {
    font-family: "Titillium Web";
    font-size: 67px;
    line-height: 70px;
    -webkit-text-stroke: 1px black;
  }
  .banner .wrapper .subtitle {
    font-family: "Roboto Mono";
    font-size: 28px;
  }
  /***********************************************/

  /******************** Card *********************/
  .card {
    max-width: 369px;
    margin: auto;
    border: solid 5px #000;
    border-radius: 20px;
    text-align: center;
    padding: 24px;
  }
  .card img {
    max-width: 130px;
    margin: auto;
    display: table;
    margin-top: -65px;
  }

  .card .card-title {
    font-family: "Titillium Web";
    font-size: 37px;
    line-height: 36px;
    
  }

  .card .card-subtitle {
    font-family: "Roboto Mono";
    font-size: 16px;
  }

  .card button {
    margin: auto;
  }
  /***********************************************/


  .mosaico{
    background-image: url(../assets/img/banner-cuys1.png);
    height: 50vh;
    width: auto;
    object-fit: cover;
    background-size: contain;
  }


  footer{
    background-color: #585858;
    height: 150px;
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  footer>ul{
    color: white;
  }

  footer>li{
    color: white;
    display: inline;
  }

  footer>p{
    color: white;
  }

  a {
    text-decoration: none;

  }

  a:visited {
    color: white;
  }

  a:hover {
    color: #FFD400;
  }

</style>
