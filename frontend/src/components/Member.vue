<template>
  <div class="container">
    <div class="row">
      <div class="col-4">
        <h5>คำค้นหาเพิ่มเติม [ระบบจะค้นจากชื่อคณะ,หลักสูตร]</h5>
        <div class="mb-3">
          <input type="text" class="form-control" v-model="word" />
        </div>
        <button class="btn btn-success" @click="searchByWord(word)">
          ค้นหา
        </button>
      </div>
      <div class="col-8">
        <div v-for="m in classes" :key="m._id" class="row mb-2">
          <div class="card">
            <div class="card-header">
              <h4>หลักสูตร: {{ m.course }}</h4>
              <h5>แผนการศึกษา: {{ m.studyPlan }}</h5>
            </div>
            <div class="card-body">
              <p>คณะ: {{ m.fauculty }}</p>
              <p>วันที่เปิดรับสมัคร : {{ m.date }}</p>
              <div class="row">
              <div class="col-3">
                <a
                  v-bind:href="'' + m.recruit"
                  class="btn btn-primary"
                  role="button"
                  >ประกาศรับสมัคร</a
                >
              </div>
              <div class="col-3 mr-0">
                <a
                  v-bind:href="'' + m.recruit"
                  class="btn btn-danger"
                  role="button"
                  >คุณสมบัติผู้สมัคร</a
                >
              </div>
            </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      classes: [],
      word: "",
    };
  },
  created() {
    axios
      .get(process.env.VUE_APP_PORT + "/class/all")
      .then((res) => (this.classes = res.data));
  },
  methods: {
    searchByWord(w) {
      console.log(w);
      this.classes = this.classes.filter(e=> e.course == w )
    },
  },
};
</script>

