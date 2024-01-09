<template>
    <div>
        <!-- start -->
        <p class="heading">Vue Gallery - (DEMO LIGHTSHOT)</p>
  <div class="gallery-image">
    <div class="img-box" @click="preview(image)" v-for="(image,index) in images" :key="index">
      <img :src="image.path" alt="" />
      <div class="transparent-box">
        <div class="caption">
          <p>{{ image.name }}</p>
          <p class="opacity-low">{{ image.descrip }}</p>
        </div>
      </div> 
    </div>
  </div>
        <!-- end -->
    </div>
    <p class="heading">Gallery Preview</p>
    <div style="display: flex; justify-content: center; margin-bottom: 50px;">
        <div class="gallery-image">
    <div class="img-box">
      <img :src="previewImage" alt="" />
      <div class="transparent-box">
        <div class="caption">
          <p>{{ previewName }}</p>
          <p class="opacity-low">{{ previewDescrip }}</p>
        </div>
      </div> 
    </div>
  </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    import '../assets/gallery.css'
    const previewImage = ref('https://www.guidingtech.com/wp-content/uploads//demo-mode-on-Android.jpg')
    const previewName = ref('Demo')
    const previewDescrip = ref('Demo Content')
    const images = [
        {
            path : "https://picsum.photos/350/250?image=444",
            name : 'Library',
            descrip : 'Architect Design',
        },
        {
            path : "https://picsum.photos/350/250/?image=232",
            name : 'Night Sky',
            descrip : 'Cinematic',
        },
        {
            path : "https://picsum.photos/350/250/?image=431",
            name : 'Tea Talk',
            descrip : 'Composite',
        },
        {
            path : "https://picsum.photos/350/250?image=474",
            name : 'Road',
            descrip : 'Landscape',
        },
        {
            path : "https://picsum.photos/350/250?image=344",
            name : 'Sea',
            descrip : 'Cityscape',
        },
        {
            path : "https://picsum.photos/350/250?image=494",
            name : 'Vintage',
            descrip : 'Cinematic',
        },
        
    ]

    function preview(i){
        previewImage.value = i.path
        previewName.value = i.name
        previewDescrip.value = i.descrip
    }
</script>
