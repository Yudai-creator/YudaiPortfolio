<template name="ScrollMouse">
    <div>
        <div class="mouse-shadow">
                <svg id="mouse-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 82.61 109.45">
                    <g id="mouse">
                        <path id="shape" d="M41.16,109.45h.14c22.77,0,41.3-17.19,41.3-38.31V38.31C82.61,17.29,64.16.14,41.42,0h-.36C18.4.12,0,17.28,0,38.31V71.14C0,92.26,18.46,109.45,41.16,109.45ZM11.8,38.31C11.82,23.24,25,11,41.22,10.94S70.81,23.25,70.81,38.31V71.14c0,15.09-13.24,27.36-29.5,27.36h-.15c-16.46,0-29.36-12-29.36-27.36Z" fill="#01BCC9"/>
                        <path ref="wheel" id="wheel" d="M38.29,28.56h6V51.14h-6Z" fill="#01BCC9"/>
                    </g>
                </svg>
            </div>   
    </div>
</template>


<script>


import { gsap } from "gsap";
export default {
    mounted(){
        const {wheel} = this.$refs

        gsap.fromTo(wheel, {y: 8}, {duration: 1, y: -8, repeat:-1, yoyo: true, ease: 'power3'})
    }
}
</script>


<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

.mouse-shadow{
    display: flex;
    justify-content: center;
    align-items: center;

    width: 45px;
    height: 55px;

    border-radius: 50%;

    background: $secondary;
}

#mouse-svg{
    width: 35px;
    height: 35px;
}

#wheel{
    transform-origin: center;
    //animation: move 1s ease-in-out alternate infinite;
}

@keyframes move {
    0%{transform: translateY(8px);}
    100%{transform: translateY(-8px);}
}

@media (max-width: $tablet-size){
    .mouse-shadow{
        display: none;
    }
}

@media (max-width: $phone-size){
    .mouse-shadow{
        display: none;
    }
}
</style>