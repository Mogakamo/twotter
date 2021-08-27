<template>
  <div id="app">
    @{{ user.username }} <strong>Followers: </strong> {{ followers }}
    <button @click="followUser">Follow</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "m_ogakadev",
        firstName: "Amos",
        lastName: "Nyaburi",
        email: "com02519@uoeld.ac.ke",
        isAdmin: true,
      },
    };
  },

  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      if (oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.username} has gained a follower!`);
      }
    },
  },

  computed: {
    fullName() {
      return `${this.user.firstName} ${this.ueser.lastName}`;
    },
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },

  mounted() {
    this.followUser();
  },
};
</script>
