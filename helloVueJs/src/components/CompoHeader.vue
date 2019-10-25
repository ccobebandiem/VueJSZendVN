<template>
  <header>
    <h1>{{ titleHeader }}</h1>
    <button v-on:click="changeTitleHeader">Thay doi title tu TestHeader.vue</button>
    <ul>
      <li v-for="user in listUser" v-bind:key="user.id">{{ user.email }}</li>
    </ul>
  </header>
</template>

<script>
    export default {
        name: "TestHeader",
        props: {
            titleHeader: {
                type: String,
                default: 'Gia tri mac dinh'
            },
            listUser: {
                type: Array,
                default: []
            }
        },
        data() {
            return {

            }
        },
        methods: {
            changeTitleHeader(e) {
                // không được phép thay đổi trực tiếp props từ component cha
                // -> Truyền sự kiện thông báo ra bên ngoài
                // -> kích hoạt sự kiện changeTitleEvent ở trong CompoHeader.vue
                // -> kích hoạt function bên ngoài App.Vue nó sẽ chạy
                // -> khi function đó chạy -> thay đổi dữ liệu
                console.log('truoc khi kich hoat changTitleEvent trong CompoHeader.vue');
                var data = {
                    title: 'test -> data truyen bien thong qua event'
                }
                this.$emit('changeTitleEvent', data )
                console.log('sau khi kich hoat changTitleEvent trong CompoHeader.vue');
            }
        }
    }
</script>

<style scoped>

</style>
