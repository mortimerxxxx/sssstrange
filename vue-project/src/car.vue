<template>
    <div class="car">
        <h3>Name: {{ carName }} / {{ reversName }}</h3>
        <p>Year: {{ carYear }}</p>

        <button @click="changeName">Change Name</button>
        <button @click="changeFunc()">Chunga-changa</button>
    </div>
</template>




<script>
    export default {
        // props: [
        //     'carName',
        //     'carYear'
        // ],
        // props: {
        //     carName: String,
        //     carYear: Number
        // },
        props: {
            carName: {
                    type: String,
                    default: 'Ty fuckacha'
            },
            carYear: Number,
            changeFunc: Function
        },
        methods: {
            changeName() {
                this.carName = 'Mazda',
                this.$emit('nameChanged', this.carName)
            }
        },
        computed: {
            reversName() {
                return this.carName.split('').reverse().join('')
            }
            
        }
    }
</script>




<style>
    .car {
        border: 1px solid #000;
    }
    .car h3 {
        margin-bottom: 10px;
        font-size: 40px;
    }
</style>