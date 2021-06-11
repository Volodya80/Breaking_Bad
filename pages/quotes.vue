<template>
    <div class="container">
        <p class="h1 text-primary text-center">Цитаты</p>
        <Quote v-on:changed="find"></Quote>

        <figure v-for="(quote, index) in quotes" :key="index">
            <blockquote class="blockquote">
                <p>{{quote.quote}}</p>
            </blockquote>
            <figcaption class="blockquote-footer">
                {{quote.author}} said in <cite title="serie">{{quote.series}}</cite>
            </figcaption>
        </figure>
    </div>
</template>

<script>
import Quote from "@/components/quotes-component"

export default {
    components: {
        Quote
    },
    data() {
        return {
            quotes: []
        }
    },
    methods: {
        async find(val){
            try {
                let response = await fetch(this.request(val));
                let data = await response.json();
                console.log(data);
                this.quotes = []
                for (let i in data) {
                    this.quotes.push(data[i]);
                }
            }
            catch(err){
                console.log(err.message)
            }
        },
        request(val) {
            return "https://www.breakingbadapi.com/api/quote?author="+val.split(' ').join('+');
        }
    },
    computed: {
        
    }
}
</script>