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
  color: white;
  background: red;
  border-radius: 8px;
}

.default {
  color: black;
  background: gray;
  border-radius: 0;
}

.box {
  width: 200px;
  display: flex;
  gap: 10px;
  .item {
    flex: 1;
    height: 50px;
    cursor: pointer;
    transition: 0.3s;
    line-height: 50px;
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
