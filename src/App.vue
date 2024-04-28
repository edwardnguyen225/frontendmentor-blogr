<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
    Product

    Overview
    Pricing
    Marketplace
    Features
    Integrations

    Company

    About
    Team
    Blog
    Careers

    Connect

    Contact
    Newsletter
    LinkedIn

    Login
    Sign Up

    A modern publishing platform
    Grow your audience and build your online brand

    Start for Free
    Learn More

    Designed for the future

    Introducing an extensible editor
    Blogr features an exceedingly intuitive interface which lets you focus on one thing: creating content.
    The editor supports management of multiple blogs and allows easy manipulation of embeds such as images,
    videos, and Markdown. Extensibility with plugins and themes provide easy ways to add functionality or
    change the looks of a blog.

    Robust content management
    Flexible content management enables users to easily move through posts. Increase the usability of your blog
    by adding customized categories, sections, format, or flow. With this functionality, you’re in full control.

    State of the Art Infrastructure
    With reliability and speed in mind, worldwide data centers provide the backbone for ultra-fast connectivity.
    This ensures your site will load instantly, no matter where your readers are, keeping your site competitive.

    Free, open, simple
    Blogr is a free and open source application backed by a large community of helpful developers. It supports
    features such as code syntax highlighting, RSS feeds, social media integration, third-party commenting tools,
    and works seamlessly with Google Analytics. The architecture is clean and is relatively easy to learn.

    Powerful tooling
    Batteries included. We built a simple and straightforward CLI tool that makes customization and deployment a breeze,
    but
    capable of producing even the most complicated sites.

    Product

    Overview
    Pricing
    Marketplace
    Features
    Integrations

    Company

    About
    Team
    Blog
    Careers

    Connect

    Contact
    Newsletter
    LinkedIn

  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
