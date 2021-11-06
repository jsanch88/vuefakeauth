<script setup>

</script>

<template>
<div class="flex flex-col  space-y-12 items-center justify-center  min-h-screen-nonav">

<div class="bg-pink-400 flex justify-center overflow-hidden items-center border-4 rounded-lg shadow-2xl ">
<img class="h-64" src = "../assets/bglogin.png" alt = "Hello BG">
<form class = "flex flex-col p-4 space-y-4 ">

    <input type = "text" class = "bg-gray-100 border-2 rounded-lg" placeholder = "Username" />

    <input type = "password"  class = "bg-gray-100 border-2 rounded-lg" placeholder = "Password" />

    <button type = "submit" class = "py-2 bg-blue-400 font-semibold rounded-lg">Login</button>
</form>
</div>


</div>
</template>