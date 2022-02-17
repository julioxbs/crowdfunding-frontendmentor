<template>
  <div class="container">
      <section class="top-info shadow px-3 py-5 text-center">
      <img class="icon" src="/images/logo-mastercraft.svg" alt="logo">

      <h1 class="fw-bold">Mastercraft Bamboo Monitor Riser</h1>

      <p>
          A beautiful handcrafted monitor stand to reduce neck and eye strain.
      </p>

      <div class="links d-flex align-items-center justify-content-center justify-content-md-between gap-3">
          <a href="#" class="btn btn-primary w-50" @click="openModal">Back this project</a>

          <a href="#"><img src="/images/icon-bookmark.svg" alt="icon-bookmark"></a>
      </div>
  </section>

  <div class="data w-100 shadow p-4">
      <section class="bottom-info">
            <p v-for="{values, text, id} in infos" :key="id" class="d-flex flex-column text-center gap-2">
                <span class="fs-1 fw-bold">{{values}}</span>
                <span>{{text}}</span>
            </p>
        </section>

        <div class="progress">
            <div class="progress-bar" role="progressbar" style="width: 75%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            infos: [
                {values: "$89,914", text: "of $100,00 backend", id: 1},
                {values: "5,007", text: "total backend", id: 2},
                {values: "56", text: "days left", id: 3},
            ]
        }
    }
}
</script>

<style scoped>
.top-info {
    /* position: fixed;
    top: 50%;
    left: 50%;
    transform: translateX(-50%); */
    transform: translateY(-15%);
    position: relative;
}

.data {
    border-radius: 15px;
}

.top-info,
.bottom-info {
    background-color: #fff;
    border-radius: 15px;
    max-width: 400px;
    margin: 0 auto;
}

.bottom-info .bar {
    background: cyan;
    width: 50%;
}

.icon {
    position: absolute;
    left: 45%;
    top: -8%;
}

@media only screen and (min-width: 800px) {
    .top-info,
    .bottom-info {
        background-color: #fff;
        border-radius: 15px;
        max-width: 700px;
        margin: 0 auto;
    }

    .bottom-info {
        display: flex;
        justify-content: center;
        gap: 2.5rem;
    }

    .data {
        max-width: 700px;
        margin: 0 auto;
    }
}
</style>