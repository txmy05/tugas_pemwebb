<template>
  <div id="app">
    <h1 class="title">Welcome Everybody</h1>

    <!-- Click Counter -->
    <div class="counter-section">
      <h2 class="section-title">Click Counter</h2>
      <button @click="incrementCounter" class="vintage-button">Clicked {{ counter }} times</button>
    </div>

    <!-- Box Colour Changer -->
    <div class="color-changer-section">
      <h2 class="section-title">Box Colour Changer</h2>
      <div class="box" :style="{ backgroundColor: boxColor }"></div>
      <button @click="changeColor" class="vintage-button">Change Box Color</button>
    </div>

    <!-- Image Carousel -->
    <div class="carousel-section">
      <h2 class="section-title">Music Image </h2>
      <div class="carousel-container">
        <img :src="images[currentImage]" alt="Image Carousel" class="carousel-img" />
        <div class="carousel-buttons">
          <button @click="prevImage" class="vintage-button">Previous</button>
          <button @click="nextImage" class="vintage-button">Next</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      
      counter: 0,

      
      colors: ["#8B4513", "#A0522D", "#D2B48C", "#DEB887", "#F4A460"], // Vintage colors
      boxColor: "#8B4513",

      
      images: [
        "https://i.scdn.co/image/ab67616d00001e02d0bbd3ea2ec554f17a6603cc",
        "https://i1.sndcdn.com/artworks-BrybqyhBwMXE2Ec6-zEeIrA-t1080x1080.jpg",
        "https://i.scdn.co/image/ab67616d00001e02ed3953f8af1f764a146b7583"
      ],
      currentImage: 0
    };
  },
  methods: {
    incrementCounter() {
      this.counter++;
    },

  
    changeColor() {
      const randomIndex = Math.floor(Math.random() * this.colors.length);
      this.boxColor = this.colors[randomIndex];
    },

    
    nextImage() {
      this.currentImage = (this.currentImage + 1) % this.images.length;
    },
    prevImage() {
      this.currentImage =
        (this.currentImage - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Playfair+Display:wght@400;700&display=swap');

#app {
  font-family: 'Playfair Display', serif;
  text-align: center;
  color: #5a3d2b;
  background-color: #f5f5dc; /* Vintage beige background */
  margin-top: 40px;
  padding: 20px;
  border: 2px solid #8b4513;
  box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.3);
}

.title {
  font-family: 'Cinzel', serif;
  color: #6b4226; /* Vintage brown */
  font-size: 2.5em;
}

.section-title {
  font-family: 'Cinzel', serif;
  color: #6b4226; /* Vintage brown */
  font-size: 1.8em;
}

.counter-section, .color-changer-section, .carousel-section {
  margin: 20px 0;
}

button {
  margin: 10px;
  padding: 10px 20px;
  font-size: 16px;
  font-family: 'Playfair Display', serif;
  background-color: #d2b48c; /* Tan */
  color: #5a3d2b;
  border: 1px solid #8b4513;
  cursor: pointer;
  transition: all 0.3s ease;
  border-radius: 20px; /* Rounded button */
}

button:hover {
  background-color: #8b4513; /* Darker brown on hover */
  color: #fff;
}

.box {
  width: 100px;
  height: 100px;
  margin: 10px auto;
  border: 2px solid #6b4226;
}

.carousel-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.carousel-img {
  width: 400px; /* Lebar gambar lebih besar */
  height: 300px; /* Tinggi gambar lebih besar */
  margin: 10px;
  border: 2px solid #8b4513;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}


.carousel-buttons {
  display: flex;
  gap: 10px;
}

.vintage-button {
  background-color: #f4a460; /* Sandy brown */
  color: #5a3d2b;
  border: none;
  padding: 10px 15px;
  font-size: 16px;
  font-family: 'Playfair Display', serif;
  cursor: pointer;
  transition: background-color 0.3s ease;
  border-radius: 20px; /* Rounded button */
}

.vintage-button:hover {
  background-color: #8b4513; /* Darker brown on hover */
  color: white;
}
</style>
