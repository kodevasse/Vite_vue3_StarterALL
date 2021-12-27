<script>
import AddUser from "/src/components/AddUser.vue";
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Users",
  methods: {
    ...mapActions(["fetchUsers", "deleteUser"]),
  },
  computed: mapGetters(["usersList"]),
  created() {
    this.fetchUsers();
  },
  components: {
    AddUser,
  },
};
</script>

<template>
  <ul>
    <li v-for="user in usersList" :key="user.id">
      <div class="flex flex-row gap-x-3">
        <span class="text-teal-300 mt-1"> {{ user.id }}</span>
        <strong class="mt-1 gap-x-3">{{ user.name }} </strong>
        <span class="border-lime-300 border-2 rounded">({{ user.email }})</span>
        <small class="btn btn-error" @click="deleteUser(user.id)"
          >&#10005;</small
        >
      </div>
    </li>
  </ul>
  <AddUser />
  <!-- <div class="overflow-x-auto">
    <table class="table w-full"> 
      <thead>
        <tr>
          <th></th>
          <th>Name</th>
          <th>Job</th>
          <th>Favorite Color</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>1</th>
          <td>Cy Ganderton</td>
          <td>Quality Control Specialist</td>
          <td>Blue</td>
        </tr>
        <tr>
          <th>2</th>
          <td>Hart Hagerty</td>
          <td>Desktop Support Technician</td>
          <td>Purple</td>
        </tr>
        <tr>
          <th>3</th>
          <td>Brice Swyre</td>
          <td>Tax Accountant</td>
          <td>Red</td>
        </tr>
        <tr>
          <th>4</th>
          <td>Marjy Ferencz</td>
          <td>Office Assistant I</td>
          <td>Crimson</td>
        </tr>
      </tbody>
    </table>
  </div> -->
</template>
