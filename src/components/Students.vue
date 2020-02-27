<template>
    <div>
        <h4>We are inside the students component</h4>
        
            <p v-bind:class="{'graduated': mystudent.graduated}"
             v-bind:key="mystudent.id" v-for="mystudent in mystudents"> 
               <StudentItem v-bind:mystudent="mystudent"
                v-on:del-student="$emit('del-student', mystudent.id)" /> 
            </p>
         
        
    </div>
</template>

<script>
import StudentItem from './StudentItem'
export default {
    name:"Students",
    props: ["mystudents"],
    components:{
        StudentItem
    }
}
</script>
<style scoped>
 .graduated{
     text-decoration: line-through;
 }
</style>