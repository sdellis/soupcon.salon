<template>
  <Layout>
    <div class="container" style="grid-column: 2 / span 1;">
      <h1>How to Help</h1>
      <div v-for="task in $page.tasks.edges" :key="task.id" class="task d-flex">
        <div class="task__img"
             :style="{ 'background-image': 'url(' + task.node.image + ')' }"></div>
        <div class="task__body">
          <g-link :to="task.node.path" class="task__link"></g-link>
          <h1 class="task__title">{{task.node.title}}</h1>
          <p class="task__abstract">{{task.node.abstract}}</p>
        </div>
      </div>
    </div>
  </Layout>
</template>
<page-query>
query {
  tasks: allTasks {
    edges {
      node {
        title
        abstract
        image
        path
      }
    }
  }
}
</page-query>
<script>
export default {
  metaInfo: {
    title: "My To-dos"
  }
};
</script>
<style>
.task {
  display: flex;
  align-items: center;
  box-shadow: 5px 5px 11px rgba(0, 0, 0, 0.15);
  border-radius: 8px;
  position: relative;
  margin-top: 50px;
  background-color: #fff;
}
@media screen and (max-width: 992px) {
  .task {
    display: block;
  }
}
.task__title {
  margin-top: 0;
}
.task__body {
  padding: 15px 30px;
}
.task__link {
  position: absolute;
  top: 0;
  right: 0;
  left: 0; 
  bottom: 0;
}
.task__img {
  width: 250px;
  height: 140px; 
  background-size: cover;
  background-position: center;
  border-radius: 8px;
  margin-right: 15px;
}
@media screen and (max-width: 992px) {
  .task__img {
    width: 100%;
    height: 180px;
  }
}
</style>