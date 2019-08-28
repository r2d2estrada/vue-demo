<template>
    <div class="users">
        <h1>Users</h1>
        <div class="row">
            <div class="card-inline left">
                <UserList :users="users" @onUserSelected="setSelectedUser($event)" />
            </div>
            <div class="card-inline right">
                <UserDetail :user="selectedUser" />
            </div>
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
                { name: 'Juan', email: 'juan@gmail.com' },
                { name: 'Sophie', email: 'sophie@mail.com' }
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

<style scoped lang="scss">
    .row {
        display: flex;
        .card-inline {
            display: inline-block;
            box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
            margin: 0 1rem;

            &.left {
                width: 30%;
            }
            &.right {
                width: 70%;
            }
        }
    }
</style>