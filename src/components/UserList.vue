<template>
    <div class="user-list">
        <h3>User List</h3>
        <ul>
            <li v-for="(user, index) in users" 
                :key="index" 
                @click="onUserClicked(user, index)"
                :class="index === selectedIndex ? 'active' : ''">{{ user.name }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'UserList',
    data() {
        return {
            selectedIndex: null
        }
    },
    props: ['users'],
    methods: {
        onUserClicked(user, index) {
            this.selectedIndex = index;
            this.$emit('onUserSelected', user);
        }
    }
}
</script>

<style scoped lang="scss">
    .user-list {
        padding: 1rem;
        
        h3 {
            margin: 0;
            padding: 1rem 0;
            border-bottom: 1px solid #aaa;
        }
        
        ul {
            text-align: left;
            list-style: none;
            padding-left: 0;
            margin: 0;

            li {
                width: calc(100% - 0.5rem);
                padding: 0.5rem 0 0.5rem 0.5rem;
                border-bottom: 1px solid #aaa;
                cursor: pointer;
                transition: 0.3s;

                &:hover,
                &.active {
                    background: #ddd;
                }
            }
        }
    }
</style>