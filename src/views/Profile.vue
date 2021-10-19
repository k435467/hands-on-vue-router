<template>
  <div>
    <h3>My profile</h3>
    <h4>{{ $route.params.id }}</h4>
    <router-link :to="{ name: 'Profile', params: { id: 456 } }">
      go to profile456
    </router-link>
    <br />
    <br />
    <router-link
      :to="{ name: 'Profile', params: { id: 456 }, query: { plan: 'private' } }"
    >
      go to profile456 with url parameters
    </router-link>
    <h5>route.query: {{ $route.query }}</h5>
    <br />
    <br />
    <router-link :to="{ name: 'Info', params: { id: 789 } }">
      go to Info 789
    </router-link>
    <br />
    <br />
    <router-view />
  </div>
</template>

<script>
export default {
  name: "Profile",
  mounted() {
    console.log(this.$route.params.id);
  },
  watch: {
    $route(to, from) {
      console.log("to", to);
      console.log("from", from);
    },
  },
};
</script>
