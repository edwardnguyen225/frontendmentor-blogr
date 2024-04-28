<template>
  <div class="item">
    <h3>
      <slot name="heading"></slot>
    </h3>
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  flex-direction: column;
  gap: 16px;
  text-align: center;
}

.item h3 {
  font-weight: 600;
  font-size: 28px;
  line-height: 32px;
  color: #1f3e5a;
}

.content {
  line-height: 28px;
  letter-spacing: 0.5px;
  color: #4c5862;
}

@media (min-width: 1280px) {
  .item {
    max-width: 540px;
    text-align: left;
  }
}
</style>
