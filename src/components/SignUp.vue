<template>

  <div class="row">
    <div class="col-8 offset-2 mt-5" >
      <div class="card card-info">
        <div class="card-header">
          <h3 class="card-title">Vue Form</h3>
        </div>


        <form class="form-horizontal">
          <div class="card-body">
            <div class="form-group row">
              <label for="inputEmail3" class="col-sm-2 col-form-label">Email</label>
              <div class="col-sm-10">
                <input type="email" class="form-control" v-model="email" placeholder="Email">
              </div>
            </div>
            <div class="form-group row">
              <label class="col-sm-2 col-form-label">Password</label>
              <div class="col-sm-10">
                <input v-model="password" type="password" class="form-control" id="inputPassword3" placeholder="Password">
              </div>
            </div>
            <div class="form-group row">
              <label for="inputEmail3" class="col-sm-2 col-form-label">Position :</label>
              <select v-model="position" class="form-control">
                <option value="fizika">Fizika</option>
                <option value="matematika">Matematika</option>
              </select>
            </div>
            <div class="form-group row">
              <label for="inputEmail3" class="col-sm-2 col-form-label">ENGLISH</label>
              <input value="English" v-model="languanges" type="checkbox" >
            </div>
            <div class="form-group row">
              <label for="inputEmail3" class="col-sm-2 col-form-label">RUSSIAN</label>
              <input value="Russian" v-model="languanges" type="checkbox" >
            </div>
            <div class="form-group row">
              <label for="inputEmail3" class="col-sm-2 col-form-label">Skills</label>
              <input  v-model="tempSkilss" type="text" @keyup="handSkil">
            </div>
          </div>

        </form>
      </div>

      {{email}}
      {{password}}
      {{position}}
      {{skils}}
      <ul>
        <li v-for="languange in languanges" :key="languange">{{languange}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
data(){
  return{
    email:'',
    password:'',
    position:'fizika',
    languanges:[],
    tempSkilss:'',
    skils:[]
  }
}
,methods:{
    handSkil(e){
      if(e.key == ',' && this.tempSkilss.length>=2){
        this.skils.push(this.tempSkilss)
        this.tempSkilss = null
      }
    }
  }
}
</script>