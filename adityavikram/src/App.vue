<script setup>
import Testimonial from "./components/Testimonial.vue";
const images = [
  [
    {
      title: "MADE FOR YOU YOU WERE MADE",
      text: "PISTONS",
      src: "https://thumbs.dreamstime.com/z/tree-golf-course-sunset-time-40067260.jpg?w=992",
    },
    {
      title: "YOU WERE MADE TOMAKE AN IMPACT.",
      text: "Welcome",
      src: "https://cdn.pixabay.com/photo/2015/03/22/17/28/rings-684944_1280.jpg",
    },
  ],
  [
    {
      title: "til1",
      text: "Nature",
      src: "https://cdn.pixabay.com/photo/2016/08/12/14/25/abstract-1588720_1280.jpg",
    },
    {
      title: "til1",
      text: "God is Great",
      src: "https://cdn.pixabay.com/photo/2012/11/13/17/44/e-mail-65927_1280.jpg",
    },
  ],
  [
    {
      title: "til1",
      text: "Friendship",
      src: "https://media.istockphoto.com/id/1408387701/photo/social-media-marketing-digitally-generated-image-engagement.webp?b=1&s=612x612&w=0&k=20&c=GZCD21X5437zQJjw40Qnda-pMWLY_x0zzeQSv-rEe_I=",
    },
    {
      title: "til1",
      text: "BrotherHood",
      src: "https://thumbs.dreamstime.com/z/golf-course-tree-sand-bunker-panorama-44431428.jpg?w=992",
    },
  ],
  [
    {
      title: "til1",
      text: "Beautfull",
      src: "https://thumbs.dreamstime.com/z/tree-golf-course-sunset-time-40067260.jpg?w=992",
    },
    {
      title: "til1",
      text: "Nature ",
      src: "https://thumbs.dreamstime.com/z/golf-course-tree-sand-bunker-panorama-44431428.jpg?w=992",
    },
  ],
  // Add more image pairs as needed
];
</script>

<template>
  <Navbar style="width: 100%; z-index: 9; margin-top: -10px; position: fixed">
    <div>
      <nav class="navbar">
        <div class="container">
          <!-- <div class="navbar-brand">
          <router-link to="/" class="navbar-item"> My App </router-link>
        </div> -->
          <div class="navbar-menu">
            <div class="navbar-end">
              <b>PISTON</b>
              <div class="tab">
                <router-link to="/new" class="navbar-item">NEW</router-link>
                <router-link to="/brands" class="navbar-item"
                  >BRANDS</router-link
                >
                <router-link to="/collections" class="navbar-item"
                  >COLLECTIONS</router-link
                >
                <router-link to="/accessories" class="navbar-item"
                  >ACCESSORIES</router-link
                >
                <router-link to="/about" class="navbar-item">ABOUT</router-link>
              </div>
              <div class="thirdpart">
                <div class="icon">
                  <img
                    name="cart-icon"
                    id="image"
                    src="https://cdn-icons-png.flaticon.com/512/263/263142.png"
                  />
                  <img
                    name="search-icon"
                    id="image"
                    src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIAAAACACAMAAAD04JH5AAAAZlBMVEX///8AAADq6uo6OjpUVFTm5ubj4+Pu7u42Njbf39/5+fnLy8ucnJwtLS3z8/PW1tZ4eHiysrJPT08gICBjY2NeXl6/v78LCwsoKCirq6ujo6ODg4NwcHBqampFRUVKSkoXFxeRkZHawpUlAAAEvElEQVR4nO1b65qiMAzlKnItCHIREXn/l9yhKaisaNPGYff7PH+HktienKQhYxhffPHF/4bE81nI2M4Lft20FZ5S27zh6gwN+y03knCwK/MJ8qLxP249YA+/fImrc3I/aj87vLAukH5sG4Lm+miqii+941zsfOFCEX7EfnNnp3LajN3In+zK6Ly/c+FIvwu+M7897krrCeM9djrM5LxGxDFxms07mbf+GBvmbbpQboI1//wze/NokNXTsycy+yWO4NkUqEVCY7+ZNlWW3EkkVtgkxzCIt2FoxS6CiwQepOJV7w5/AeF2pS0Jwv4RfZwhjQfih6QKUc1qpa17hAj/QWmxD9pYv9CNdyh17BuGG4N0Kdu39Oz/qDN4kKqud/SW/2AHypyprQYCHLWySsjTU26prPWBxJpyCqJYqCyFA9AKohEgJCV+IWSASNe+kXAi2uiNDDh9LgRlRamWm2EDSIq7fnzTHrsFV90IvMGvFA4z4xtAVFW147ti1GkGvP4/09gXW4BSI0YTghPOnNCYFaleElmCYQ80sTUU/Bl6JA15NRNr5PEleFAf5GnI66COzr7h8jOQT0m2onyvo0adqTWGTaWUQtcwoHSNU8AhvV2GKBLwSqSltG+4Y27LZbsnKXEQjrAxyoZ6WBIdhtc8ZghVYMSAkKJkfLYi7nA0CF55XAdp7UNdJKltPjp3SSBEpDeeu3piBzAvxTiLc0ByW9nHHJDcAYyz0sBs647fJIgdKBE3NB6G+ScckKxyA66ERD2+CREmwfFLyY7WAZ7gGsmHHfKCSLxT9qaHSRySCGJMYd5QXosA/nise9kMy4VA+mkpZKg6G3oDpBVJhzvVYnycrt1viBpH/ifBRYbQPhfiXF5aOGUqwjNoUdcCQ0Steod0iaTCKgu/GeRkZSE0nDAr4DJJdTWAfguu4cSluyZyABp1uIaTT7kFPaIWmMGlAN/ffAa1liN88qHISBAC+Hb1ESleq0gVGDCCixFBbQoMVLnsQ6dfV43EdyOV1BpclMizwFEjnCAU9WjAk4Byww0+GtUaLWs4RvXapoD1yoMx4ru7+ilCy1a5Zyrs6+gpxKIZK10SxBSBXrsNWv1mrrCL4ru7Wet1POHLo1lhRdk9mhNsvUtWKKaXUlRiKmPzBltvvEvMAZixfEmVTNvf1losFvCmIZ5eUhGaaZ4pMyyIo6tm53v6QVX73oWg7KedHzV0Bx7sNS/b2TQgVb2ZZEqaed6ug33fxRRMNKxiplTfrHIqbG+TjrP8WBUFD354fTfIWA/h0onAz7o74rd35iwxZ6frQXK6H9jL7W5oypAxFpZllDrx/axh8UgVIh6MI1r30b2Kv+cZiXhgjLNyl3fmnw68efA3kp6DH63Plebpmlh5RDzgCKwsPSznSE27i9gLtRY8UMurz5xwWRm1ndNfeqc4t03ov/ttuz0VD1Qx8YD0eyQKVkzIAyVQ80DBAzI9UIUYj7M35IGYctzOAxGN9WeH8F/B31wP3GpzHoCMqw0ZkmB7HmyfF1yonzRvLDoQeqB5b9SBC3lBeqyEHiIzbcmDfHMe5P8ID6inRRAQPPj8f6itwq23rdFAD2g/EqPxtp7/4osvfhF/AFiELjOq4t87AAAAAElFTkSuQmCC"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </nav></div
  ></Navbar>
  <Imagerow>
    <div class="out">
      <div
        v-for="(imagePair, index) in images"
        :key="index"
        class="image-container"
        :style="{ zIndex: index }"
      >
        <div class="image-wrapper">
          <img :src="imagePair[0].src" :alt="'Image ' + index" />
          <div class="image-text">
            <CurvedText :text="imagePair[0].title" />
            <p>{{ imagePair[0].text }}</p>
          </div>
        </div>
        <div class="image-wrapper">
          <img :src="imagePair[1].src" :alt="'Image ' + index" />
          <div class="image-text">
            <CurvedText :text="imagePair[1].title" />
            <p>{{ imagePair[1].text }}</p>
          </div>
        </div>
      </div>
      <div class="image-container">
        <img
          src="https://cdn.pixabay.com/photo/2022/09/27/10/27/brain-7482511_1280.jpg"
          style="z-index: 7; width: 100%"
        />
      </div>
    </div>
  </Imagerow>
  <About style="z-index: 5">
    <div class="out">
      <div class="image-container" style="z-index: 9">
        <div class="image-wrapper">
          <img
            src="https://thumbs.dreamstime.com/z/golf-course-tree-sand-bunker-panorama-44431428.jpg?w=992"
            alt="Image 1"
          />
        </div>
        <div class="about">
          <div
            style="
              display: flex;
              justify-content: center;

              width: 100%;
              height: 100%;
            "
          >
            <div style="background-color: white; padding: 15%">
              <h1>About PISTONS</h1>
              <p>
                 Lorem ipsum dolor sit amet consectetur adipisicing elit. Non
                inventore Lorem ipsum dolor sit, amet consectetur adipisicing
                elit. Voluptas unde maxime quibusdam ipsum laudantium ad beatae
                ab odio doloremque, veritatis cumque voluptatem voluptatum
                dolorum natus error blanditiis est corporis temporibus? possimus
                eligendi, sequi quia ducimus vitae nihil recusandae tenetur
                laboriosam praesentium quam necessitatibus ut natus, iusto
                quibusdam officia nostrum consequuntur.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div style="z-index: 10">
      <div class="testimonials">
        <h1>TESTIMONIAL</h1>
      </div>
      <div class="test">
        <Testimonial />
        <Testimonial />
        <Testimonial />
        <Testimonial />
      </div>
    </div>
  </About>
</template>

<style scoped>
/* .test {
  display: flex;
  flex-direction: row;
}
.testimonials {
  display: flex;
  justify-content: center;
} */
.logo {
  display: block;
  margin: 0 auto 2rem;
}
.navbar-end {
  display: flex;
  justify-content: space-between;
}
.icon {
  /* display: flex; */
  display: flex;
  flex-direction: row;
  align-items: end;
  width: 20px;
}
.tab {
  /* font-size: larger; */
  font-weight: 800;
  margin-right: 11%;
  margin-top: 2%;
  margin-bottom: 2%;
  
  
}

.thirdpart {
  margin-right: 6%;
  margin-left: 11%;
  margin-top: 2%;
  margin-bottom: 2%;
  
}
#image[name="search-icon"] {
  margin-left: 10px; /* Adjust the margin as needed */
}
/* Add your CSS styles here */
.navbar {
  background-color: white;
  color: #333; /* Text color */
}
#image {
  width: 100%;
  /* margin-left: 10%; */
}

b {
  font-size: xx-large;
  margin-left: 1.5%;
  margin-right: 11%;
  margin-top: 2%;
  margin-bottom: 2%;
}
.navbar-brand {
  color: #333; /* Text color */
}

.navbar-item {
  color: #333; /* Text color */
  margin: 1.5%; /* Add spacing between items */
  text-decoration: none;
  text-align: center;
}

.navbar-item:hover {
  cursor: pointer;
  text-decoration: underline;
}
.semicircle-text {
  position: absolute;
  bottom: 20px;
  left: 20px;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 20px 40px;
  font-size: 16px;
  z-index: 10;
  margin: 30px;
  transform: rotate(-180deg);
  border-radius: 50%;
  text-align: center;
}

.image-container {
  width: 100%;
  display: flex;
  justify-content: space-between;
  top: 12%;
  position: sticky;
  height: 500px;
}
.image-text {
  position: absolute;
  bottom: 20px; /* Adjust the distance from the bottom as needed */
  left: 20px; /* Adjust the distance from the left as needed */
  /* background-color: rgba(0, 0, 0, 0.7); Background color and opacity */
  color: white; /* Text color */
  padding: 10px; /* Padding around the text */
  font-size: 20px; /* Font size */
  font-weight: 100;
  z-index: 10; /* Ensure it's above the image */
  margin: 200px;
}
.image-wrapper {
  flex: 1;
  max-width: 50%;
  padding: 0px;
  position: relative;
}

img {
  max-width: 100%;
  height: 90%;
}

.out {
  margin-bottom: 0px;
  /* height: 500px; */
  /* overflow-y: visible; */
}
/* ///////////////////////////////////// about*/
.about {
  display: flex;
  align-items: center;
  width: 50%;
}

.test {
  display: flex;
  flex-direction: row;
}
.testimonials {
  display: flex;
  justify-content: center;
}
.image-wrapper {
  flex: 1;
  max-width: 50%;
  padding: 0px;
}

img {
  max-width: 100%;
  height: 90%;
}
.out {
  height: 3000px;
  /* overflow-y: scroll; */
  overflow-y: visible;
}
</style>
