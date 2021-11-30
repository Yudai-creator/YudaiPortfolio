<template name="CtaButton">
    <div ref="button" class="btn-area">
        <nuxt-link v-bind:to="page">{{btntext}}</nuxt-link>
    </div>
</template>

<script>



import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
    props: {
        btntext: String,
        page: String,          
    },
     mounted(){
        const {button} = this.$refs

        const tl = new gsap.timeline();

        //tl.fromTo(button, {boxShadow:"-1px 1px 0px #02112E", y: -5}, 
        //{scrollTrigger: {
            //trigger: button,
            //start: "top center",
            //markers: false,
            //scrub: true,
            //toggleActions: "restart pause reverse none"
        //}, 
        //duration: .5, boxShadow:"-10px 10px 0px #02112E", y: -1, ease: 'power3'})

        //tl.to(button, {duration: .5, scale: 1.1, y: -2, ease: 'power2', delay: .5})

        //tl.to(button, {duration: .2, scale: 1.2, x: 5, repeat:-1, yoyo: true})
        

        button.addEventListener("mouseover", () => {
            tl.to(button, {duration: .2, backgroundColor: "#028a94", y: -5, ease: 'power3'})
        })

        button.addEventListener("mouseout", () => {
            tl.to(button, {duration: .2, backgroundColor: "#01BCC9", y: 0, ease: 'power3'})
        })
    }
}
</script>

<style lang="scss">
@use '~/assets/styles/global_variables/variables' as *;

@mixin btn-style{
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    width: 160px;
    height: 50px;
    border-radius: 5px;
    background: $accent; 
}

.btn-area{
    @include btn-style();
    transition: all .5s ease-in-out;
    
    a{
    text-decoration: none;
    text-align: center;
    color: $secondary;
    font-family: $font;
    font-weight: 800;
    font-size: 13px;
    padding: 30px;
    }  
}





@media (max-width: $tablet-size){
    .btn-area{
        margin-left: -100px;
        margin-top: 50px;
    }
}

//phone-landscape-size
@media (max-width: $phone-landscape-size){
    .btn-area{
        width: 120px;
        height: 50px;
        a{
            font-size: 12px;
        }
    }
}

@media (max-width: $phone-size){
    .btn-area{
        width: 120px;
        height: 50px;

        a{
            font-size: 12px;
        }
    }
}



</style>