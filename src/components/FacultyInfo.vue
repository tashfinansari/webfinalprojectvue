<template>
    
    <div class="facultyinfo">
        
       <div v-for="faculty in faculties" :key="faculty.fid" >
           <Faculty :faculty="faculty"/>
       </div>

    </div>

</template>

<script>

import Faculty from "./FacultyComponent.vue"
export default{

   name: 'FacultyInfo',
   components: {
       Faculty
   },
   props: {
       faculties: Array
   }

}

</script>


<style>
.facultyinfo{
   background-color: grey;
   padding: 1em;
   border-radius: 15px;
   text-align: center;
   box-sizing:border-box;
}
</style>