<template>
    <div class="users">
        <h1>Users</h1>
        <div class="card-inline">
            <UserList :users="users" @onUserSelected="setSelectedUser($event)" />
        </div>
        <div class="card-inline">
            <UserDetail :user="selectedUser" />
        </div>
    </div>
</template>

<script>
import UserList from './../components/UserList';
import UserDetail from './../components/UserDetail';

export default {
    name: 'Users',
    data() {
        return {
            users: [
                { name: 'Arturo', email: 'artestradaredz.85@gmail.com' },
                { name: 'Marie', email: 'marie@gmail.com' },
                { name: 'Juan', email: 'juan@gmail.com' }
            ],
            selectedUser: null
        }
    },
    components: {
        UserList,
        UserDetail
    },
    methods: {
        setSelectedUser(event) {
            this.selectedUser = event;
        }
    }
}
</script>

<style scoped>
    .card-inline {
        display: inline-block;
        width: 45%;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
        margin: 0 1rem;
    }
</style>