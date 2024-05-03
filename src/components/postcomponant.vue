<template>
  <div class="col-12 p-5 d-flex">
    <div class="col-6">
      <div class="m-5">
        <label for="">postTitle</label><br /><br />
        <input type="text" class="form-control" v-model="newPost.title"/>
      </div>
      <div class="m-5">
        <h4>category</h4>
        <div class="d-flex gap-5">
          <div v-for="cat in post.category" :key="cat" class="d-flex">
            <input type="radio" name="category" class="m-2" v-model="newPost.category" :value="cat"/>
            <label>{{ cat }}</label>
          </div>
        </div>
      </div>
      <div class="m-5">
        <h4>series</h4>
        <select class="form-control" v-model="newPost.Editation">
          <option v-for="ser in post.series" :key="ser" >{{ ser }}</option>
        </select>
      </div>
      <div class="m-5">
        <h4>social Network</h4>
        <div class="d-flex gap-5">
          <div v-for="soc in post.socialNetworks" :key="soc" class="d-flex">
        <input type="checkbox" name="category" class="m-2" v-model="newPost.Networks" :value="soc"/>
            <label>{{ soc }}</label>
          </div>
        </div>
      </div>
      <div class="m-5">
        <input type="checkbox" class="m-2" v-model="newPost.PublishNow"/>
        <label>publish now</label>
      </div>
      <div class="m-5">
        <button class="btn btn-primary" @click="openMo">Next</button>
      </div>
    </div>

    <!-- ///////////////////////// -->
    <div class="col-5 m-5">
      <div
        class="w-100 bg-light rounded-3 d-flex flex-column p-2 gap-3"
        style="top: 10%"
        v-if="alerts===true"
      >
   <p>title:{{newPost.title}}</p>
   <p>category:{{newPost.category}}</p>
   <p>Edition:{{newPost.Editation}}</p>
   <p>Networks:<span v-for="co in newPost.Networks" :key="co"> {{co}} ,</span></p>
   <p>PublishNow:{{newPost.PublishNow}}</p>


        <div class="row w-100 p-2">
          <button class="btn btn-primary" @click="closeMo">submit</button>
          <button class="btn btn-danger" @click="closeMo">close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import post from "../post";
export default {
  data() {
    return {
      post: post,
      newPost: {
        title: "",
        category: "",
        Editation: "",
        Networks: [],
        PublishNow: false,
      },
      alerts: false,
    };
  },
  methods: {
    openMo() {
      this.alerts = true;
    },
    closeMo() {
      this.alerts = false;
    },
      checkedNetworks() {
    return this.newPost.Networks;
  }
  },






};
</script>

<style></style>
