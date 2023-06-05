<template>
    <header>
        <button @click="handleSwitchGame">{{ level }}</button>
    </header>
</template>

<script lang="ts">
export default {
    props: ['handleSwitchGame', 'level']
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