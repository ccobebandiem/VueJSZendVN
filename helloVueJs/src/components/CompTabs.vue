<template>
  <div class="comp-tabs">
    <div class="tab-title">
      <span>{{ title }}</span>
      <i class="icon ion-logo-apple"></i>
    </div>
    <div class="tab-content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
    export default {
        name: "comp-tabs",
        props: {
            title: String,
        },
        data() {
            return {}
        }
    }
</script>

<style scoped>
  .tab-title {
    padding: 15px 30px;
    display: flex;
    justify-content: space-between;
    border: 2px solid #000;
  }
  .tab-content {
    margin-top: 2px;
    padding: 1px;
    border: 2px solid #0000ff;
  }
  .tabs-header {
    margin: 0;
    padding: 0;
    display: flex;
    list-style-type: none;
  }
  .tabs-header li {
    padding: 8px 15px;
    background-color: #ccc;
    transition: all .3s ease;
  }
  .tabs-header li:hover {
    color: #fff;
    background-color: #333;
  }
  .tab-content {
    padding: 15px;
    border: 2px solid salmon;
    text-align: left;
  }
</style>
