<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <form @submit.prevent="handleSubmit">
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- OLD 
                    <div class="form-group">
                        <label for="fullname">Full Name:</label>
                        <input required type="text" name="fullname" class="form-control" v-model="fullName">
                    </div> -->
                    <!-- NEW -->
                    <full-name v-model="fullName"></full-name>
                    <!-- Mail -->
                    <div class="form-group">
                        <label for="email">Email:</label>
                        <input required type="email" name="email" class="form-control" v-model="email">
                    </div>
                    <!-- Password -->
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input required type="password" name="password" class="form-control" v-model="password">
                    </div>
                    <!-- Store Data? Yes/No -->
                    <div class="checkbox">
                        <label>
                          <input type="checkbox" v-model="storeData"> Store Data?
                        </label>
                    </div>
                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->
                    <button class="btn btn-primary" @click.prevent="handleSubmit">
                        Submit
                    </button>
                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                    </form>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }}</p>
                        <p>Mail: {{ email }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import FullName from './FullName.vue'
export default {
  data() {
    return {
      fullName: '',
      email: '',
      password: '',
      storeData: false,
      submitted: false,
    }
  },
  components: {
      FullName
  },
  methods: {
    handleSubmit() {
      this.submitted = true
    },
  },
}
</script>

<style>

</style>
