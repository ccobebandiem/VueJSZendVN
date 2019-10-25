<template>
  <div id="app">
    <demo-slot/>
    <compo-header
      v-bind:titleHeader="title"
      v-on:changeTitleEvent="handleChangeTitle"
      v-bind:list-user="listUser"
    />
    <list-user
      v-bind:listUser="listUser"
      v-on:deleteUserEvent="handleDeleteUser"
    />
    <comp-footer
      v-bind:title="title"
    />
    <demo-ref/>
  </div>
</template>

<script>
    // + props -> những data truyền từ compo cha vào compo con -> cú pháp giống thuộc tính -> ràng buộc thuộc tính -> sử dụng v-bind:
    import CompoHeader from "./components/CompoHeader";
    import CompFooter from "./components/CompFooter";
    import ListUser from "./components/ListUser";
    import DemoRef from "./components/DemoRef";
    import DemoSlot from "./components/DemoSlot";

    export default {
        name: 'App',
        data() {
            return {
                title: "Hello VueJs Header",
                listUser: [
                    {id: 1, email: 'test@gmail.com', active: true},
                    {id: 2, email: 'test2@gmail.com', active: false},
                    {id: 3, email: 'test3@gmail.com', active: true},
                    {id: 4, email: 'test4@gmail.com', active: false},
                    {id: 5, email: 'test5@gmail.com', active: false},
                    {id: 6, email: 'test6@gmail.com', active: true},
                    {id: 7, email: 'test7@gmail.com', active: true},
                ],
            }
        },
        components: {
            DemoSlot,
            CompoHeader,
            CompFooter,
            ListUser,
            DemoRef
        },
        methods: {
            handleChangeTitle(data) {
                this.title = data.title;
                console.log('handleChangeTitle duoc goi sau khi kich hoat thanh cong App.vue');
            },
            handleDeleteUser(data) {
                var indexDelete = -1;
                this.listUser.forEach((u, idx) => {
                    console.log(u.id, idx, data.id);
                    if (u.id === data.id) {
                        indexDelete = idx;
                    }
                });
                if (indexDelete != -1) {
                    this.listUser.splice(indexDelete, 1);
                }
                console.log('indexDelete sau khi chay vong for', indexDelete);
                console.log('handleDeleteUser trong App.vue', data)
            }
        }
    }
</script>

<!--
Props Down: truyền dữ liệu từ cha vào con -> thằng con chỉ được dùng, k đc thay dổi trực tiếp
Event Up: truyền thông điệp ( sự kiện ) thông báo cho component cha biết là nó muốn thay đổi dữ liệu. -> nhiệm vụ của component cha là nhận thông điệp và thay đổi data
-> custome event trong Vuejs
click-> sự kiện có sẵn trong vuejs. v-on:click='changeTitle'  - click: tên sự kiện có sẵn của vue - changeTitle: hàm xử lý sự kiện khi nguoi dung click
-->

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
