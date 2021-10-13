<template>
    <div>
        <h3>Xem ket qua</h3>
        <button @click="status = !status">Result</button>
        <div v-show="status">
            thong tin ket qua sinh vien
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            this.$root.$on('add', function (stu) {
                console.log(stu.mssv);
            })
        },
        data() {
            return {
                status: true
            }
        }
    }
</script>

<style scoped>

</style>