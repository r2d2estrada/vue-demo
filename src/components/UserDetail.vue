<template>
    <div div v-if="user" class="user-detail"> 
        <h3>User Detail</h3>
        <h4>Name: {{ user.name }}</h4>
        <p>Email: {{ user.email }}</p>  
    </div>
</template>

<script>
export default {
    name: 'UserDetail',
    props: ['user']
}
</script>

<style scoped lang="scss">
    .user-detail {
        padding: 0.5rem 1rem;
        h4, p {
            text-align: left;
        }
        h4 {
            margin: 4px 0;
        }
    }
</style>