<template name="component-name">
    <div>
        <NavBar/>
        <header class="service-header">
            <h1 ref="headline">{{title}}</h1>
            <ScrollMouse/>
        </header>
        <main class="service">
            <section class="service-intro">
                <div>
                    <p ref="text">
                        I help you go through the process of designing and building a website that match you expectatives.
                    </p>
                <div ref="cta" class="service-button-area">
                    <CtaButton  class="btn" btntext="Get in touch!" page="#contact"/>
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
            <section id="contact" class="services_form">
                <ContactForm/>
            </section>
            <footer>
                <PageFooter/>
            </footer>
        </main>
    </div>
</template>

<script>

import NavBar from '../components/NavBar.vue'
import CtaButton from '../components/CtaButton.vue'
import ServiceDetails from '../components/ServiceDetails.vue'
import PageFooter from '../components/PageFooter.vue'
import ServiceSvg from '../components/ServiceSvg.vue'
import ScrollMouse from '../components/ScrollMouse.vue'
import ContactForm from '../components/ContactForm.vue'

import { gsap } from "gsap";
export default {
    components:{
    NavBar,
    CtaButton,
    ServiceDetails,
    PageFooter,
    ServiceSvg,
    ScrollMouse,
    ContactForm
  },
  data (){
      return{
          title: 'Build a good website and thank me later.'
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

    margin-top: 350px;
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

.services_form{
    padding: 30px;
    margin-bottom: 50px;
}

@media (min-width: $extra-large-screen){
    .service-header{
        h1{
            font-size: 5em;
        }
    }

    .service-intro{
        p{
            font-size: 2.5em;
        }
    }

    .services-details{
        .backlit{
            width: 1500px;
            height: 350px;
        }
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
            font-size: 1.8rem;
            width: 20ch;
        }
    }
    

    .service-intro{
        display: inline;
        position: relative;
        
        div{
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        p{
            font-size: 1em;
            margin: 0;
            position: relative;
            right: 50px;
            width: 30ch;
        }
    }

    .services{
        position: relative;
        top: 120px;
        
    }

    .services-details{
        display: inline;
        margin: 0;
    }

    .service-button-area{
        position: relative;
        right: 150px;
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