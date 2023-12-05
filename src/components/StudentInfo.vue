<template>
    
     <div class="studentinfo">
         
        <div v-for="student in students" :key="student.id" >
            <Student :student="student"/>
        </div>

     </div>

</template>

<script>

import Student from "./StudentComponent.vue"
export default{

    name: 'StudentInfo',
    components: {
        Student
    },
    props: {
        students: Array
    }

}

</script>


<style>
.studentinfo{
    background-color: grey;
    padding: 1em;
    text-align: center;
    border-radius: 15px;
    box-sizing:border-box;
}
</style>