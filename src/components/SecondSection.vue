<template>
  <section class="section-container">
    <img class="illustration" src="../assets/images/illustration-phones.svg" alt="phones" />
    <div class="content-container">
      <div class="content">
        <h2 class="title">State of the Art Infrastructure</h2>
        <p>
          With reliability and speed in mind, worldwide data centers provide the backbone for
          ultra-fast connectivity. This ensures your site will load instantly, no matter where your
          readers are, keeping your site competitive.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section-container {
  margin-top: 100px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.illustration {
  width: 100%;
  max-width: 328px;
  z-index: 1;
}

.content-container {
  position: relative;
  top: -200px;
  overflow: hidden;

  background: linear-gradient(135deg, #2d2e40 0%, #3f4164 100%);
  border-radius: 0px 100px;

  color: white;
}

.content {
  width: 100vw;
  height: 100%;
  padding: 221px 24px 109px;
  text-align: center;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;

  background-image: url(../assets/images/bg-pattern-circles.svg);
  background-size: 160%;
  background-position-y: -250px;
  background-position-x: -100px;
  background-repeat: no-repeat;
}

.content h2 {
  font-weight: 600;
  font-size: 40px;
  line-height: 61px;
  letter-spacing: -1.2px;
}

.content p {
  letter-spacing: 0.5px;
}

@media (min-width: 1280px) {
  .section-container {
    margin-top: 300px;
    padding: 0 24px;

    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 40px;

    background-image: url(../assets/images/bg-pattern-circles.svg),
      linear-gradient(to bottom, #2c2d3f, #3f4164);
    background-size: 160%;
    background-repeat: no-repeat;
    background-position-x: -750px;
    background-position-y: 90%;
    max-height: 400px;
    border-top-right-radius: 100px;
    border-bottom-left-radius: 100px;
    color: white;
  }

  .illustration {
    width: 50%;
    max-width: 540px;
    flex: 1 0 auto;
  }

  .content-container {
    position: static;
    width: 50%;
    flex: 1 0 auto;
    max-width: 540px;
    background: none;
    border-radius: 0;
  }

  .content {
    padding: 0;
    width: 100%;
    background: none;
    text-align: left;
    align-items: start;
  }
}
</style>
