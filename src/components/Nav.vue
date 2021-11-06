<template>
<div class="bg-blue-400 text-white">
<div class = "container mx-auto flex items-center justify-between">

<h1 class="tracking-tighter text-3xl font-bold">
Basic<span class="font-normal">Router</span>
</h1>
    
    <nav>
        <ul class= "flex space-x-4">
        <router-link to = "/">
            <li class="bg-black py-8 px-4 hover: cursor-pointer hover:bg-yellow-300 hover:text-pink-700">Home</li></router-link>

            <router-link to = "/about">
            <li class="bg-black py-8 px-4 hover: cursor-pointer hover:bg-yellow-300 hover:text-pink-700">About</li></router-link>

            <router-link to = "/hello">
            <li class="bg-black py-8 px-4 hover: cursor-pointer hover:bg-yellow-300 hover:text-pink-700">Hello</li>
        </router-link>
        

        </ul>
    </nav>
</div>
    </div>
</template>
