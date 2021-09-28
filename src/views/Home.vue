<template>
    <div>
        <h1>Welcome to {{title2}}!</h1>
        <!--        <input type="text" value='abc' >-->
        <input type="text" v-model="input1" >
        <button type="button" @click="getData">Get</button>
        <button type="button" @click="setData">Set</button>

        <select class="form-control" v-model="region" @change="changeRegion">
            <option :key="i" :value="data.value" v-for="(data, i) in options">{{data.label}}</option>
        </select>

        <table class="table table-bordered" v-if="tableShow">
            <tr :key="i" v-for="(data, i) in options">
                <td>{{data.value}}</td>
                <td>{{data.label}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
    export default {
        data(){
            return {
                title: '개발자의 품격',
                title2: 'Seoul',
                input1: 'abc',
                options: [
                    {value: 'S', label: 'Seoul'},
                    {value: 'J', label: 'Jeju'},
                    {value: 'B', label: 'Busan'},
                ],
                region: 'B',
                tableShow: false
            }
        },
        watch: {
            input1(){
                console.log(this.input1)
            }
        },
        methods: {
            getData(){
                alert(this.input1)
            },
            setData(){
                this.input1 = "12345"
            },
            changeRegion(){
                alert(this.region)
            }
        },
        beforeCreate() {
            console.log('a')
        },
        created() {
            console.log('b')
        },
        beforeMount() {
            console.log('c')
        },
        mounted() {
            console.log('d')
        },
        beforeUpdate() {
            console.log('e')
        },
        updated() {
            console.log('f')
        },
        beforeDestroy() {
            console.log('g')
        },
        destroyed() {
            console.log('h')
        }
    }
</script>
