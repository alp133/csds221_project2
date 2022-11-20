<template>
  <div class="container">
    <h2 class="text-center mt-5">FRAMEWORKS</h2>
    <!-- Input-->
    <div class="d-flex">
      <input type="text" placeholder="Enter task" class="form-control" />
      <button class="btn btn-warning rounded-0">SUBMIT</button>
    </div>
    <!--Task Table-->
    <table class="table table-bordered">
      <thead>
        <tr>
          <th scope="col">Title</th>
          <th scope="col">Description</th>
          <th scope="col">Deadline</th>
          <th scope="col">Priority</th>
          <th scope="col">Is Complete</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>title01</td>
          <td>description01</td>
          <td>02/03/22</td>
          <td>med</td>
          <td>checkbox</td>
          <td>
            <div>
              <button class="btn btn-primary btn-block btn-sm w-75">
                <span class="fa-solid fa-pen-to-square"></span>
                update
              </button>
            </div>
            <div>
              <button class="btn btn-danger btn-block btn-sm w-75">
                <span class="fa-solid fa-circle-xmark"></span>
                cancel
              </button>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
data(){
  return{
    tasks: [
      {
      title: "title01",
      description: "description01",
      deadline: "02/03/22",
      priority: "med"
      }
    ]
  }
},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
