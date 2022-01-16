<template>
  <div class="container">
    <div class="image_container">
      <a :href="card.targetUrl">
        <img
          :src="require(`../assets/${this.card.imageUrl}`)"
          :alt="card.imageAlt"
      /></a>
    </div>
    <div class="user_continer">
      <img
        src="https://cdn.pixabay.com/photo/2016/08/08/09/17/avatar-1577909_960_720.png"
        :alt="user"
      />
      <p class="username">UserName</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    card: Object,
  },
  computed: {
    nullHandling: function () {
      if (this.card.postedBy) {
        if (this.card.postedBy.avatarUrl) {
          return require(`../assets/${this.card.postedBy.avatarUrl}`);
        } else {
          return "";
        }
      } else {
        return "";
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;

  .image_container {
    img {
      border-radius: 15px;
      max-width: 600px;
      max-height: 600px;
      object-fit: cover;
      border: 1px solid gray;
    }
  }

  .user_continer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-top: 10px;

    img {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      margin-right: 15px;
    }
  }
}
</style>