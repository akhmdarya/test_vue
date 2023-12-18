<template>
  <div v-if="posts.length > 0">
    <h3>Cписок</h3>
    <transition-group
    name="post-list"
    >
      <PostItem
        v-for="post in posts"
        :key="post.id"
        @remove="$emit('remove', post)"
        :post="post"
      />
    </transition-group>
  </div>
  <h2 v-else-if="posts.length === 0" style="color: chocolate">
    список постов пуст
  </h2>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>

.post-list-item{
  display: inline-block;
  margin-right: 10px;
}
.post-list-enter-active,
.post-list-leave-active
{
transition: all 0.5s ease;
}
.post-list-enter-from,
.post-list-leave-to{
  opacity: 0;
  transform: translateX(130px);
}
.post-list-move{
  transition: transform 0.4s ease;
}
</style>
