<script setup lang="ts">
const { signOut } = useAuth();

const logout = async()=>{ // async = assincrona
        console.log("Successfully logged out!");
        try{
            //await = espere (espere o signOut)
            await signOut({redirect: false});
            navigateTo('/');
        } catch(error){
            //catch = se não (se não fizer o signOut, cai no catch)
            console.log("Error when trying to execute logout", error);
        }}

definePageMeta({
    middleware: 'auth'

})
</script>

<template>
    <div>
        <h1>Minha Tela Home Modificada!!!</h1>    
        <button @click="logout" class="customButton">SAIR</button>
    </div>
</template>

<style lang="scss">

</style>