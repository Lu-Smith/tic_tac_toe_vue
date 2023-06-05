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
