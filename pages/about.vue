<template>
    <div class="grid">
        <div class="col-12 md:col-6 md:col-offset-3">
            <h2>about!</h2>
            <Button label="Get About Info from the server" icon="pi pi-check" @click="onClick" />
            <p v-if="message">{{ message }}</p>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const message = ref('')

    const onClick = async () => {
        const data = await $fetch('/api/hello', {
            method: 'GET'
        })
        message.value = data.message
    }
</script>
