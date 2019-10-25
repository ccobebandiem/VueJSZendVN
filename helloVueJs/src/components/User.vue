<template>
  <div>
    <p>{{ user.email }}</p>
    <button
      v-on:click="handleDelete">Delete</button>
  </div>
</template>

<script>
    export default {
        name: "User",
        props: {
            user: {
                type: Object,
                default: null
            }
        },
        data() {
            return {

            }
        },
        methods: {
            handleDelete(e) {
                var data = {
                    id: this.user.id
                }
                console.log('handleDelete trong User.vue');
                this.$emit('deleteUser', data);
            }
        }
    }
</script>

<style scoped>

</style>
