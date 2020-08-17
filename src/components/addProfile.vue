<template>
  <div id="add-profile">
        <h1>My profile</h1>
        <form v-if="!submitted" class="grid-container">
            <div class="col-1"></div>
            <div class="col-2">
                <h2>Edit account information</h2>
                <p>Personal</p>
                <div class="form">
                    <label for="firstName">First Name</label>
                    <input type="text" placeholder="First Name" v-model="profile.firstName" required>
                </div>

                <div class="form">
                    <label for="lastName">Last Name</label>
                    <input type="text" placeholder="Last name" v-model="profile.lastName" required>
                </div>

                <div class="form">
                    <label for="emailAddress">Email Address</label>
                    <input type="email" placeholder="Email Address" v-model="profile.email" required>
                </div>

                <div class="form">
                    <label for="phone">Phone</label>
                    <input type="tel" placeholder="Phone" v-model="profile.phone" required>
                </div>

                <p>Location</p>
                <div class="form">
                    <label for="country">Country</label>
                    <input type="text" placeholder="Country" v-model="profile.country" required>
                </div>

                <div class="form">
                    <label for="city">City</label>
                    <input type="text" placeholder="City" v-model="profile.city" required>
                </div>

            </div>
            <div class="col-3">
                <div class="col-3_grid">
                    <p>Education</p>
                    <div class="col-3_education">
                        <label for="education">Education</label>
                        <input class="educ" type="text" placeholder="Education" v-model="profile.education" required>
                    </div>    
                    <div class="col-3_date">
                        <label for="date">Date</label>
                        <input class="date" type="date" v-model="profile.date" required>
                    </div>
                    <div class="col-3_add-btn">
                        <div class="add"><i class="fas fa-plus-circle"></i><span>Add</span></div>
                    </div>
                    <div class="col-3_remove-btn">
                        <div class="remove"><span>Remove</span><i class="fas fa-minus-circle"></i></div>
                    </div>
                    <div class="col-3_save-btn">
                        <button v-on:click.prevent="post" class="save">Save changes</button>
                    </div>
                </div>
            </div>
            <div class="col-4"></div>
        </form>

        <div v-if="submitted" id="preview">
            <h2>{{profile.firstName}} {{profile.lastName}}</h2>
            <p class="email"><i class="far fa-envelope"></i> {{profile.email}}</p>
            <p class="phone"><i class="fas fa-mobile-alt"></i> {{profile.phone}}</p>
            <h3 class="location">Location</h3>
            <p class="country">Country: {{profile.country}}</p>
            <p class="city">City: {{profile.city}}</p>
            <h3 class="education-title">Education</h3>
            <p class="date">{{profile.date}}</p>
            <p class="education">{{profile.education}}</p>
            <button class="edit"><i class="fas fa-pencil-alt"></i>Edit</button>
        </div>

      </div>
</template>

<script>

export default {

  data () {
    return {
    
        profile: {
            firstName: '',
            lastName: '',
            email: '',
            phone: '',
            country: '',
            city: '',
            education: '',
            date: ''
        },
        submitted: false,
    }


  },

  methods: {
      post: function () {
          this.$http.post('http://jsonplaceholder.typicode.com/posts', {
              title: this.profile.firstName,
              body: this.profile.lastName,
              userId: 1
          }).then(function(data){
              console.log(data);
              this.submitted = true;
          });
      }
  }
}
</script>

