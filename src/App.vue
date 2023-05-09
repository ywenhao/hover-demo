<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue';
</script>

<template>
  <div class="box">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
  </div>
</template>

<style lang="scss" scoped>
.active {
  background: red;
}

.default {
  background: gray;
}

.box {
  width: 200px;
  display: flex;
  gap: 10px;
  .item {
    flex: 1;
    height: 50px;
    cursor: pointer;
    @extend .default;
  }
}

// hover 部分
.box {
  .item:nth-child(2) {
    @extend .active;
  }
  &:hover {
    .item {
      @extend .default;
    }
    .item:hover {
      @extend .active;
    }
  }
}
</style>
