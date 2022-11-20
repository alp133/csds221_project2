<template>
  <div class="container-fluid">
    <div class="card">
    <div class = "card-header d-flex justify-content-between align-items-center">
      <div class = "col-md-11">
      <h5 class= "text-center"> FRAMEWORKS </h5>
      </div>
      <div class = "col-md-1">
      <button type = "button" class="btn btn-sm">Add</button>
      </div>
      </div>
    </div>
    <!-- Input-->
    <div class="d-flex">
      <input
        v-model="task"
        type="text"
        placeholder="Enter task"
        class="form-control"
      />
      <button @click="submitTask" class="btn btn-warning rounded-0">
        SUBMIT
      </button>
    </div>

    <div>
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
          <tr v-for="(task, index) in tasks" :key="index">
            <td>{{ task.title }}</td>
            <td>{{ task.description }}</td>
            <td>{{ task.deadline }}</td>
            <td>
              <span>{{ task.priority }}</span>
            </td>
            <td align="center">
              <label class="container">
                <input type="checkbox" />
                <span class="checkmark"></span
              ></label>
            </td>
            <td>
              <div>
                <button
                  @click="editTask(index)"
                  class="btn btn-primary btn-block btn-sm w-75"
                >
                  <span class="fa-solid fa-pen-to-square"></span>
                  update
                </button>
              </div>
              <div>
                <button
                  @click="deleteTask(index)"
                  class="btn btn-danger btn-block btn-sm w-75"
                >
                  <span class="fa-solid fa-circle-xmark"></span>
                  cancel
                </button>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      task: '',
      editedTask: null,
      availablePriorities: ['Low', 'Med', 'High'],
      tasks: [
        {
          title: 'title01',
          description: 'description01',
          deadline: '02/03/22',
          priority: 'med',
        },
      ],
    };
  },
  methods: {
    submitTask() {
      if (this.task.length === 0) return;
      if (this.editedTask === null) {
        this.tasks.push({
          title: this.task,
          description: 'a description',
          deadline: 'a time',
          priority: 'mid',
        });
      } else {
        this.tasks[this.editedTask].title = this.task;
        this.editedTask = null;
      }
      this.task = '';
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    editTask(index) {
      this.task = this.tasks[index].title;
      this.editedTask = index;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
