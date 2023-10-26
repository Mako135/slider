<template>
  <div class="gallery">
  
      <div v-for="(image, index) in images" :key="index" @click="showImage(index)">
        <div class="gallery-inner">
          <img :src="image.url" />
          <div class="image-info">
            <p><strong>{{ image.name }}</strong></p>
            <p>Автор: {{ image.author }}</p>
          </div>
        </div>
    
    </div>
    <div class="modal" v-if="shownImage !== null" @click.self="hideImage">
      <img :src="images[shownImage].url" />
    </div>
  </div>
</template>

<style>
.gallery {
  width: 1200px;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
}

.gallery img {
  
  width: 350px;
  height: 200px;
  object-fit: cover;
  cursor: pointer;

}


.gallery-inner{
  transition: 0.2s;
  height: 200px;
  display: flex;
  flex-direction: column;

}

.gallery-inner:hover {
  scale: 1.1;
  transition: 0.2s;
}

.image-info {
  display: flex;
  flex-direction: column;
  position: absolute;
  margin-top: 120px;
  align-items: start;
  padding: 20px 10px;
  width: 330px;
  background: linear-gradient(to top, rgba(0, 0, 0, 1), transparent);
}

.image-info p {
  margin: 0;
  padding: 0;
}


.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.2s;
}

.modal img {
  height: 600px;
  width: 800px;
  object-fit: cover;
}

.fadeIn{
	animation-name: fadeIn;
	-webkit-animation-name: fadeIn;	
	animation-duration: .5s;	
	-webkit-animation-duration: 0.5s;
	animation-timing-function: ease-in-out;	
	-webkit-animation-timing-function: ease-in-out;		
}
@keyframes fadeIn {
	0% {
		transform: scale(0);
		opacity: 0.0;		
	}
	60% {
		transform: scale(1.1);	
	}
	80% {
		transform: scale(0.9);
		opacity: 1;	
	}	
	100% {
		transform: scale(1);
		opacity: 1;	
	}		
}
@-webkit-keyframes fadeIn {
	0% {
		-webkit-transform: scale(0);
		opacity: 0.0;		
	}
	60% {
		-webkit-transform: scale(1.1);
	}
	80% {
		-webkit-transform: scale(0.9);
		opacity: 1;	
	}	
	100% {
		-webkit-transform: scale(1);
		opacity: 1;	
	}		
}

</style>

<script>
export default {
  data() {
    return {
      images: [
        { name: "Moto KTM", author: "Mako", url: "https://sportishka.com/uploads/posts/2021-12/1639078934_69-sportishka-com-p-chernii-mototsikl-sport-krasivo-foto-75.jpg" },
        { name: "Moto KTM", author: "Mako", url: "https://on-desktop.com/wps/2017Motocycles___Yamaha_Bikes_Yamaha_FZ-10_sports_motorcycle_on_the_track_113279_.jpg" },
        { name: "Moto KTM", author: "Mako", url: "https://images.wallpaperscraft.com/image/single/motorcyclist_biker_motorcycle_297394_3840x2400.jpg" },
        { name: "Moto KTM", author: "Mako", url: "https://images.wallpaperscraft.com/image/single/motorcyclist_biker_motorcycle_297394_3840x2400.jpg" },
        { name: "Moto KTM", author: "Mako", url: "https://images.wallpaperscraft.com/image/single/motorcyclist_biker_motorcycle_297394_3840x2400.jpg" },
        { name: "Moto KTM", author: "Mako", url: "https://images.wallpaperscraft.com/image/single/motorcyclist_biker_motorcycle_297394_3840x2400.jpg" },
      ],
      shownImage: null,
    };
  },
  methods: {
    showImage(index) {
      this.shownImage = index;
    },
    hideImage() {
      this.shownImage = null;
    },
  },
};

</script>