<template>
    <div>
        <div class="input-group mb-3">
            <input type="text" class="form-control" 
                placeholder="Имя героя" aria-label="Recipient's username" 
                aria-describedby="button-addon2"
                v-model="value" v-on:change="changed">
<!--             <button class="btn btn-outline-secondary" type="button" 
                id="button-addon2" @click="find">Найти цитаты</button> -->
        </div> 
       
    </div>
</template>

<script>
export default {

    data() {
        return {
            value: ""
        }
    },
    methods: {
        changed() {
            this.$emit('changed', this.value)
        }
    }

}
</script>