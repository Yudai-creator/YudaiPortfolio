<template name="ProfileInfo">
    <div>
        <figure class="about-profile-pic">
            <img src="/profilepic/yudai.png" alt="profile-pic">
        </figure>
    </div>    
</template>


<script>


export default {
    
}
</script>


<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;

div{
    position: relative;
}

/*
.wrapper{
    width: 300px;
    height: 500px;
    background-color: $accent;
}
*/

.about-profile-pic{
    position: relative;
    bottom: 50px;
     
    img{
        width: 300px;
        height: 400px;
        box-shadow: 15px 15px 1px $accent;
        //animation: dropShadow .5s cubic-bezier(0.9,0.03,0.69,0.22) forwards;
    }
}



@media (max-width: $tablet-size){

    .about-profile-pic{ 
    transform: translateY(20px);
    img{
        width: 250px;
        height: 250px;
    }
    }
}

@media (max-width: $phone-size){

    div{
        position: relative;
        transform: translate(-50px, -300px);
    }
    

    .about-profile-pic{ 
    img{
        width: 200px;
        height: 200px;
    }
    }  
}

@media (max-width: 375px){
    div{
        padding: 0;
        margin-right: 20px;
    }
}


</style>