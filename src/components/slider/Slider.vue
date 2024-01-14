<template>
  <div class="slider-container">
    <div class="slider-line">Lorem ipsum dolor sit amet consectetur</div>
    <div class="slider-content visible" id="slide1">
      <img src="https://placekitten.com/800/400" alt="Slide 1" />
      <div class="text-container">
        <div class="left-part">
          <div>
            <h2>
              Unique Visual Solutions
            </h2>
          </div>
        </div>
      </div>
    </div>

    <div class="slider-content visible" id="slide2">
      <img src="https://placekitten.com/800/401" alt="Slide 1" />
      <div class="text-container">
        <div class="left-part">
          <div>
            <h2>
              Unique Visual Solutions
            </h2>
          </div>
        </div>
      </div>
    </div>
    <div class="slider-content visible" id="slide3">
      <img src="https://placekitten.com/800/402" alt="Slide 1" />
      <div class="text-container">
        <div class="left-part">
          <div>
            <h2>Unique Visual Solutions</h2>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>
export default {
  mounted() {
    let currentIndex = 0;
    const slides = document.querySelectorAll(".slider-content");

    function showSlide(index) {
      slides.forEach((slide) => {
        slide.classList.remove("visible");
      });
      slides[index].classList.add("visible");
    }

    function nextSlide() {
      currentIndex = (currentIndex + 1) % slides.length;
      showSlide(currentIndex);
    }
    showSlide(currentIndex);
    setInterval(nextSlide, 3000);
  },
};
</script>
  
  <style scoped>
h2 {
  font-size: 62px;
  font-weight: 700;
  color: white;
  letter-spacing: 1px;
  padding: 0;
  margin: 0;
  text-align: start;
}
.slider-container {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.slider-line {
  position: absolute;
  text-wrap: wrap;
  font-size: 42px;
  font-weight: 700;
  letter-spacing: 2px;
  color: white;
  width: 100%;
  bottom: 100px;
  right: 0;
  z-index: 99;
  width: 100%;
  height: 2px;
  animation: slideLine 10s linear infinite;
}
.slider-content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 1s ease-in-out;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.visible {
  opacity: 1;
}

.slider-content img {
  width: 100%;
  height: 100vh;
}

.text-container {
  position: absolute;
  width: 100%;
  height: 600px;
  left: 0px;
  top: 0;
  display: flex;
  justify-content: start;
  opacity: 0;
  transform: translateX(0px);
  transition: opacity 1s ease-in-out, transform 1s ease-in-out;
}

.text-container .left-part {
  width: 40%;
  height: 100%;
  height: auto;
  display: flex;
  justify-content: start;
  align-items: center;
  padding: 10px;
}

.visible .text-container {
  opacity: 1;
  transform: translateX(100px);
}

@keyframes slideLine {
  from {
    left: 100%;
  }

  to {
    left: -100%;
  }
}
</style>
  