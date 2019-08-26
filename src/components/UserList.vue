<template>
    <div class="user-list">
        <h3>User List</h3>
        <ul>
            <li v-for="(user, index) in users" :key="index" @click="onUserClicked(user)">{{ user.name }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'UserList',
    data() {
        return {}
    },
    props: ['users'],
    methods: {
        onUserClicked(user) {
            this.$emit('onUserSelected', user);
        }
    }
}
</script>

<style scoped lang="scss">
    .user-list {
        ul {
            text-align: left;
            list-style: none
        }
    }
</style>