<script setup lang="ts">
definePageMeta({
    middleware: 'auth'
})


const {signOut} = useAuth();

const Logout = () => {
    console.log('Fazendo Logout');

    signOut({redirect:false}).then(()=> {
    console.log('Logout com Sucesso');
    navigateTo('/')})

    .catch((error)=> {
        console.log('deu algum erro');
    });
}

</script>

<template>
    <div>
        <h1>Minha Tela Home!!!</h1>   
        <button  type='submit' class="customButton" @click="Logout">SAIR</button> 
    </div>
</template>

<style lang="scss">

</style>
