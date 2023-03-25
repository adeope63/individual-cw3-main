<script>
export default {
    props:['sortedLessons'],
    methods:{
        addToCart(lesson){
            this.$emit('addToCart',lesson)
        }
    }
}
</script>

<template>
         <div v-for="(lessons, index) in sortedLessons" :key="`lesson--${index}`" class="lessons__item col-md-2 py-1 border">
                        <img class="card-img-top image" v-bind:src="lessons.imgURL" width="200" height="250" >
                        <div class="card-body">       
                            <h2 class="card-title"><p> {{ lessons.subject }}</p></h2>
       
                            <p class="card-text">Location: {{ lessons.location }}</p>
                            <p class="card-text">Price: {{ lessons.price }}</p>
                            <div>
                            
                            <p class="card-text">Spaces: {{lessons.space}}</p>
                            <button class="btn btn-dark" v-on:click='addToCart(lessons)' :disabled="!lessons.space">Add to cart</button>

                        </div>
                    </div>
                    </div>

</template>

<style>
    .border{
        
        border: 1px solid black;
        margin: 20px;
    }
    .image{
        height: 150px;
        width: auto;
    }
</style>