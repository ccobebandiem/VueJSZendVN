<template>
  <div>
    <User
      v-for="user in listUser"
      v-bind:key="user.id"
      v-bind:user="user"
      v-on:deleteUser="deleteUser"
    />
  </div>
</template>

<script>
    import User from "./User";

    export default {
        name: "ListUser",
        props: {
            listUser: {
                type: Array,
                default: []
            }
        },
        data() {
            return {}
        },
        components: {
            User
        },
        methods: {
            deleteUser(data) {
                console.log('deleteUser in ListUser.vue');
                this.$emit('deleteUserEvent', data);
            }
        }
    }
</script>

<style scoped>

</style>
