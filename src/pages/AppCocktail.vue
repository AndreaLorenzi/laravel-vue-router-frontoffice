<script>
import CocktailsList from "../components/CocktailsList.vue";

export default {
  components: {
    CocktailsList,
  },
};
</script>

<template>
  <h1 class="pt-5 text-center">Cocktails List</h1>
  <div class="big_container mb-5 border-top">
    <CocktailsList />
  </div>
  <!-- PAGINATOR -->
  <nav class="nav_bar pb-5">
    <ul class="pagination">
      <li class="page-item" :class="{ disabled: currentPage === 1 }">
        <a class="page-link" href="#" @click="currentPage--">
          <span aria-hidden="true">&laquo;</span>
        </a>
      </li>
      <li
        v-for="page in nPages"
        :key="page"
        class="page-item"
        :class="{ active: page === currentPage }"
      >
        <a class="page-link" href="#" @click="currentPage = page">{{ page }}</a>
      </li>
      <li class="page-item" :class="{ disabled: currentPage === nPages }">
        <a class="page-link" href="#" @click="currentPage++">
          <span aria-hidden="true">&raquo;</span>
        </a>
      </li>
    </ul>
  </nav>

  <!-- Button trigger modal -->
  <!-- <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter">
  Launch demo modal
</button> -->

  <!-- Modal -->
  <div
    class="modal fade"
    id="exampleModalCenter"
    tabindex="-1"
    role="dialog"
    aria-labelledby="exampleModalCenterTitle"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLongTitle">Modal title</h5>
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label="Close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">...</div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">
            Close
          </button>
          <button type="button" class="btn btn-primary">Save changes</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.big_container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-inline: auto;
  padding-top: 5rem;
  max-width: 1000px;
  gap: 1rem;
}

.card_Container {
  width: calc(100% / 5);
}

.nav_bar {
  display: flex;
  justify-content: center;
}

a {
  color: rgb(180, 180, 180);
}

.big_container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin-inline: auto;
  padding-top: 5rem;
  max-width: 1000px;
  gap: 1rem;
}
</style>
