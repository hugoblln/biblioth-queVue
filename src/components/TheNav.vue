<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <nav class="navbar navbar-expand-md tm-main-nav-container">

        <div class="collapse navbar-collapse tm-main-nav" id="tmMainNav">
            <ul class="nav nav-fill tm-main-nav-ul">
                <li class="nav-item">
                    <RouterLink to="/">Home</RouterLink>
                </li>
                <li class="nav-item"><a class="nav-link" href="/">Our Team</a></li>
            </ul>
        </div>
    </nav>
</template>

<style scoped></style>