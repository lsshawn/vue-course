<template>
  <div>
    <h3>Some User Details</h3>
    <p>User loaded: {{ $route.params.id }}</p>
    <router-link
      tag="button"
      class="btn btn-primary"
      :to="`/user/${$route.params.id}/edit`"
      >Edit user</router-link
    >
  </div>
</template>

