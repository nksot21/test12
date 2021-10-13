<template>
  <div id="app">
    <h2>Danh sach quan ly sinh vien</h2>
      <manage @add="handleAdd()"/>
      <modal></modal>
  </div>
</template>

<script>
    import Manage from './components/Manage.vue'
    import Modal from './components/modal.vue'
    export default {
        components: {
            Manage, Modal
        },
        methods: {
            handleAdd() {
                console.log('da them thanh cong')
            }
        }
    }
</script>

<style>
#app {

  margin-top: 60px;
  text-align: center;
}
</style>
