<template>
    <div class = "nav">
        <a @click="Home" :href="'/' + usertype + '/' + userid"><i class="fa fa-fw fa-home"></i> Home</a>
        <a @click="Profile" :href="'/' + usertype + '/' + userid + '/profile'">Profile</a>
        <a @click="Settings" :href="'/' + usertype + '/' + userid + '/settings'">Settings</a>
        <a v-on:click="Logout" href = "/login">Logout</a>

    </div>
</template>

<script>
    export default {
        name:'NavBar',
        props: ['usertype', 'userid'],
        methods:{
            logout()
            {
                localStorage.clear();
                this.$router.push({name:'Login'})
            }
        }
    }
</script>

<style scoped>
    .nav {
        width: 100%;
        height: 45px;
        background-color: #555;
        overflow: auto;
    }
    
    .nav a {
        float: left;
        padding: 12px;
        color: white;
        text-decoration: none;
        font-size: 17px;
    }
    
    .nav a:hover {
        background-color: #8c72e0;
    }
    
    @media screen and (max-width: 500px) {
        .navbar a {
        float: none;
        display: block;
        }
    }

</style> 