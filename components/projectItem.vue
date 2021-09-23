<template name="projectItem">
    <div class="project--style">
        <h3>{{item.title}}</h3>
        <img :src="item.url">
    </div>
</template>
<script>


import projectItem from './projectItem.vue'
export default  {
    components:{
        projectItem
    },
    props: {
        item: Object
    }
}
</script>
<style lang="scss">
$bgcolor: #011d57;
$headline: #e5e5e5;
$textcolor: #CFD5E3;
$highlight: #C28A8A;
$stroke: #02112E;
$secondary: #9BB3A3;
$font: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

    .project--style{
        display: flex;

        width: 300px;
        height: 150px;
        
        border-radius: 20px 0 20px 0;
        border: 1px solid black;
        box-shadow: -15px 15px $stroke;

        
        background-size: cover;
        position: relative;
    }
</style>