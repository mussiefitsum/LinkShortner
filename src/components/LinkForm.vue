<template>
    <div>
        <label>Paste Link Here</label>
        <br />
        <input type="text" v-model="link" />
        <button @click="shortenLink">Shorten</button>
    </div>
</template>

<script>

    export default {
        data() {
            return {
                link: ''
            }
        },
        methods: {
            async shortenLink() {
                console.log(import.meta.env.VITE_ACCESS_TOKEN);
                console.log(this.link);
                const options = {
                    method: "POST",
                    headers: {
                        'Content-Type': 'application/json',
                        'Authorization': `Bearer ${import.meta.env.VITE_ACCESS_TOKEN}`
                    },
                    body: JSON.stringify({'long_url': this.link})
                }
                const data = await fetch('https://api-ssl.bitly.com/v4/shorten', options);
                const results = await data.json();
                this.link = results.link;
            }
        }
    }
</script>

<style>

</style>