<template>
    <header>
        <button @click="handleSwitchGame">basic</button>
        <button @click="handleSwitchGame">advanced</button>
    </header>
</template>

<script lang="ts">
export default {
    props: ['handleSwitchGame']
}
</script>

<style>
header {
    display: flex;
    gap: 30px;
    align-items: center;
    justify-content: center;
}
</style>