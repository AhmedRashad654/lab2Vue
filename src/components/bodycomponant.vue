<template>
  <div class="col-9">
    <button class="btn btn-primary" @click="openModal">Add column</button>
    <table class="table table-striped table-bordered">
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="student in students" :key="student.id">
          <td>{{ student.id }}</td>
          <td>{{ student.name }}</td>
          <td>{{ student.city }}</td>
        </tr>
      </tbody>
    </table>
    <form
      class="w-50 bg-light rounded-3  position-fixed d-flex flex-column p-2 gap-3"
      style="top: 10%"
      v-if="showDialog===true"
      @submit="addRow"
    >
      <div>
        <label for="">ID</label><br />
        <input type="number" class="form-control" v-model="newStudent.id" required/>
      </div>
      <div>
        <label for="">name</label><br />
        <input type="text" class="form-control" v-model="newStudent.name" required/>
      </div>
      <div>
        <label for="">city</label><br />
        <input type="text" class="form-control" v-model="newStudent.city" required/>
      </div>
      <div class="row w-100 p-2">
        <button class="btn btn-primary">add</button>
        <button class="btn btn-danger" @click="closeDialog">close</button>
      </div>
    </form>


  </div>
</template>

<script>
import student from "../student";
export default {
  data:()=>({
 
         students: student,
       newStudent:{
      id:null,
      name:"",
      city:""
    }
    ,
    showDialog:false
    
  }),
  methods:{
    openModal(){
      this.showDialog = true
    },
       closeDialog(){
      this.showDialog=false
    },
    addRow(){
      this.students.push({...this.newStudent})
      this.showDialog=false
    }
  }
};
</script>

<style></style>
