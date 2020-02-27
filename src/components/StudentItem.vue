<template>
    <div>
        <p> {{mystudent.name }} {{mystudent.id}} 
            <input type="button" value="x" class="btn"
                v-on:click="$emit('del-student', mystudent.id)"
            />    
            <input type="button" value="X" class="btn"
                v-on:click="toggle"
            />    
         </p>
    </div>
</template>
<script>
export default {
    name:"StudentItem",
    props: ["mystudent"],
    methods:{
        toggle(){
            this.mystudent.graduated = !this.mystudent.graduated;
        }
    }
}
</script>
<style scoped>
.btn{
    background-color: red;
    border-radius: 90%;
    width: 25px;
    height:25px;
    
}
</style>