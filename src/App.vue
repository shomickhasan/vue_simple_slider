<script setup>
import { ref } from 'vue'
const sliderImage = ref('https://images.unsplash.com/photo-1505653553729-d8366e1e7c9e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80')
const imageID = ref(0);


const sliderImages = [
  { imageId: 1, imageUrl: 'https://images.unsplash.com/photo-1505653553729-d8366e1e7c9e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80' },
  { imageId: 2, imageUrl: 'https://images.unsplash.com/photo-1517940322679-2b003a168fd2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80' },
  { imageId: 3, imageUrl: 'https://images.unsplash.com/photo-1598387077659-74a3ea1370b5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=876&q=80' },
  { imageId: 4, imageUrl: 'https://plus.unsplash.com/premium_photo-1661353245572-5e41f6208de8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80' },
  { imageId: 5, imageUrl: 'https://images.unsplash.com/photo-1593016250787-edf25b355001?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=870&q=80' },
  // Add more images as needed with random URLs
];
function showImage(img){
    sliderImage.value=img.imageUrl
    imageID.value=img.imageId
}
</script>

<template>
   <div class="row">
        <div class="slider">
            <div class="sliderImage">
                <img :src="sliderImage" class="img-fluid main_Img" alt="">
            </div>
            <div class="sliderNav mt-2 d-flex justify-content-center">
                <ul class="dots" v-for="image in sliderImages" :key="image.imageId">
                    <li @click ="showImage(image)" :class="(imageID ===image.imageId)? 'active': '' "></li>
                </ul>
            </div>
        </div>
   </div>
</template>

<style scoped>
.main_Img{
    height: 450px;
    width: 1200px;   
}
.sliderNav{
    text-align: center;
    margin: 0 auto;
}
ul {
    position: relative;
    padding: 0;
    text-align: center;
    display: block;
}
ul li {
    position: relative;
    display: block;
    float: left;
    margin: 5px;
    width: 20px;
    height: 20px;
    cursor: pointer;
    padding: 10px;
    background-color: rgb(96, 95, 97);
    border-radius: 50%;

}
.active{
    background-color: burlywood !important;
}


</style>
