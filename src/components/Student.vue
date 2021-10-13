<template>
    <div id="whole">
        <div class="std">
            <p><span>Mssv: </span>{{stu.mssv}}</p>
            <p><span>Name: </span>{{stu.name}}</p>
            <p><span>Age: </span>{{stu.age}}</p>
            <p><span>Class: </span>{{stu.class}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['stu'],
        data() {
            return {
                student: [
                    { mssv: '20520225', name: 'Nha Khuyen', age: 18, class: 'CNTT2020' }
                ]
            }
        }
    }
</script>

<style scoped>
    *{
        margin: 0px;
    }
    .std {
        display: block;
        text-align: left;
    }
    .std p {
         padding: 5px 10px;
         color:white;
    }
    .std p span{
        font-weight: bold;
    }
     
</style>