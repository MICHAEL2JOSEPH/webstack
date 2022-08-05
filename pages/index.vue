<template>
  <div>
  <div class="container1">
    <div class="img">
      <img src="./images/frontal image.png" class="user-img">
    </div>
    <div class="widthA">
      <h1>Hi there,</h1>
      <div class="container2">
      <h2>I am <span class="typed-text">{{ typeValue}}</span>
      <span class="cursor" :class="{'typing': typeStatus}">&nbsp;</span>
        </h2>
      </div>
      <h3 style="color:beige;">from Nigeria 💚🤍💚.</h3>
      <p>You can reach me in the <br> <strong class="ii">contact page.</strong></p>
      <a href="./contact">Contact me</a>
      <a href="./" class="btn1">About me</a>
    </div>
    <div class="seconddiv"><div class="widthB">
       
    </div>
    </div>

  
  </div>
  </div>

</template>

<script>
 export default {
    data() {
      return {
        slide: 0,
        sliding: null,
        typeValue: '',
        typeStatus: false,
        typeArray: ['MICHAEL by name,', 'a frontend developer,', 'a software developer,', 'good at team building.'],
        typingSpeed: 200,
        erasingSpeed: 100,
        newTextDelay: 2000,
        typeArrayIndex: 0,
        charIndex: 0
      }
    },
    methods: {
      onSlideStart(slide) {
        this.sliding = true
      },
      onSlideEnd(slide) {
        this.sliding = false
      },
      typeText() {
        if(this.charIndex < this.typeArray[this.typeArrayIndex].length) {
          if(!this.typeStatus)
          this.typeStatus = true;

          this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
          this.charIndex +=  1;

          setTimeout(this.typeText, this.typingSpeed);
        }
        else {
          this.typeStatus = false;
          setTimeout(this.eraseText, this.newTextDelay);
        }
      },
      eraseText() {
        if(this.charIndex > 0) {
          if(!this.typeStatus)
          this.typeStatus = true;

          this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1);
          this.charIndex -= 1;
          setTimeout(this.eraseText, this.erasingSpeed);
        }
        else {
          this.typeStatus = false;
          this.typeArrayIndex += 1;
          if(this.typeArrayIndex >= this.typeArray.length)
          this.typeArrayIndex = 0;

          setTimeout(this.typeText, this.typingSpeed + 1000);
        }
      }
    },
    created() {
      setTimeout(this.typeText, this.newTextDelay + 200);
    }
  }
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

::-webkit-scrollbar{width:3px;border-left:1px solid #48a2d6;}
::-webkit-scrollbar-thumb{background-color: #031c2b;}

body {
  width: 100%;
  height: 100vh;
}

.container2 span {
  font-size: 1.5em;
  font-weight: 400px;
}

.cursor {
  display: inline-block;
  margin-left: -3px;
  width: 3px;
  background-color: #fff;
  color: #fff;
  animation: cursorBlink 1s infinite;
}

.typing {
  animation: none;
}

@keyframes cursorBlink {
  49% { background-color: #fff; }
  50% { background-color: transparent; }
  99% { background-color: transparent; }
}

span .typed-text {
  color: #5c0248;
}

.container1 {
  width: 100%;
  height: 100%;
  padding: 0 8.5%;
  position: relative;
}

.container2 h2 {
  font-family: 'Times New Roman', Times, serif;
  color: white;
}

.container2 span {
  color: white;
}

.container2 {
  width: 42%;
  height: auto;
  padding: 8px; 
  display: flex;
  /* background:  blue; */
}

strong {
  color: rgb(14, 12, 12);
  text-decoration: underline;
  /* font-weight: 800; */
}

.widthA {
  margin-top: 15%;
  font-size: 17px;
  letter-spacing: 1px;
  line-height: 26px;
}

.widthA h1 {
  font-size: 75px;
  line-height: 160px;
  color: white;
  font-family: 'Times New Roman', Times, serif;
}

.widthA p {
  font-size: 1.5em;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  font-weight: 400;
  color: white;
}

.widthA a {
  margin-top: 30px;
  display: inline-block;
  border-radius: 14px;
  border: 2px solid purple;
  color: white;
  background: purple;
  margin-bottom: 10px;
  padding: 10px 30px;
  text-decoration: none;
  
}

.widthA .btn1 {
  background: purple;
  color: white;
  margin-left: 3%;
  font-weight: 600;
}

.user-img {
    width: 590px;
    position: absolute;
    right: 8%;
}

@media screen and (max-width: 575px) and (min-width: 105px){
  .widthA .btn1 {
    background: purple;
    color: white;
    margin-left: 0;
    font-weight: 600;
  }

  .container2 span {
    font-size: 0.9em;
    font-weight: 400px;
    color: gainsboro;
  }

    .container2 h2 {
    font-family: 'Times New Roman', Times, serif;
    color: rgb(20, 19, 19);
  }

  .container2 {
    width: 100%;
    height: auto;
    padding: 10px;
    display: flex;
    /* background:  blue; */
  }

  .widthA h1 {
    font-size: 55px;
    line-height: 60px;
    color: white;
  }

  .user-img {
    width: 300px;
    position: relative;
    right: 10px;
    top: 40px;
  }

  .widthA .btn1 {
    background: purple;
    color: white;
    margin-left: 0px;
    font-weight: 400;
  }

  .container1 {
    width: 100%;
    height: 100%;
    /* padding: 0 8.5%; */
    position: relative;
  }

  .widthA a {
    margin-top: 30px;
    display: inline-block;
    border-radius: 14px;
    border: 2px solid purple;
    color: white; 
    padding: 5px 10px;
    text-decoration: none;
  
  }

    .widthA p {
    font-size: 1.1em;
    font-family: 'Times New Roman', Times, serif;
    color: gainsboro;
    letter-spacing: 1px;
  }
}

/* @media only screen and (min-width: 768px) {
  
} */

@media screen and (max-width: 1070px)  and (min-width: 805px) {
    .user-img {
    width: 440px;
    height: 450px;
    position: absolute;
    right: 5px;
  }
}

@media screen and (max-width: 804px) and (min-width: 576px) {
    .user-img {
    width: 480px;
    position: absolute;
    right: 5px;
    top: 500px;
  }

   .container2 {
    width: 350px;
    height: auto;
    padding: 10px;
    display: flex;
    /* background:  blue; */
  }
}

</style>