<template>
  <h1>Hello, {{ name }}</h1>
</template>

<script>
export default {
  asyncData({ $axios, params }) {
    return $axios.get(`users/${params.id}`)
      .then((res) => {
        return { name: res.data.name }
      })
  }
}
</script>