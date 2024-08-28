
<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Jersey+10&display=swap" rel="stylesheet">
    <Scene class="scene"/>
    <img src="/src/assets/Images/UTMMA WEBLOGO.png" alt="UTM Martial Arts" id="logo1" />
    <img src="/src/assets/Images/UTMMA WEBLOGO.png" alt="UTM Martial Arts" id="logo2" />

    <div id="text">Coming Soon</div>
    <Link id="instalink" url="https://www.instagram.com/utmmartialarts/" imageSrc="./src/assets/Images/instagram.png" altText="Instagram logo"/>
    <Link id="discordlink" url="https://discord.com/invite/7mKsUxmWZ7" imageSrc="./src/assets/Images/discord.png" altText="Instagram logo"/>
    
</template>

<script setup>
import Link from './components/Link.vue'
import Scene from './components/Scene.vue'
</script>

<style>
#app{
  background-color: black;
}
.scene {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 1;
}
#logo1, #logo2 {
  position: fixed;
  top: 45%;
  transform: translateY(-50%);
  z-index: 2;
  width: 300px;
  height: auto; /* Maintain aspect ratio */
}

#logo1 {
  left: 180px;
}

#logo2 {
  right: 180px;
}

#text {
  color: white;
  position: fixed;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  font-size: 60px;
  font-family: "Jersey 10", sans-serif;
  font-weight: 400;
  font-style: normal;
}
#instalink {
  position: fixed;
  top: 86%; /* Adjust this value to fine-tune the vertical position */
  left: calc(50% - 27px); /* Moved 27px to the left of center */
  transform: translateX(-50%);
  z-index: 2;
}
#discordlink {
  position: fixed;  
  top: 86%; /* Adjust this value to fine-tune the vertical position */
  right: calc(50% - 27px); /* Moved 27px to the right of center */
  transform: translateX(50%);
  z-index: 2;
}

@font-face {
  font-family: "myFont";
  src: url("https://fontsfree.net/?s=Avenir%20Next%20Condensed%20Bold");
}

@media (max-width: 1140px) {

  #logo1, #logo2 {
  position: fixed;
  top: 45%;
  transform: translateY(-50%);
  z-index: 2;
  width: 300px;
  height: auto; /* Maintain aspect ratio */
}

#logo1 {
  left: 70px;
}

#logo2 {
  right: 70px;
}

  #text {
    font-size: 60px;
    top: 80%;
  }

  #instalink, #discordlink {
    top: 85%;
  }
}

#logo1, #logo2 {
  position: fixed;
  top: 45%;
  transform: translateY(-50%);
  z-index: 2;
  width: 300px;
  height: auto; /* Maintain aspect ratio */
}

#logo1 {
  left: 180px;
}

#logo2 {
  right: 180px;
}

#text {
  color: white;
  position: fixed;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  font-size: 60px;
  font-family: "Jersey 10", sans-serif;
  font-weight: 400;
  font-style: normal;
}
#instalink {
  position: fixed;
  top: 86%; /* Adjust this value to fine-tune the vertical position */
  left: calc(50% - 27px); /* Moved 27px to the left of center */
  transform: translateX(-50%);
  z-index: 2;
}
#discordlink {
  position: fixed;
  top: 86%; /* Adjust this value to fine-tune the vertical position */
  right: calc(50% - 27px); /* Moved 27px to the right of center */
  transform: translateX(50%);
  z-index: 2;
}

@font-face {
  font-family: "myFont";
  src: url("https://fontsfree.net/?s=Avenir%20Next%20Condensed%20Bold");
}

@media (max-width: 1140px) {

  #logo1, #logo2 {
  position: fixed;
  top: 45%;
  transform: translateY(-50%);
  z-index: 2;
  width: 300px;
  height: auto; /* Maintain aspect ratio*/
}

#logo1 {
  left: 70px;
}

#logo2 {
  right: 70px;
}

  #text {
    font-size: 60px;
    top: 80%;
  }

  #instalink, #discordlink {
    top: 85%;
  }
}

@media (max-width: 768px) {


  #logo1 {
    width: 130px;
    top: 6%;
    left: 50%;
    transform: translateX(-50%);
  }
  #logo2 {
    display: none;

  #text {
    font-size: 60px;
    top: 76%;
  }

  #instalink, #discordlink {
    top: 80%;
  }
}
}

@media (max-width: 480px) {

  .scene {
    top: 5%;
  }
  #logo1 {
    width: 130px;
    top: 8%;
    left: 50%;
    transform: translateX(-50%);
  }
  #logo2 {
    display: none;
  }
  #text {
    font-size: 30px;
    top: 79%;
  }

  #instalink, #discordlink {
    top: 85%;
  }

  #instalink {
    left: calc(50% - 30px);
  }

  #discordlink {
    right: calc(50% - 30px);
  }
}
</style>