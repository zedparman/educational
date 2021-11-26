<template>
    <div>
        <h1>profile</h1>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        name: 'next',
        async created () {
            const response = await axios.get('user');
            console.log(response);
        },
    }
</script>

<style scoped>

</style>