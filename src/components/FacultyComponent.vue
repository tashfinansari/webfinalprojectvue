<template>
    <div class='format' >
        <div>
            
                <h1>Faculty Name: {{faculty.facultyName}}</h1>
                <h2>Faculty ID: {{faculty.fid}} </h2>
                <h2>Year of Joining: {{faculty.yearOfJoining}} </h2>
                <h4>Subject Taught: {{faculty.subject}}</h4>
                <h4>Teaching Experience: {{faculty.teachingExperience}}</h4>
            
        </div>
    
    
        <!-- </div> -->
    </div>
    </template>
    
    <script>
    
    export default{
        name: 'FacultyComponent',
        props:{
            faculty: Array
        }
    }
    </script>
    
    <style scoped>
    
    .format{
        width: 100%;
        height: 100%;
        text-align: center;
    }
    
    
    h4{
        margin: 2px;
    }
    
    div{
        background-color: #ffb89e;
        color: black;
        padding: 1em;
    }
    
    </style>