<script setup>
import {ref} from "vue";
import { useRouter } from "vue-router";
import useAuth from "../composable/useAuth";
import useError from "../composable/useError";

const { isAuthenticated, login} = useAuth();

const username = ref("");
const password = ref("");

const router = useRouter();

const loggingIn = () => {
    login(username.value, password.value);
    if (isAuthenticated.value)
    {
        router.push("/");
    }
    else {
        setError("Invalid username or password");
        start();
    }
};

const { error, setError } = useError();

import { useTimeout, promiseTimeout } from "@vueuse/core";

const { ready, start } = useTimeout(5000, {controls: true});

</script>

<template>
<div class="flex flex-col  space-y-12 items-center justify-center  min-h-screen-nonav">

Login status: {{isAuthenticated}}

<div class="bg-pink-400 flex justify-center overflow-hidden items-center border-4 rounded-lg shadow-2xl ">
<img class="h-64" src = "../assets/bglogin.png" alt = "Hello BG">
<form @submit.prevent = "loggingIn" class = "flex flex-col p-4 space-y-4 ">

    <input type = "text" class = "bg-gray-100 border-2 rounded-lg" placeholder = "Username" v-model = "username" />

    <input type = "password"  class = "bg-gray-100 border-2 rounded-lg" placeholder = "Password" v-model = "password" />

    <button type = "submit" @submit.prevent = "loggingIn" class = "py-2 bg-blue-400 font-semibold rounded-lg">Login</button>
</form>
</div>

<div v-if = " !ready && error "
      class="absolute w-1/3 p-4 text-center text-white bg-purple-800 rounded-lg  bottom-2 right-2">
{{error}}
</div>

</div>
</template>