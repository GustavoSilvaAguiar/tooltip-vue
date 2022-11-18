<template>
  <div class="tooltip">
    <slot></slot>
    <span>{{tooltip}}</span>
  </div>
</template>
<script lang="ts">
export default {
  props: {
    tooltip: String,
  },
  data() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
.tooltip {
  cursor: pointer;
  display: block;
  position: relative;
}
div.tooltip span {
  position: absolute;
  text-align: center;
  visibility: hidden;
  background-color: #14706A;
  color: #fff;
  padding: 5px 10px;
  border-radius: 5px;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.24);
  font-size: 13px;
}
div.tooltip span:after {
  content: '';
  position: absolute;
  bottom: 100%;
  left: 50%;
  margin-left: -8px;
  width: 0; height: 0;
  border-bottom: 5px solid #14706A;
  border-right: 8px solid transparent;
  border-left: 8px solid transparent;
}

div:hover.tooltip span {
  transition-delay: 0.5s;
  visibility: visible;
  top: 30px;
  left: 0;
  z-index: 999;
}
</style>
