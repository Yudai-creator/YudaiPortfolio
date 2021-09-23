<template name="RichText">
    <div>
        <h1>
          {{headline}}<span>.</span>
        </h1>
        <p>
         {{text}} 
        </p>
    </div>
</template>


<script>
import RichText from '../components/RichText.vue'
export default{
    components:{
        RichText
    },
    props: {
        headline: String,
        text: String
    }
}
</script>


<style lang="scss" scoped>
@use '~/assets/styles/global_variables/variables' as *;


    h1{
      font-size: $headline-size;
    }
    p{
      margin-top: 20px;
      color: $secondary;
      font-size: $text-size;

      font-weight: $font-bold;
    }


@media (max-width: $tablet-size){
    h1{
        font-size: 2.2em;
    }
    p{
        font-size: 1.2em;
    }
}

//phone-landscape-size
@media (max-width: $phone-landscape-size){
    h1{
        font-size: 2.5em;
    }
    p{
        font-size: 1em;
    }
}

@media (max-width: $phone-size){    
    h1{
        font-size: 2.5em;
    }
    p{
        font-size: 1em;
    }
}



</style>