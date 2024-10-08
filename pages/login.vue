<template>
  <div class="login-layout">
    <div class="card" style="padding-top: 120px;">
      <!--   -->
      <div class="card-body">
        <div class="row">
          <div class="col">
            
            <form style="padding-top:120px ;">
              <h3 style="padding-left: 50px; padding-bottom: 30px;">Login Admin</h3>
            <div class="form-group" style="padding-left: 100px;">
              <label for="exampleInputEmail1">Email</label>
              <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
              <!-- <small id="emailHelp" class="form-text text-muted">We'll never share your email with anyone else.</small> -->
            </div>
            <div class="form-group" style="padding-left: 100px;">
              <label for="exampleInputPassword1">Password</label>
              <input type="password" class="form-control" id="exampleInputPassword1">
              <button type="submit" style="margin-top: 30px;" class="btn btn-primary">Submit</button>
            </div>
            <!-- <div class="form-group form-check">
              <input type="checkbox" class="form-check-input" id="exampleCheck1">
              <label class="form-check-label" for="exampleCheck1">Check me out</label>
            </div> -->
            <!-- <button type="submit" class="btn btn-primary">Submit</button> -->
          </form>
            <!-- <form action="">
              <input type="text">
            </form> -->
          </div>
          <div class="col">
            <img src="@/assets/bglogin.jpg" style="width: 70%;" alt="" class="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
.login-layout{
  background: #a8a8a8;
  height: 100vh;
  padding: 50px 100px;
}

.form-control{
  background-color: #d4d4d4;
}
.img{
  height: 70vh;
  width: 60vh;
}
</style>