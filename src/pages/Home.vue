<script setup lang="ts">
import { onMounted } from "vue";
import SvgImage from "../components/SvgImage.vue";

onMounted(() => {
  console.log("APP MOUNTED")
  let audioElem = document.querySelector("audio");
  audioElem.click();
  audioElem.muted = false;
  audioElem.play()
})
</script>

<template>
  <div id="app-container">
    <header>
      <SvgImage data="/assets/img/logo_montblanc.svg" id="logo" />
      <nav>
        <ul>
          <li><a href="#" title="">Bikes</a></li>
          <li><a href="#" title="">Accesories</a></li>
          <li><a href="#" title="">New tech</a></li>
          <li><a href="#" title="">Explore</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <picture id="bike-container">
        <source srcset="/assets/img/bike.jpg" media="(min-width: 800px)">
        <img src="/assets/img/bike.jpg" alt="" />
      </picture>

      <div id="bike-wheel">vdvf</div>

      <div id="bike-details">
        <div class="bike-info-container">
          <h4>TOP SPEED</h4>
          <div class="informations">
            <p class="info-title">6-SPEED CONSTANT-MESH</p>
            <p class="info-value">169 MPH</p>
            <p class="info-converted-value">272 KM/H</p>
          </div>
        </div>
        <div class="bike-info-container">
          <h4>POWER</h4>
          <div class="informations">
            <p class="info-title">121 KW</p>
            <p class="info-value">162 HP</p>
            <p class="info-converted-value">9,25 RPM</p>
          </div>
        </div>
        <div class="bike-info-container">
          <h4>TORQUE</h4>
          <div class="informations">
            <p class="info-title">8,800 RPM</p>
            <p class="info-value">130.5 N.M</p>
            <p class="info-converted-value">96.6 LBF.FT</p>
          </div>
        </div>
        <div class="bike-info-container">
          <h4>FUEL CAPACITY</h4>
          <div class="informations">
            <p class="info-title">4.5 US GAL</p>
            <p class="info-value">17 L</p>
            <p class="info-converted-value">3.7 IMP GAL</p>
          </div>
        </div>
      </div>
      <SvgImage data="assets/img/montblanc_motorcycle_circle.svg" id="mont_blanc_logo" />
      <SvgImage data="assets/img/asian-text.svg" class="asian-text" id="asian-text-01" />
      <SvgImage data="assets/img/asian-text.svg" class="asian-text" id="asian-text-02" />

      <p id="bike-text-summary">The bike comes in all black, with a relatively modern appeal. Chrome accents in just
        the right places make the bike stand out, while the black-on-black satin text on the bike’s fork-guards helps
        highlight the company’s branding without being too direct or obvious.</p>
    </main>
  </div>
</template>

<style scoped lang="scss">
@use "sass:string";

@function autoSizing($size, $coeffReducer: 0.7) {
  @return string.unquote("calc(#{$size}px * #{$coeffReducer})");
}

@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');

img {
  width: 100%;
  height: 100%;
}

#app-container {
  width: autoSizing(1742);
  height: autoSizing(1124);
  background: #060507;
  border-radius: 32px;
  border: 2px solid #060507;
  position: relative;
  font-family: arial;
  animation: appContainerDisplay 500ms ease-out 3s forwards;

  #audio-container {
    display: none;
  }

  header {
    width: autoSizing(1200);
    height: autoSizing(120);
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
    align-content: flex-start;
    align-items: center;
    // background-color: red;

    #logo {
      width: autoSizing(285);
      height: autoSizing(45);
      margin-left: autoSizing(64);
      margin-right: autoSizing(50);
    }

    ul {
      list-style-type: none;
      width: 100%;
      margin: 0;
      // background-color: green;
      display: flex;
      justify-content: space-between;

      li {
        display: inline-block;

        >a {
          color: #ffffff;
          font-family: Arial;
          font-size: 0.9rem;
          font-weight: 700;
          text-transform: uppercase;
          text-decoration: none;
          margin-left: 2rem;
        }
      }
    }
  }

  #bike-container {
    width: autoSizing(1200);
    height: autoSizing(813);
    position: absolute;
    animation: bikeSlideLeft 1500ms ease-out forwards;
  }

  #bike-wheel {
    width: autoSizing(316);
    height: autoSizing(658);
    background-image: url('../assets/img/bike_wheel.jpg');
    z-index: 0;
    position: absolute;
    top: autoSizing(100);
    right: autoSizing(220);
    background-color: red;
    animation: bikeWheelSlideLeft 500ms ease-out;
  }

  #bike-details {
    width: autoSizing(353);
    height: 100%;
    position: absolute;
    z-index: 4;
    bottom: 0;
    right: 0;
    background-color: #060507;
    border-bottom-right-radius: 32px;
    border-top-right-radius: 32px;
    padding: autoSizing(40);
    padding-top: 20%;
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-around;

    .bike-info-container {
      margin-bottom: 2px;
      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      height: autoSizing(148);
      color: #ffffff;
      opacity: 0;
      animation: fadeIn 500ms ease-in forwards;

      &:nth-child(1) {
        animation-delay: 400ms;
      }

      &:nth-child(2) {
        animation-delay: 800ms;
      }

      &:nth-child(3) {
        animation-delay: 1200ms;
      }

      &:nth-child(4) {
        animation-delay: 1600ms;
      }

      h4 {
        width: auto;
        height: 100%;
        writing-mode: vertical-lr;
        text-orientation: mixed;
        font-size: autoSizing(18);
        font-weight: 100;
        color: #3F3E44;
        margin: 0 18px 0 0;
        text-align: center;
      }

      .informations {
        height: 100%;
        display: flex;
        flex-flow: column nowrap;
        justify-content: space-evenly;

        >p {
          margin: 0;
          padding: 0;
        }

        .info-title {
          font-size: autoSizing(12);
          font-weight: 100;
          text-transform: uppercase;
          font-family: 'Montserrat', sans-serif;
        }

        .info-value {
          font-size: autoSizing(32);
          font-weight: 700;
          text-transform: uppercase;
        }

        .info-converted-value {
          font-size: 12px;
          font-weight: 100;
          text-transform: uppercase;
          font-family: 'Montserrat', sans-serif;
        }
      }


    }
  }

  #mont_blanc_logo {
    width: autoSizing(183);
    width: autoSizing(183);
    position: absolute;
    left: autoSizing(990);
    top: autoSizing(214);
    opacity: 0;
    animation: montblancLogoRotate 1500ms ease-in-out 2500ms forwards;
  }

  .asian-text {
    position: absolute;
    top: autoSizing(740);
    opacity: 0;
    width: autoSizing(822);
    height: autoSizing(150);
    transform-origin: left bottom;
  }

  #bike-text-summary {
    width: autoSizing(406);
    font-size: autoSizing(12);
    position: absolute;
    bottom: 50px;
    left: autoSizing(590);
    color: #ffffff;
    opacity: 0;
    animation: displaySummary 2000ms linear 1s forwards;
  }

  #asian-text-01 {
    left: 0;
    animation: asianTextSlideLeft 800ms ease-in-out 800ms forwards;
  }

  #asian-text-02 {
    right: 0;
    animation: asianTextSlideLeft 800ms ease-in-out 500ms forwards;
  }


}

@keyframes bikeWheelSlideLeft {
  0% {
    transform: translateX(100px);
  }

  100% {
    transform: translateX(0px);
  }
}

@keyframes displaySummary {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }

}

@keyframes appContainerDisplay {
  to {
    border-color: #ffffff;
    border-width: 2px;
  }

}

@keyframes montblancLogoRotate {
  0% {
    transform: scale(0) rotate(360deg);

  }

  90% {
    opacity: 1;
    transform: scale(1.2);
  }

  100% {
    opacity: 1;
    transform: scale(1) rotate(20);
  }
}

@keyframes bikeSlideLeft {
  0% {
    transform: scale(0.4);
    opacity: 0;
  }

  100% {
    transform: scale(1);
  }
}

@keyframes asianTextSlideLeft {
  0% {
    transform: translateY(5rem);
    opacity: 0;
  }

  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;

  }

  to {
    opacity: 1;
  }
}
</style>
