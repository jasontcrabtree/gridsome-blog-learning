<script>
import PostList from "@/components/PostList";
import BgColumn from "@/components/BgColumn";

import { Pager } from "gridsome";

export default {
  components: {
    PostList,
    BgColumn,
    Pager
  },
  metaInfo: {
    title: "Blog: Jason is writing words online"
  }
};

console.log("mroe blogs");
</script>

<page-query>
query ($page: Int) {
  allPost(perPage: 999, page: $page) @paginate {
    pageInfo {
      totalPages
      currentPage
    }
    edges {
      node {
        id
        title
        date (format: "D MMMM YYYY")
        path
        description
      }
    }
  },
    metadata {
    siteName
    siteDescription
  }
}
</page-query>

<template>
  <layout>
    <main class="blog-main">
      <header>
        <h1>Personal Blog</h1>
        <p class="large-paragraph-text">
          A personal and professional blog by
          <a
            href="http://twitter.com/jasontcrabtree"
          >@jasontcrabtree.</a>
          I write about learning Product Design and Development and strategy analysis focused on design in business and society.
        </p>
      </header>

      <section class="blog-list-section--layout">
        <h2>Latest Posts:</h2>

        <ul class="posts">
          <PostList v-for="edge in $page.allPost.edges" :key="edge.node.id" :post="edge.node" />
        </ul>
        <Pager
          class="pager-component--style"
          :info="$page.allPost.pageInfo"
          :showNavigation="false"
          :showLinks="true"
        />
      </section>
    </main>
    <BgColumn />
  </layout>
</template>

<style scoped>
.pager-component--style {
  display: flex;
  justify-content: flex-start;
  justify-content: center;
  font-weight: 500;
}

.pager-component--style > * {
  text-decoration: none;
  padding: 4px 32px;
  border-radius: 4px;
  margin: 0px 16px;
}

.pager-component--style > .active {
  background: #3d36b2;
  color: white;
}

.pager-component--style > *:last-child {
  margin-right: 0px;
}

.blog-main {
  grid-column: 2 / 9;
}

.blog-main > header > * {
  margin-bottom: var(--size-32);
}

.blog-main > * {
  margin: var(--size-32) 0px;
}
</style>
