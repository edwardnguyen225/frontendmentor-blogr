<script setup lang="ts">
import InfoItem from './InfoItem.vue'
</script>

<template>
  <section class="section-container">
    <picture>
      <source
        srcset="../assets/images/illustration-laptop-desktop.svg"
        media="(min-width: 1440px)"
      />
      <img
        class="illustration"
        alt="Laptop and mobile phone displaying a blog post"
        src="../assets/images/illustration-laptop-mobile.svg"
        width="328"
        height="326"
      />
    </picture>

    <div class="content">
      <InfoItem>
        <template #heading>Free, open, simple</template>
        <p>
          Blogr is a free and open source application backed by a large community of helpful
          developers. It supports features such as code syntax highlighting, RSS feeds, social media
          integration, third-party commenting tools, and works seamlessly with Google Analytics. The
          architecture is clean and is relatively easy to learn.
        </p>
      </InfoItem>

      <InfoItem>
        <template #heading>Powerful tooling</template>
        <p>
          Batteries included. We built a simple and straightforward CLI tool that makes
          customization and deployment a breeze, but capable of producing even the most complicated
          sites.
        </p>
      </InfoItem>
    </div>
  </section>
</template>

<style scoped>
.section-container {
  margin: 0 24px;
  display: flex;
  flex-direction: column;
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
    margin: 300px auto 200px;
    max-width: 1440px;

    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 40px;
  }

  picture {
    width: 50%;
    max-width: 540px;
  }

  .illustration {
    flex: 1 1 auto;
    margin: 0;
    width: auto;
    width: 100%;
    max-width: 784px;
    height: auto;
    margin-bottom: 0;
    position: relative;
    left: -50%;
    transform: scale(2);
  }

  .content {
    width: 50%;
    max-width: 540px;
    gap: 40px;
  }
}
</style>
