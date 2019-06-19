<template>
    <div>
        <nav>
            <ul>
               
                <li> <router-link to="/">Home</router-link></li>
                <li> <router-link to="/about">About</router-link></li>
                <li> <router-link :to="{name: 'contact'}">Contact</router-link></li>
            </ul>
        </nav>
        <div>
            <ul>
                <li v-for="(id,index) in userIds" :key="index">
                    <router-link :to="{ name: 'profile', params:{ user_id: id}}"> Profile {{id}} </router-link>
                </li>
            </ul>
            <button @click="goHome">Home</button>
            <button @click="goContact">Contact</button>
            <button @click="goBack">Back</button>
            <button @click="goForward">Next</button>

        </div>
    </div>
</template>

<script>
export default {
    name:'Navbar',
    data(){
        return{
            userIds:['1','2','3']
        }
    },
    methods:{
        goHome(){
            this.$router.push( {name: 'Home'} )
        },
        goContact(){
            this.$router.push( {name: 'contact'} )
        },
        goBack(){
            this.$router.go( -1 )
        },
        goForward(){
            this.$router.go( 1 )
        }
    }
}
</script>

<style scoped>
    nav{
        text-align: center;
    }
    nav ul{
        padding: 0;
    }
    nav li{
    display: inline-block;
    list-style-type: none;
    margin: 0;
    padding: 8px;
    }

</style>


