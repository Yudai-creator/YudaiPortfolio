<template name="component-name">
    <div>
        <navBar/>
        <header class="service-header">
            <h1 ref="headline">{{title}}</h1>
            <ScrollMouse/>
        </header>
        <main class="service">
            <section class="service-intro">
                <div>
                    <p ref="text">
                        Do you want to make your business be known<br> 
                        and make more clients?
                        <br>
                        <br>
                        You have come to the right place.  
                    </p>
                <div ref="cta" class="service-button-area">
                    <ctaButton  class="btn" btntext="Get in touch!" page="#"/>
                </div>
                </div>
                <ServiceSvg/>
            </section>
            <section class="services">
                <div class="services-details">
                    <div class="backlit"></div>
                    <ServiceDetails icon="/icons/bx-store-alt(1).svg" headline="Landing page that converts" text="Do you want a place to showcase your ideas, messages or services? Let's make an ideal Landing Page, built on the basis of your ideas."/>
                    <ServiceDetails icon="/icons/bx-play-circle.svg" headline="Motion Graphics and Animations" text="Make your website stand out, surprise your customers with a page full of life that will make their experience better."/>
                    
                    <ServiceDetails icon="/icons/bx-devices.svg" headline="Responsive website design" text="Your website will fit perfectly in every device, making sure that your users don't miss your message."/>
                    <ServiceDetails icon="/icons/bxs-buildings.svg" headline="Setup your own SPA" text="I design and build custom digital products that help businesses grow. I offer you a site perfectly adjusted to your needs"/>
                </div>
            </section>
            <section class="services_form">
                <ContactForm/>
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
import ContactForm from '../components/ContactForm.vue'

import { gsap } from "gsap";
export default {
    components:{
    navBar,
    ctaButton,
    ServiceDetails,
    PageFooter,
    ServiceSvg,
    ScrollMouse,
    ContactForm
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
    },
  mounted(){
      const {headline, text, cta} = this.$refs

      let tl = new gsap.timeline();

      tl.from(headline, {duration: .5, stagger: .5, opacity: 0, y: -5, ease: 'power2.inOut'})
        .from(text, {duration: .5, opacity: 0, y: -5, ease: 'power2.inOut'})
        .from(cta, {duration: .5, opacity: 0, y: -5, ease: 'power2.inOut'})
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

.services{
    position: relative;
}

.services-details{
    position: relative;
    display: flex;
    justify-content: space-around;

    margin-top: 150px;
    margin-bottom: 150px;
    
    color: $primary;

    .backlit{
        position: absolute;
        background-color: $secondary;
        top: 10%;
        width: 900px;
        height: 300px;

        border-radius: 20px;
    }
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

    .backlit{
        display: none;
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

    .services_form{
        height: 50vh;
    }

    .backlit{
        display: none;
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