<template>
  <div class="home">
    <!-- A carousel with any images/titles you would like to use -->
    <div class="container">
      <div class="carousel">
        <ul class="slides">
          <input type="radio" name="radio-buttons" id="img-1" checked />
          <li class="slide-container">
            <div class="slide-image">
              <img
                style="object-fit: cover; overflow: hidden"
                src="../assets/pug-2.jpg"
              />
            </div>
            <div class="carousel-controls">
              <label for="img-3" class="prev-slide">
                <span></span>
              </label>
              <label for="img-2" class="next-slide">
                <span>&rsaquo;</span>
              </label>
            </div>
          </li>
          <input type="radio" name="radio-buttons" id="img-2" />
          <li class="slide-container">
            <div class="slide-image">
              <img
                style="object-fit: cover; overflow: hidden"
                src="../assets/pug-3.jpg"
              />
            </div>
            <div class="carousel-controls">
              <label for="img-1" class="prev-slide">
                <span>&lsaquo;</span>
              </label>
              <label for="img-3" class="next-slide">
                <span>&rsaquo;</span>
              </label>
            </div>
          </li>
          <input type="radio" name="radio-buttons" id="img-3" />
          <li class="slide-container">
            <div class="slide-image">
              <img
                style="object-fit: cover; overflow: hidden"
                src="../assets/pug-4.jpg"
              />
              />
            </div>
            <div class="carousel-controls">
              <label for="img-2" class="prev-slide">
                <span>&lsaquo;</span>
              </label>
              <label for="img-1" class="next-slide">
                <span>&rsaquo;</span>
              </label>
            </div>
          </li>
          <div class="carousel-dots">
            <label for="img-1" class="carousel-dot" id="img-dot-1"></label>
            <label for="img-2" class="carousel-dot" id="img-dot-2"></label>
            <label for="img-3" class="carousel-dot" id="img-dot-3"></label>
          </div>
        </ul>
      </div>
    </div>

    <div class="container">
      <div class="row" align="left" id="paragraph">
        <!-- Intro heading -->
        <h1>The Story of the Pug Called Poet</h1>
        <!-- Intro text-->
      </div>
      <div class="row" align="left" id="paragraph">
        <p>
          Eighteen years, eighteen years She got one of your kids, got you for
          eighteen years I know somebody payin' child support for one of his
          kids His baby mama car and crib is bigger than his You will see him on
          TV any given Sunday Win the Super Bowl and drive off in a Hyundai She
          was supposed to buy your shorty Tyco with your money She went to the
          doctor, got lipo with your money She walkin' around lookin' like
          Michael with your money Shoulda got that insured, Geico for your money
          If you ain't no punk Holla, "We want prenup! We want prenup!" (Yeah!)
          It's somethin' that you need to have 'Cause when she leave yo' ass,
          she gon' leave with half Eighteen years, eighteen years And on the
          18th birthday he found out it wasn't his?
        </p>
        <br />
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aut ut fugiat
          enim consequuntur minima. Eveniet, iste! Ullam earum, dignissimos
          sequi, laudantium quidem consequatur magnam dolorem suscipit, nulla
          corrupti vitae natus.
        </p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

@Component({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {}
</script>

<style>
#paragraph {
  padding: 3em 10em 0 10em;
}

@media only screen and (max-width: 600px) {
  #paragraph {
    padding: 10px;
  }
  img {
    max-width: 100%;
    height: auto;
  }
}

ul.slides {
  display: block;
  position: relative;
  height: 600px;
  margin: 0;
  padding: 0;
  overflow: hidden;
  list-style: none;
}

.slides * {
  user-select: none;
  -ms-user-select: none;
  -moz-user-select: none;
  -khtml-user-select: none;
  -webkit-user-select: none;
  -webkit-touch-callout: none;
}

ul.slides input {
  display: none;
}

.slide-container {
  display: block;
}

.slide-image {
  display: block;
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  opacity: 0;
  transition: all 0.7s ease-in-out;
}

.slide-image img {
  width: auto;
  min-width: 100%;
  height: 100%;
}

.carousel-controls {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  z-index: 200;
  font-size: 100px;
  line-height: 600px;
  color: #fff;
}

.carousel-controls label {
  display: none;
  position: absolute;
  padding: 0 20px;
  opacity: 0;
  transition: opacity 0.2s;
  cursor: pointer;
}

.slide-image:hover + .carousel-controls label {
  opacity: 0.5;
}

.carousel-controls label:hover {
  opacity: 1;
}

.carousel-controls .prev-slide {
  width: 49%;
  text-align: left;
  left: 0;
}

.carousel-controls .next-slide {
  width: 49%;
  text-align: right;
  right: 0;
}

.carousel-dots {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 20px;
  z-index: 999;
  text-align: center;
}

.carousel-dots .carousel-dot {
  display: inline-block;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: #fff;
  opacity: 0.5;
  margin: 10px;
}

input:checked + .slide-container .slide-image {
  opacity: 1;
  transform: scale(1);
  transition: opacity 1s ease-in-out;
}

input:checked + .slide-container .carousel-controls label {
  display: block;
}

input#img-1:checked ~ .carousel-dots label#img-dot-1,
input#img-2:checked ~ .carousel-dots label#img-dot-2,
input#img-3:checked ~ .carousel-dots label#img-dot-3,
input#img-4:checked ~ .carousel-dots label#img-dot-4,
input#img-5:checked ~ .carousel-dots label#img-dot-5,
input#img-6:checked ~ .carousel-dots label#img-dot-6 {
  opacity: 1;
}

input:checked + .slide-container .nav label {
  display: block;
}
</style>
