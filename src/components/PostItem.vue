<template>
  <article class="media">
    <figure class="media-left">
      <p class="image is-64x64">
        <img class="is-rounded" :src="`../../${post.node.author.image}`" />
      </p>
    </figure>
    <div class="media-content">
      <div class="content">
        <h2 class="title is-3">
          <g-link :to="post.node.path">
            {{ post.node.title }}
          </g-link>
        </h2>
        <p class="subtitle is-6">
          <g-link :to="post.node.author.path">{{ post.node.author.title }} </g-link>
        </p>
        <p>{{ post.node.excerpt }}</p>
      </div>
      <div class="tags">
        <span v-for="tag in post.node.tags" :key="tag.id">
          <div class="tag">
            <g-link :to="tag.path">
              {{ tag.id }}
            </g-link>
          </div>
        </span>
      </div>
      <nav class="level is-mobile">
        <div class="level-left">
          <a class="level-item">
            <span class="icon is-small"><i class="fas fa-reply"></i></span>
          </a>
        </div>
      </nav>
    </div>
  </article>
</template>

<script>
export default {
  props: { post: {} },
};
</script>

<style>
.tags {
  gap: 5px;
}
</style>
