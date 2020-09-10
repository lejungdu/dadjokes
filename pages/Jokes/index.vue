<template>
    <div>Jokes</div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            jokes: [],
        }
    },
    async created(){
        const config = {
            headers: {
                Accept: 'application/json'
            }
        }
        const url = 'https://icanhazdadjoke.com/search'
        

        try {
            const res = await axios.get(url, config);
            console.log('hi')
            console.log(res.data)
        } catch (error) {
            console.log(error)
        }

    },
    head(){
        return{
            title: 'Welcome to Dad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes'
                }
            ]
        }
    }
}
</script>