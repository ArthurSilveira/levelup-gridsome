<template>
  <section>
    <h3>Latest Posts</h3>
    <article v-for="edge in $static.allBlogPost.edges" :key="edge.node.id">
      <h4>{{edge.node.title}}</h4>
      <p>{{edge.node.date}}</p>
      <p>{{edge.node.path}}</p>
      <a href="#">Read More</a>
    </article>
  </section>
</template>

<static-query>
  query LatestPosts {
    allBlogPost {
      edges {
        node {
          id
          title
          date (format:"MMM Do YYYY")
          path
        }
      }
    }
  }
</static-query>

