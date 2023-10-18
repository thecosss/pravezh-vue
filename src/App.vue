<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Общие данные</router-link>
      <router-link to="/about">Информация о долге</router-link>
      <router-link to="/about">Платежи</router-link>
      <router-link to="/about">Обещания <AppBtn class="outline btn-icon" icon="Plus" /></router-link>
      <router-link to="/about">Работа в суде</router-link>
    </div>
    <router-view/>

    <div class="modaltest" v-if="showModal">modal test</div>
  </div>
</template>

<script>
  import AppBtn from './components/AppBtn.vue';

  export default {
    data(){
      return {
        showModal: false
      }
    },
    components: {AppBtn}
  }
</script>

<style lang="less">
.modaltest {
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: #000;
  opacity: 0.5;
}
#app {
  background-color: #F3F3F3;
  width: 1234px;
  border-radius: 16px;
  min-height: 700px;
}
#nav {
  border-bottom: 1px solid #C7C7C7;
  display: flex;
  gap: 8px;
  padding: 0 32px;
  a {
    text-decoration: none;
    padding: 16px 8px;
    color: #000;
    border-bottom: 2px solid transparent;
    margin-bottom: -1px;
    display: flex;
    align-items: center;
    gap: 6px;
  }
}
.router-link-exact-active {
  font-weight: 600;
  border-bottom-color: #5167F1 !important;
}
</style>
