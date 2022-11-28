<template>
    <div>
        <form @submit.prevent="save">
            <div>
        <label for ="name"> product name</label>
        <input type="text" id="name" v-model="formData.name">
    </div>
    <div>
        <label for ="category"> category</label>
        <input type="text" id="name" v-model="formData.category">
    </div>
    <div>
        <label for ="price"> price</label>
        <input type="text" id="price" v-model="formData.price">
    </div>
    <button> save</button>
        </form>
    </div>
</template>

<script>
import axios from 'axios'
import { METHODS } from 'http';

    export default{
        name: 'post',
        data(){
            return{
                name:'',
                category:'',
                price: ''

            }
        },
       methods:{
            save(){
                axios.post('localhost:8004/products/',this.formData)
                

            }
        }
    }
</script>
