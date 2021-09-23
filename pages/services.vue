<template name="component-name">
    <div>
        <navBar/>
        <header class="service-header">
            <h1>{{title}}</h1>
            <ScrollMouse/>
        </header>
        <main class="service">
            <section class="service-intro">
                <div>
                    <p>
                        Do you want to make your business be known<br> 
                        and make more clients?
                        <br>
                        <br>
                        You have come to the right place.  
                    </p>
                <div class="service-button-area">
                    <ctaButton class="btn" btntext="Get in touch!" page="#"/>
                </div>
                </div>
                <ServiceSvg/>
            </section>
            <section class="services">
                <div class="services-details">
                    <ServiceDetails icon="/icons/bx-store-alt(1).svg" headline="Landing page that converts" text="Do you want a place to showcase your ideas, messages or services? Let's make an ideal Landing Page, built on the basis of your ideas."/>
                    <ServiceDetails icon="/icons/bx-play-circle.svg" headline="Motion Graphics and Animations" text="Make your website stand out, surprise your customers with a page full of life that will make their experience better."/>
                </div>
                <div class="services-details">
                    <ServiceDetails icon="/icons/bx-devices.svg" headline="Responsive design" text="Your website will fit perfectly in every device, making sure that your users don't miss your message."/>
                    <ServiceDetails icon="/icons/bxs-buildings.svg" headline="Setup your SPA" text="I design and build custom digital products that help businesses grow. I offer you a site perfectly adjusted to your needs"/>
                </div>
            </section>
            <footer>
                <PageFooter/>
            </footer>
        </main>
    </div>
</template>

<script>

import navBar from '../components/navBar.vue'
import ctaButton from '../components/ctaButton.vue'
import ServiceDetails from '../components/ServiceDetails.vue'
import PageFooter from '../components/PageFooter.vue'
import ServiceSvg from '../components/ServiceSvg.vue'
import ScrollMouse from '../components/ScrollMouse.vue'
export default {
    components:{
    navBar,
    ctaButton,
    ServiceDetails,
    PageFooter,
    ServiceSvg,
    ScrollMouse
  },
  data (){
      return{
          title: 'What can I do for you?'
      }
  },
  head(){
        return{
            title: 'Services'
        }
    }
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

.service-header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-left: 122px;
    margin-right: 140px;
    margin-top: 50px;
    h1{
        font-size: $headline-size;
    }
}

.service-intro{
    display: flex;
    justify-content: space-between;
    margin-left: 122px;
    margin-right: 100px;

    p{
        font-size: $text-size;
        margin-top: 50px;
        margin-bottom: 50px;
        font-weight: 600;
    }
}

.services-details{
    display: flex;
    justify-content: space-around;

    margin-top: 100px;
    margin-bottom: 100px;
    
    color: $primary;
}

@media (max-width: $tablet-landscape-size){
    .mouse-shadow{
        display: none;
    }
}

@media (max-width: $tablet-size){
    .btn{
        position: relative;
        left: 100px;
    }
}

@media (max-width: $phone-size){
    .service-header{
        margin-left: 40px;
        margin-top: 20px;
        h1{
        font-size: 2.5em;
    }
    }
    

    .service-intro{
        display: inline;
        position: relative;
        right: 30px;
        div{
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        p{
            font-size: 1em;
            margin: 0;
        }
    }

    .services{
        position: relative;
        top: 180px;
    }

    .services-details{
        display: inline;
        margin: 0;
    }

    .service-button-area{
        position: relative;
        right: 150px;
    }
}

@media (max-width: 375px){
    .service-intro{
        right: 0;
        left: 15px;
        p{
            padding: 20px;
        }

        .btn{
            position: relative;
            left: -50px;
        }
    }

    .service-button-area{
        right: 0;
        
    }

    .services-details{
        padding: 20px;
    }
}

</style>