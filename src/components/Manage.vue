<template>
    <div>
        <div id="add_sv">
            <button @click="add_status = !add_status">Them sinh vien</button>
            <div v-show="add_status">
                <ul>
                    <li>
                        <label for="mssv">MSSV: </label> 
                        <input id="mssv" type="text" v-model="stu.mssv"/>
                    </li>
                    <li>
                        <label for="name">Name: </label>
                        <input id="name" type="text" v-model="stu.name"/>
                    </li>
                    <li>
                        <label for="age">Age: </label>
                        <input id="age" type="text" v-model="stu.age"/>
                    </li>
                    <li>
                        <label for="class">Class: </label>
                        <input id="class" type="text" v-model="stu.class"/>
                    </li>
                </ul>
                <button type="submit" @click="stuAdd">Submit</button>
            </div>
        </div>

        <div id="listshow" v-for="(student, index) in students" :key="index">
            <Stu_info :stu="student"></Stu_info>
            <button @click="del_stu(index)">Xoa</button>
        </div>

        <h3>Danh sach nay co: {{students.length}} sinh vien</h3>
    </div>
</template>

<script>
    import Stu_info from './Student.vue'
    export default {
        data() {
            return {
                stu: { mssv:'', name:'', age:'', class:''},
                students: [],
                add_status: false
            }
        },
        components: { Stu_info },
        methods:
        {
            stuAdd() {
                this.$root.$emit('add', this.stu);
                this.students.push({mssv: this.stu.mssv, name: this.stu.name, age: this.stu.age, class: this.stu.class});
                this.add_status = !this.add_status;
                this.stu.mssv = '';
                this.stu.name = '';
                this.stu.age = '';
                this.stu.class = '';
                
            },
            del_stu(index) {
                this.students.splice(index, 1);
            }
        }
    }
</script>

<style scoped>
    * {
        margin:0px;
        padding:0px;
        list-style:none;
        text-align: center;
        outline:none;
    }
    ul{
        display: block;
        width: 400px;
        text-align:left;
        background-color: grey;
        margin-left:auto;
        margin-right: auto;
    }
    ul li{
        display: block;
        margin: 5px 10px;

    }
    #listshow {
        display: flex;
        background-color: dimgray;
        margin-top: 10px;
        justify-content: space-between;
        margin-left: auto;
        margin-right: auto;
        width: 500px;
    }
    #listshow{
        width:400px;

    }
    #listshow button{
        width:50px;
        height:20px;
        margin-top:10px;
        margin-right:10px
    }
</style>