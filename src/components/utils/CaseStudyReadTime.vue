<template>
  <aside>
    <p class="date-style">{{ $page.work.date }} | {{ readTime }} min read</p>
  </aside>
</template>

<page-query>
query Work ($path: String!) {
    work: work (path: $path) {
      image
        title
        content
        date (format: "D MMMM YYYY")
    }
}
</page-query>


<script>
export default {
  props: {
    readTime: { type: String }
  }
};
</script>

<style>
</style>