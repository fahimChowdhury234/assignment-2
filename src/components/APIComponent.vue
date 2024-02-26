<template>
    <div class="quote">
        <h1> Api Component</h1>

        <button @click="fetchData">Fetch Data</button>
        <div v-if="quote">
            <p>ID: {{ quote.id }}</p>
            <p>Quote: {{ quote.quote }}</p>
            <p>Anime: {{ quote.anime }}</p>
            <p>Character: {{ quote.character }}</p>
        </div>
    </div>
</template>
  
<script setup>
import { ref } from "vue";

const quote = ref(null)
const fetchData = (async () => {
    try {
        const response = await fetch('https://animechan.xyz/api/random');
        const data = await response.json();
        quote.value = data;
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}) 
</script>
  
<style  scoped>
.quote {
    width: 50%;
    margin: 0 auto;
}
</style>
<!-- export default {
    data() {
        return {
            quote: null
        };
    },
    methods: {
        async fetchData() {
            try {
                const response = await fetch('https://animechan.xyz/api/random');
                const data = await response.json();
                this.quote = data;
            } catch (error) {
                console.error('Error fetching data:', error);
            }
        }
    }
}; -->