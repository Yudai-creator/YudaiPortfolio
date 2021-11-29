<template name="component-name">
    <div>
        <svg id="knowledge-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1092 731">
                        <g id="knowledge">
                            <rect ref="frame" id="frame" x="120" y="108" width="910" height="490" fill="#cfd5e3" stroke="#02112e" stroke-width="5"/>
                            <rect ref="shadow" id="board-shadow" x="208" y="192" width="294" height="361" fill="#6820FF" stroke="#02112e" stroke-width="5" opacity="0.3" style="isolation:isolate"/>
                            <g ref="lines">
                                <rect id="rect-8" x="615" y="218" width="235" height="13" fill="#02112e"/>
                                <rect id="rect-7" x="615" y="242" width="342" height="13" fill="#02112e"/>
                                <rect id="rect-6" x="615" y="300" width="235" height="13" fill="#02112e"/>
                                <rect id="rect-5" x="615" y="396" width="235" height="13" fill="#02112e"/>
                                <rect id="rect-4" x="615" y="324" width="342" height="13" fill="#02112e"/>
                                <rect id="rect-3" x="615" y="348" width="342" height="13" fill="#02112e"/>
                                <rect id="rect-2" x="615" y="372" width="342" height="13" fill="#02112e"/>
                                <rect id="rect-1" x="615" y="454" width="123" height="34" fill="#6820FF"/>
                            </g>
                            
                            <rect ref="board" id="board" x="227" y="172.5" width="294" height="361" fill="#02112e"/>
                            <circle ref="circle1" id="circle-03" cx="676.5" cy="696.5" r="32" fill="#cfd5e3" stroke="#02112e" stroke-width="5"/>
                            <circle ref="circle2" id="circle-02" cx="34.5" cy="66.5" r="32" fill="#cfd5e3" stroke="#02112e" stroke-width="5"/>
                            <circle ref="circle3" id="circle-01" cx="1057.5" cy="34.5" r="32" fill="#cfd5e3" stroke="#02112e" stroke-width="5"/>
                            <g ref="code" id="code-typing">
                                <path ref="arrowShadow2" id="arrow-shadow-2" d="M451.94,404.78l61.9-53.1-61.9-53.1,18.9-16.1,80.8,69.3L470.84,421Z" fill="#e6e6e6"/>
                                <rect id="Rectángulo_55" data-name="Rectángulo 55" x="333.64" y="327.18" width="25.2" height="25.2" fill="#e6e6e6"/>
                                <rect id="Rectángulo_56" data-name="Rectángulo 56" x="408.54" y="327.18" width="25.2" height="25.2" fill="#e6e6e6"/>
                                <rect id="Rectángulo_57" data-name="Rectángulo 57" x="371.04" y="327.18" width="25.2" height="25.2" fill="#e6e6e6"/>
                                <path ref="arrowShadow1" id="arrow-shadow-1" d="M334.34,404.18l-62-53.1,61.9-53-18.9-16.2-80.7,69.2,80.8,69.3Z" fill="#e6e6e6"/>
                                <path ref="arrow2" id="arrow-2" d="M451.94,392.88l61.9-53.1-61.9-53.1,18.9-16.1,80.8,69.3-80.8,69.2-18.9-16.2Z" fill="#6820FF"/>
                                <path id="dots" d="M325.84,345.58H351v-25.2h-25.2Zm126.4-25.2H427v25.2h25.2Zm-75.8,25.2h25.2v-25.2h-25.2Z" fill="#6820FF"/>
                                <path ref="arrow1" id="arrow-1" d="M334.34,392.28l-62-53.1,61.9-53.1-18.9-16.2-80.8,69.3,80.8,69.3Z" fill="#6820FF"/>
                            </g>
                        </g>
        </svg>
                    
        <svg id="tech-blob" xmlns="http://www.w3.org/2000/svg" width="650" height="650" viewBox="0 0 1642.527 1642.418">
            <path id="blob" d="M844.273,6.776C911.3,87.4,924.249,208.689,966.9,304.739S1081.917,472.3,1082.679,543.81c1.523,71.511-68.551,143.723-111.205,239.773-43.416,95.348-58.649,215.235-126.439,260.806s-188.135,18.228-294.009-4.908C445.152,1017.046,353.75,998.818,275.3,958.155,197.606,917.491,133.624,854.393,65.835,781.48S-73.553,625.838-80.408,539.6C-88.025,452.669-30.9,362.228,46.031,303.337c76.93-58.19,172.9-85.533,258.21-157.044C388.787,75.482,462.671-38.8,560.166-75.953,656.9-113.812,778.006-73.85,844.273,6.776Z" transform="matrix(0.719, 0.695, -0.695, 0.719, 800.931, 121.325)" fill="#02112e"/>
        </svg>
    </div>
</template>



<script>


import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted(){

        const{circle1, circle2, circle3, frame, shadow, board, code, 
        lines, arrow1, arrow2, arrowShadow1, arrowShadow2 
        } = this.$refs

        const tl = new gsap.timeline({
            scrollTrigger: {
                trigger: circle1,
                toggleActions: "restart pause none none",
                start: "50px 80%"
            },
            defaults: {
                ease: 'power2',
                duration: .4
            }
        });


        tl.fromTo(frame, {scale: 0}, { scale: 1})
          .fromTo(shadow, {scale: 0}, { scale: 1})
          .fromTo(board, {scale: 0}, { scale: 1})
          .fromTo(code, {scale: 0}, { scale: 1})
          .fromTo(lines, {scale: 0}, { scale: 1})  
          .fromTo(circle1, {scale: 0}, { scale: 1})
          .fromTo(circle2, {scale: 0}, { scale: 1})
          .fromTo(circle3, {scale: 0}, { scale: 1})

          .fromTo(arrow1, {x: -8}, {duration: 1, x: 0, repeat:-1, yoyo: true, ease: 'power2'},"label")
          .fromTo(arrowShadow1, {x: -8}, {duration: 1, x: 0, repeat:-1, yoyo: true, ease: 'power2'},"label")
          .fromTo(arrow2, {x: 8}, {duration: 1, x: 0, repeat:-1, yoyo: true, ease: 'power2'}, "label")
          .fromTo(arrowShadow2, {x: 8}, {duration: 1, x: 0, repeat:-1, yoyo: true, ease: 'power2'},"label")
          
        


    }
}
</script>


<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

div{
    position: relative;
}

#knowledge-svg{
    width: 500px;
    height: 500px;

    position: absolute;
    top: 15%;
    left: 10%;
}

@media (max-width: $tablet-size){
    #knowledge-svg{
        width: 300px;
        height: 300px;
    }

    #tech-blob{
        width: 400px;
        height: 400px;
    }
}

@media (max-width: $phone-size){
    #blob{
        display: none;
    }

    #knowledge-svg{
        width: 350px;
        height: 350px;

        top: 0;
    }
}

@media (max-width: 375px){
    #knowledge-svg{
        width: 320px;
        height: 320px;
        left: 5%;
    }
}
</style>