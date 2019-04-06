<template>
  <div class="home">
    <div @scroll="handleSCroll" class="top-bar">
      <img id="idea-logo" alt="Vue logo" src="../assets/Clim_Logo_2.svg" />
    </div>
    <section id="intro-section">
      <h2>CLIMATE <span style="color: #FA9917;">INSIGHT</span></h2>
      <img id="owl" src="../assets/owl.svg">
      <p>We provide a playful learning experience, which makes children understand a 
        complex matter like climate change... and learn how to act on it.</p>
    </section>
    <section class="game-intro-section">
      <h2>GAMES TO MAKE A CHANGE</h2>
      <p>We provide a game with an alternative approach where your actions which are totally normal in today's society does not result in a "happily ever after" but gives you a more realistic result.</p>
      <img @scroll="scrolltornado" class="moving-tornado" src="../assets/tornado_smile.svg">
    </section> 

    <section id="tree-cut-game-section">
       <iframe class="UnityObject" src="https://c.simmer.io/static/unityFrame/index.html?url=https%3A%2F%2Fsimmercdn.com%2Funity%2Fx74PHp5BitgePJQIfb9V1JEKMju2%2Fcontent%2F5fb82cda-a278-f41b-d3b2-fe483e608d70&imagePath=screens/0.png" style="width:560px;height:420px;border:0"></iframe>
        <div>
            <h2>The Amazon Forest</h2>
            <p>You are a grumpy lumberjack that works with harvesting trees from ancient forests. 
              You are currently on a holiday road trip to an unknown destination. What happens next?</p>
            <img @scroll="scrolltree" class="falling-tree" src="../assets/tree.svg">
        </div>

    </section>

    <section id="electricity-game-section">

      <div>
            <h2>Disco Light</h2>
            <p>The electricity bill is going through the roof. You must keep the lights off as much as possible otherwise you won't be able to afford that new pair of shoes next month.
              Turn OFF the light!</p>
            <div @scroll="scrollamp" class="lightbulb"></div>
      </div>

      <iframe id="UnityObject_2" src="https://c.simmer.io/static/unityFrame/index.html?url=https%3A%2F%2Fsimmercdn.com%2Funity%2Fx74PHp5BitgePJQIfb9V1JEKMju2%2Fcontent%2F366f9683-e048-6b5b-618f-eca6579dcd5f&imagePath=screens/0.png" style="width:560px;height:400px;border:0"></iframe>
    </section>
    <section id="recycle-game-section">

      <iframe class="UnityObject" src="https://c.simmer.io/static/unityFrame/index.html?url=https%3A%2F%2Fsimmercdn.com%2Funity%2Fx74PHp5BitgePJQIfb9V1JEKMju2%2Fcontent%2F207f45c7-aa27-285e-cd3e-61d3e451b40d&imagePath=screens/0.png" style="width:560px;height:420px;border:0"></iframe>
      <div>
            <h2>Throw it in the Bin!</h2>
            <p>It is time to recycle!</p>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: "home",
  data () {
  return {
    scrolled: false
  };
},
methods:{
      handleSCroll (event) {
        let header = document.querySelector(".top-bar");
        let logo = document.querySelector("#idea-logo");
        if (window.scrollY > 80 && !header.className.includes('top-bar-scrolled') && !logo.className.includes('smaller-logo')) {
        header.classList.add('top-bar-scrolled'); 
        logo.classList.add('smaller-logo'); 
        } else if (window.scrollY < 80) {
          header.classList.remove('top-bar-scrolled');
          logo.classList.remove('smaller-logo'); 
        }
      },
      scrolltornado (event) {
        let tornado = document.querySelector(".moving-tornado");
        if (window.scrollY >550 && !tornado.className.includes('updated-position')) {
        tornado.classList.add('updated-position'); 
        } else if (window.scrollY < 550) {
          tornado.classList.remove('updated-position');
        }
      },
      scrolltree (event) {
        let tree = document.querySelector(".falling-tree");
        if (window.scrollY >1130 && !tree.className.includes('falling-move')) {
        tree.classList.add('falling-move'); 
        } else if (window.scrollY < 1130) {
          tree.classList.remove('falling-move');
        }
      },
      scrollamp (event) {
        let lamp = document.querySelector(".lightbulb");
        if (window.scrollY > 1330 && !lamp.className.includes('light')) {
        lamp.classList.add('light'); 
        } else if (window.scrollY < 1330) {
          lamp.classList.remove('light');
        }
      }
    },
    created () {
      window.addEventListener('scroll', this.handleSCroll);
      window.addEventListener('scroll', this.scrolltornado);
      window.addEventListener('scroll', this.scrolltree);
      window.addEventListener('scroll', this.scrollamp);

    },
    destroyed () {
      window.removeEventListener('scroll', this.handleSCroll);
      window.removeEventListener('scroll', this.scrolltornado);
      window.removeEventListener('scroll', this.scrolltree);
      window.removeEventListener('scroll', this.scrollamp);
    } 
};
</script>

<style lang="scss">

body{
  margin: 0 !important;
}

.top-bar{
  position: sticky;
  top: 0;
  display: inline-block;
  width: 100vw;
  height: 80px;
  z-index: 999;
  background-color: #fff;

  }

  .top-bar-scrolled{
    -webkit-box-shadow: 0px 10px 5px 0px rgba(0,0,0,0.3);
    -moz-box-shadow: 0px 10px 5px 0px rgba(0,0,0,0.3);
    box-shadow: 0px 10px 5px 0px rgba(0,0,0,0.3);
  }

#idea-logo{
    position: absolute;
    left: 20px;  
    top: 0;
    box-sizing: border-box;
    width: 10%;
    margin: 20px 0;
    transition:  all ease-in .3s;
  }

  .smaller-logo{
    width: 7% !important;
  }

#UnityObject{
    display: block;
    margin: 0 30px
  }

#intro-section{
  position: relative;
  left: 0;
  width: 100vw;
  height: 400px;
  display: block;
  padding: 130px 50px;

  #owl{
    position: absolute;
    right: 200px;
    top: 125px;
    box-sizing: border-box;
    width: 10%;
    z-index: 2;
  }

  h2{
    font-family: "Roboto", sans-serif;
    font-size: 72px;
    font-weight: 700;
    color: #333;
    text-align: left;
    margin: 20px 0 10px 0;
    border-bottom: solid 2px #333;
    padding: 10px 0;
  }

  p{
    font-family: "Roboto", sans-serif;
    font-size: 20px;
    font-weight: 400;
    color: #333;
    text-align: left;
    width: 600px;
  }
}

.game-intro-section{
  position: relative;
  left: 0;
  width: 100vw;
  height: 400px;
  display: block;
  background: rgb(28,196,120);
  background: linear-gradient(90deg, rgba(28,196,120,1) 0%, rgba(28,196,186,1) 100%, rgba(0,212,255,1) 100%);
  padding: 10px;

  &::before{
    content: "";
    position: absolute;
    background: linear-gradient(90deg, rgba(28,196,120,1) 0%, rgba(28,196,186,1) 100%, rgba(0,212,255,1) 100%);
    left: 0;
    top: -50px;
    width: 100vw;
    height: 100px;
    border-radius: 50%;
    -webkit-box-shadow: 0px -10px 10px 10px rgba(110,110,110,0.2);
    -moz-box-shadow: 0px -10px 10px 10px rgba(110,110,110,0.2);
    box-shadow: 0px -10px 10px 10px rgba(110,110,110,0.2);
    z-index: -3;
  }

    &::after{
    content: "";
    position: absolute;
    background: linear-gradient(90deg, rgba(28,196,120,1) 0%, rgba(28,196,186,1) 100%, rgba(0,212,255,1) 100%);
    left: 0;
    bottom: -50px;
    width: 100vw;
    height: 100px;
    border-radius: 50%;
    -webkit-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    -moz-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    z-index: 3;
  }

  .moving-tornado{
    position: absolute;
    right: 300px;
    top: 150px;
    width: 120px;
    height: 300px;
    filter: invert(1);
    transition: all ease-in 1s
  }

  .updated-position{
    right: 120px !important;
    top: 60px !important;
  }

  h2{
    font-family: "Roboto", sans-serif;
    font-size: 52px;
    font-weight: 700;
    color: rgba(28,196,120,1);
    text-align: left;
    margin: 20px 50px;
    background-color: #fff;
    padding: 10px;
    width: 700px;
    box-sizing: border-box;
    z-index: 5;
  }

  p{
    font-family: "Roboto", sans-serif;
    font-size: 20px;
    font-weight: 400;
    color: #fff;
    text-align: left;
    width: 600px;
    margin: 20px 50px;
  }
}

#tree-cut-game-section{
  display: flex !important;
  flex-direction: row ;
  position: relative;
  left: 0;
  width: 100vw;
  height: 500px;
  display: block;
  background: #FA9917;
  padding: 100px 0;

  #UnityObject{
    display: block;
    margin: 0 30px
  }

  div {
    display: block;
    width: 20vw;
    height: inherit;
    padding: 10px;

    h2{
    font-family: "Roboto", sans-serif;
    font-size: 42px;
    font-weight: 700;
    text-align: left;
    color: #fff;
    width: 500px;
    box-sizing: border-box;
  }

  p{
    font-family: "Roboto", sans-serif;
    font-size: 18px;
    font-weight: 400;
    color: #fff;
    text-align: left;
    width: 500px;

  }
  .falling-tree{
    position: absolute;
    right: 300px;
    top: 350px;
    width: 100px;
    height: 150px;
    filter: invert(1);
    transition: all ease-in 1s
  }
  .falling-move{
    transform: rotate(-90deg);
    transform-origin: bottom ;
  }
  }

  &::after{
    content: "";
    position: absolute;
    background: #FA9917;
    left: 0;
    bottom: -50px;
    width: 100vw;
    height: 100px;
    border-radius: 50%;
    -webkit-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    -moz-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    z-index: 3;
  }
}

#electricity-game-section{
  display: flex !important;
  flex-direction: row ;
  position: relative;
  left: 0;
  width: 100vw;
  height: 500px;
  display: block;
  background: #3399FF;
  padding: 100px 0;

  #UnityObject_2{
    display: block;
    margin: 0 30px
  }

  div {
    display: block;
    width: 40vw;
    height: inherit;
    padding: 10px;

    h2{
    font-family: "Roboto", sans-serif;
    font-size: 42px;
    font-weight: 700;
    text-align: left;
    color: #fff;
    width: 500px;
    box-sizing: border-box;
    margin: 0 30px;
  }

  p{
    font-family: "Roboto", sans-serif;
    font-size: 18px;
    font-weight: 400;
    color: #fff;
    text-align: left;
    width: 500px;
    margin: 0 30px;
  }
    .lightbulb{
      display: block;
      position: absolute;
      left: 100px;
      top: 300px;
      width: 100px;
      height: 150px;
      filter: invert(1);
      transition: all ease-in 0.3s;
      background-image: url("../assets/lightbulb-off.svg");
      background-repeat: no-repeat;
      background-size: 80%;
      z-index: 5;
    }
    .light{
      background-image: url("../assets/lightbulb-on.svg");
    }
  }

  &::after{
    content: "";
    position: absolute;
    background: #3399FF;
    left: 0;
    bottom: -50px;
    width: 100vw;
    height: 100px;
    border-radius: 50%;
    -webkit-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    -moz-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    z-index: 3;
  }
}

#recycle-game-section{
  display: flex !important;
  flex-direction: row ;
  position: relative;
  left: 0;
  width: 100vw;
  height: 500px;
  display: block;
  background: #B1CDB6;
  padding: 100px 0;

  .UnityObject{
    display: block;
    margin: 0 30px
  }

  div {
    display: block;
    width: 40vw;
    height: inherit;
    padding: 10px;

    h2{
    font-family: "Roboto", sans-serif;
    font-size: 42px;
    font-weight: 700;
    text-align: left;
    color: #fff;
    width: 500px;
    box-sizing: border-box;
    margin: 0 30px;
  }

  p{
    font-family: "Roboto", sans-serif;
    font-size: 18px;
    font-weight: 400;
    color: #fff;
    text-align: left;
    width: 500px;
    margin: 0 30px;
  }
    
  }

  &::after{
    content: "";
    position: absolute;
    background: #3399FF;
    left: 0;
    bottom: -50px;
    width: 100vw;
    height: 100px;
    border-radius: 50%;
    -webkit-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    -moz-box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    box-shadow: 0px 15px 10px 10px rgba(110,110,110,0.2);
    z-index: 3;
  }
}
  
</style>
