<script setup>
import useAuth from '../composable/useAuth';
const { isAuthenticated, logout} = useAuth();
</script>

<template>
<div class="bg-purple-500 text-white">
<div class = "container mx-auto flex items-center justify-between">

<h1 class="tracking-tighter text-3xl font-bold">
Vue<span class="bg bg-pink-300 font-normal">FakeAuth</span>
</h1>
    
    <nav>
        <ul class= "flex space-x-4">
        <router-link to = "/">
            <li class="bg-pink-500 py-8 px-4 hover: cursor-pointer hover:bg-gray-300 hover:text-blue-700">Home</li></router-link>

            <router-link  to = "/about">
            <li class="bg-pink-500 py-8 px-4 hover: cursor-pointer hover:bg-gray-300 hover:text-blue-700">About</li></router-link>

            <router-link v-if = "!isAuthenticated" to = "/login">
            <li class="bg-pink-500 py-8 px-4 hover: cursor-pointer hover:bg-gray-300 hover:text-blue-700">Login</li></router-link>

            <div v-else class = "flex">

            <router-link to = "/secret">
            <li class="bg-pink-500 py-8 px-4 hover: cursor-pointer hover:bg-gray-300 hover:text-blue-700">Secret</li></router-link>

            <button  @click = "logout">
            <li class="bg-pink-500 py-8 px-4 hover: cursor-pointer hover:bg-gray-300 hover:text-blue-700">Logout</li></button>

            </div>

        </ul>
    </nav>
</div>
    </div>
</template>
