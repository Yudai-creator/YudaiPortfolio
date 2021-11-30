<template>
<div class="container">
  <NavBar/>
    <main class="home">
      <section class="home-text">
        <!--
        <h1>
          Hi and welcome<span>.</span><br>
          I'm Yudai<span>.</span>
        </h1>
        <p>
          I am a <span>Web Developer</span> focus on builidng<br>
          beautiful and functional web applications.<br> 
        </p>
        -->
        <RichText headline="Hi and welcome I'm Yudai" 
        text="I am a Web Developer focus on builidng
          beautiful and functional web applications. "/>

        <div class="home-button-area">
          <CtaButton btntext="See my work" page="/projects"/>
        </div>
      </section>

      
      <section class="home-graphics">
        <HomeSvgs/>
      </section>
    </main>
</div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import CtaButton from '../components/CtaButton.vue'

import RichText from '../components/RichText.vue'
import HomeSvgs from '../components/HomeSvgs.vue'
export default {
  components:{
    NavBar,
    CtaButton,
    RichText,
    HomeSvgs
  },
  head(){
        return{
            title: 'Yudai Creator',
            hid: 'homepage',
            name: 'homepage',
            content: 'This is Yudai Creator, welcome'
        }
  },
  transition: 'home'

}
</script>

<style lang="scss">
@use '~/assets/styles/global_variables/variables' as *;

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


  body{
    background: $primary;
    font-family: $font;
    color: $secondary;
  }

  .home{
    display: flex;
    justify-content: space-between;
  }

  .home-text{
    position: relative;
    margin-left: 120px;
    margin-top: 40px;
  }


  .home-graphics{
    position: relative;
    margin-right: 250px;

    

    z-index: -1;
    bottom: 60px;
  }

  .home-button-area{
    margin-top: 30px;
  }

  .home-enter-active, .home-leave-active{
    transition: opacity .5s;
  }

  .home-enter, .home-leave-active{
    opacity: 0;
  }



//table-landscape-size
@media (max-width: $tablet-landscape-size){
  .home-graphics{
    left: 100px;
    bottom: 40px;

    width: 400px;
    height: 400px;
  }
}  


@media (max-width: $tablet-size){
  .home{
      display: inline;
  }
  
  .home-text{
    margin-top: 80px;
  }

  .home-graphics{
    bottom: 0;
    top: 70px;
    left: 100px;
  }

  .home-button-area{
      display: flex;
      justify-content: center;
      align-items: center;
    }
}


//phone-landscape-size
@media (max-width: $phone-landscape-size){

  .home-text{
    margin-left: 40px;
    margin-top: 20px;
  }

  .home-graphics{
    bottom: 0;
  }

  .home-button-area{
      display: flex;
      justify-content: center;
      align-items: center;
    }
}  


@media (max-width: $phone-size){
    .home{
      display: inline;
    }
      
    .home-text{
      margin-left: 40px;
      margin-top: 20px;
    }

    .home-graphics{
      width: 400px;
      height: 400px; 
    }

    .home-button-area{
      display: flex;
      justify-content: center;
      align-items: center;
    }
}



</style>