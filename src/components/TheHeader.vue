<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
let isMobile = ref(false)
let isMenuOpen = ref(false)

const closeMenu = () => {
  isMenuOpen.value = false
  activeItem.value = undefined
}

const handleResize = () => {
  isMobile.value = window.innerWidth < 1024
  closeMenu()
}

type Item = 'Product' | 'Company' | 'Connect'
const itemDictionary: Record<
  Item,
  {
    item: Item
    subItems: string[]
  }
> = {
  Product: {
    item: 'Product',
    subItems: ['Overview', 'Pricing', 'Marketplace', 'Features', 'Integrations']
  },
  Company: {
    item: 'Company',
    subItems: ['About', 'Team', 'Blog', 'Careers']
  },
  Connect: {
    item: 'Connect',
    subItems: ['Contact', 'Newsletter', 'LinkedIn']
  }
}
let activeItem = ref<Item | undefined>()
const setActiveItem = (item: Item | undefined) => {
  if (item === activeItem.value) {
    activeItem.value = undefined
    return
  }

  activeItem.value = item
}

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

onMounted(() => {
  handleResize()
  window.addEventListener('resize', handleResize)
  window.addEventListener('scroll', closeMenu)
})

onUnmounted(() => {
  window.removeEventListener('resize', handleResize)
  window.removeEventListener('scroll', closeMenu)
})
</script>

<template>
  <header>
    <div class="header-container">
      <nav class="navigation">
        <div class="left">
          <img class="logo" src="../assets/images/logo.svg" alt="logo" />
          <ul v-show="!isMobile">
            <li v-for="item in itemDictionary">
              <div
                role="button"
                @click="setActiveItem(item.item)"
                :class="{ active: activeItem === item.item }"
              >
                {{ item.item }}
                <img
                  src="../assets/images/icon-arrow-light.svg"
                  alt="arrow"
                  :class="{ 'rotate-180': activeItem === item.item }"
                />
              </div>
              <ul class="sub-items-menu" v-show="activeItem === item.item">
                <li v-for="subItem in item.subItems">
                  <a>{{ subItem }}</a>
                </li>
              </ul>
            </li>
          </ul>
        </div>
        <div class="right">
          <div class="cta" v-show="!isMobile">
            <button class="btn-ghost btn-ghost-white">Login</button>
            <button class="btn-secondary">Sign Up</button>
          </div>
          <div v-show="isMobile" class="menu-button" @click="toggleMenu">
            <img
              v-show="!isMenuOpen"
              class="hamburger"
              src="../assets/images/icon-hamburger.svg"
              alt="menu"
            />
            <img
              v-show="isMenuOpen"
              class="hamburger"
              src="../assets/images/icon-close.svg"
              alt="menu"
            />

            <div class="menu-container" v-show="isMenuOpen">
              <ul>
                <li v-for="item in itemDictionary">
                  <div role="button" @click.stop="setActiveItem(item.item)">
                    {{ item.item }}
                    <img
                      src="../assets/images/icon-arrow-dark.svg"
                      alt="arrow"
                      :class="{ 'rotate-180': activeItem === item.item }"
                    />
                  </div>
                  <ul class="sub-items-menu" v-show="activeItem === item.item">
                    <li v-for="subItem in item.subItems">
                      <a>{{ subItem }}</a>
                    </li>
                  </ul>
                </li>
              </ul>

              <div class="divider"></div>

              <div class="cta">
                <button class="btn-ghost">Login</button>
                <button class="btn-primary">Sign Up</button>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </div>

    <div class="header-content">
      <div class="content">
        <h1>
          A modern<br v-show="isMobile" />
          publishing platform
        </h1>
        <p>Grow your audience and build your online brand</p>
      </div>
      <div class="cta">
        <button class="btn-secondary">Start for Free</button>
        <button class="btn-outline">Learn More</button>
      </div>
    </div>
  </header>
</template>

<style scoped>
header {
  padding: 56px 24px 156px;
  overflow: hidden;
  background-image: url(../assets/images/bg-pattern-intro-mobile.svg),
    linear-gradient(135deg, #ff8f71 0%, #ff3e55 80%);
  background-repeat: no-repeat;
  background-size: 300%;
  background-position-x: 37%;
  background-position-y: 45%;

  border-radius: 0px 0px 0px 100px;
}

header ul {
  padding: 0;
  list-style-type: none;
  list-style-position: outside;
}

header a {
  text-decoration: none;
  cursor: pointer;
}

header a:hover {
  font-weight: 700;
}

.navigation {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.header-content {
  margin-top: 108px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
  text-align: center;
  gap: 48px;
}

.header-content .content h1 {
  font-family: 'Overpass';
  font-weight: 600;
  font-size: 36px;
  line-height: 55px;
  letter-spacing: -1.08px;
}

.header-content .content p {
  font-family: 'Overpass';
  font-style: normal;
  font-weight: 400;
  font-size: 18px;
  line-height: 28px;
}

.header-content .cta {
  display: flex;
  gap: 16px;
}

button {
  padding: 15px 16px;
  border-radius: 28px;

  font-family: 'Ubuntu';
  font-weight: 700;
  font-size: 16px;
  line-height: 18px;

  color: #ff505c;
  border: none;
  cursor: pointer;
}

.btn-primary {
  background: linear-gradient(135deg, #ff8f71 0%, #ff3e55 100%);
  color: white;
}

.btn-secondary {
  background: white;
}

.btn-secondary:hover {
  background: #ff7b86;
  color: white;
}

.btn-outline {
  background: transparent;
  border: 1px solid white;
  color: white;
}

.btn-ghost-white:hover,
.btn-outline:hover {
  background: #ffffff;
  color: #ff7b86;
}

.btn-ghost {
  background: transparent;
  font-weight: 600;
  color: #1f3e5a;
}

.btn-ghost-white {
  color: white;
}

.menu-button {
  position: relative;
}

.menu-button .hamburger {
  cursor: pointer;
}

.menu-container {
  position: absolute;
  top: calc(100% + 40px);
  right: 0;
  width: 324px;
  padding: 24px 24px 32px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 24px;

  background: #ffffff;
  box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.243444);
  border-radius: 5px;
}

.menu-container ul {
  width: 100%;
  padding: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 24px;
}

.menu-container > ul > li {
  width: 100%;
  font-family: 'Ubuntu';
  font-weight: 700;
  font-size: 18px;
  line-height: 21px;
  text-align: center;
}

.menu-container > ul > li > div {
  color: #1f3e5a;
  text-decoration: none;
}

.rotate-180 {
  transform: rotate(180deg);
}

.menu-container > ul > li > div > img {
  transition: transform 0.3s;
}

.menu-container .sub-items-menu {
  margin-top: 24px;
  padding: 18px 0 24px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 16px;

  background: #eeeef0;
  mix-blend-mode: normal;
  border-radius: 5px;
}

.menu-container .sub-items-menu a {
  font-family: 'Overpass';
  font-weight: 600;
  font-size: 16px;
  line-height: 28px;
  text-align: center;
  color: #1f3e5a;
  opacity: 0.75;
}

.menu-container .divider {
  width: 100%;
  height: 1px;
  background: #e0e0e0;
}

.menu-container .cta {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.menu-container button {
  padding: 15px 40px;
}

@media (min-width: 1024px) {
  header {
    padding-top: 63px;
    background-size: 200%;
    background-position-x: 20%;
    background-position-y: 49%;
  }

  button {
    padding: 15px 40px;
  }

  .header-container {
    max-width: 1110px;
    margin: 0 auto;
  }

  .navigation .left {
    display: flex;
    align-items: center;
    gap: 64px;
  }

  .navigation .left > ul {
    display: flex;
    align-items: center;
    gap: 32px;
  }

  .navigation .left > ul > li {
    position: relative;
    font-family: 'Ubuntu';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 18px;

    color: rgba(255, 255, 255, 0.75);
  }

  .navigation .left > ul > li > div {
    display: flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;
  }

  .navigation .left > ul > li > div.active,
  .navigation .left > ul > li > div:hover {
    text-decoration: underline;
    font-weight: 700;
    color: white;
    stroke: white;
  }

  .navigation .left > ul > li > div > img {
    transition: transform 0.3s;
  }

  .navigation .left ul.sub-items-menu {
    position: absolute;
    top: calc(100% + 27px);
    left: -24px;
    min-width: 168px;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 8px;

    background: #ffffff;
    box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.243444);
    border-radius: 5px;
    color: #2d2e40;
  }

  .navigation .left ul.sub-items-menu a {
    font-family: 'Ubuntu';
    font-style: normal;
    font-weight: 400;
    font-size: 15px;
    line-height: 33px;
    color: #2d2e40;
  }

  .navigation .left ul.sub-items-menu a:hover {
    font-weight: 700;
  }

  .navigation .right .cta {
    display: flex;
    align-items: center;
    gap: 32px;
  }

  .header-content .content h1 {
    font-size: 64px;
    line-height: 98px;
    letter-spacing: -1.92px;
  }

  .header-content .content p {
    font-size: 20px;
    line-height: 31px;
  }
}
</style>
