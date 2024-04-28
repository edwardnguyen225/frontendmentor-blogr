<script setup lang="ts">
import InfoItem from './InfoItem.vue'
</script>

<template>
  <section class="section-container">
    <h2>Designed for the future</h2>

    <div class="content-container">
      <div class="img-container">
        <picture>
          <source
            srcset="../assets/images/illustration-editor-desktop.svg"
            media="(min-width: 1440px)"
          />
          <img
            class="illustration"
            src="../assets/images/illustration-editor-mobile.svg"
            width="326"
            height="326"
          />
        </picture>
      </div>

      <div class="content">
        <InfoItem>
          <template #heading>Introducing an extensible editor</template>
          <p>
            Blogr features an exceedingly intuitive interface which lets you focus on one thing:
            creating content. The editor supports management of multiple blogs and allows easy
            manipulation of embeds such as images, videos, and Markdown. Extensibility with plugins
            and themes provide easy ways to add functionality or change the looks of a blog.
          </p>
        </InfoItem>

        <InfoItem>
          <template #heading>Robust content management</template>
          <p>
            Flexible content management enables users to easily move through posts. Increase the
            usability of your blog by adding customized categories, sections, format, or flow. With
            this functionality, you're in full control.
          </p>
        </InfoItem>
      </div>
    </div>
  </section>
</template>

<style scoped>
.section-container {
  margin: 0 24px;
  display: flex;
  flex-direction: column;
}

.section-container h2 {
  text-align: center;
  margin-bottom: 40px;
  font-size: 28px;
  line-height: 43px;
  letter-spacing: -0.84px;

  color: #1f3e5a;
}

.img-container {
  width: 100%;
}

.illustration {
  margin: 0 auto;
  width: 100%;
  height: auto;
  margin-bottom: 46px;
}

.content {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

@media (min-width: 1280px) {
  .section-container {
    margin: 0 auto;
    max-width: 1110px;
  }

  .section-container h2 {
    margin-bottom: 93px;
  }

  .content-container {
    display: flex;
    gap: 40px;
  }

  .img-container {
    position: relative;
    width: 50%;
    order: 1;
  }

  .illustration {
    position: absolute;
    flex: 1 1 auto;
    width: 150%;
    height: auto;
    right: -50%;
    top: -40%;
  }

  .content {
    width: 50%;
    gap: 40px;
  }
}

@media (min-width: 1440px) {
  .illustration {
    right: -80%;
    top: -50%;
  }
}
</style>
