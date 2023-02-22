
<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <header class="navbar bg-dark">
        <nav class="container d-flex justifi-content-between">
            <div class="navbar-brand text-light">
                Rapha Todo 2.0
            </div>
            <div class="d-flex gap-3">
                <div class="nav-item">
                    <RouterLink class="text-light" to="/">Home</RouterLink>
                </div>
                <div class="nav-item">
                    <RouterLink class="text-light" to="/about">About</RouterLink>
                </div>
            </div>
        </nav>
    </header>
</template>


<style scoped></style>