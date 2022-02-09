<template>
    <h1>Dashboard</h1>
    <p>Liste des Utilisateurs</p>
    <p>
        <router-link to="/sign-up">Nouveau Utilisateur</router-link>
    </p>
    <br><br><br><br>

    <table>
        
    </table>
</template>

<script>
    import axios from 'axios';
    export default {
        name : 'Home',
        data()
        {
            return {
                users:[],
            }
        },
        async mounted()
        {
            let result = await axios.get("http://localhost:3000/users");
            console.warn(result);
            this.users = result.data;
        }
    }
</script>

