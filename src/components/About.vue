<template>
  <div class="container">
    <section class="shadow my-5 p-3">
        <div class="about py-3">
            <h5 class="fw-bold">About this project</h5>

            <p class="text-muted" v-for="text in texts" :key="text.id">
                {{text.text}}
            </p>
        </div>

        <div v-for="val in boxes" :key="val.id" class="box border rounded p-3 d-flex flex-column mb-3 gap-3">
            <div class="box-header d-md-flex align-items-md-center justify-content-md-between">
                <p class="p-0 m-0 fw-bold">{{val.title}}</p>
                <span style="font-size: 12px;">{{val.sub}}</span>
            </div>

            <p class="text-muted m-0">{{val.text}}</p>

            <div class="price d-md-flex align-items-md-center justify-content-md-between">
                <p class="text-muted"><span class="fw-bold fs-1 text-black">{{val.value}}</span> left</p>

                <a href="#" class="btn btn-primary">Selected Reward</a>
            </div>
        </div>
    </section>
  </div>
</template>

<script>
export default {
    data() {
        return {
            texts: [
                {text: "The Mastercraft Bamboo Monitor Riser is a sturdy and stylish platform that elevates your screen to a more comfortable viewing height. Placing your monitor at eye level has the potential to improve your posture and make you more comfortable while at work, helping you stay focused on the task at hand."},

                {text: "Featuring artisan craftsmanship, the simplicity of design creates extra desk space below your computer to allow notepads, pens, and USB sticks to be stored under the stand."},
            ],

            boxes: [
                {title: "Bamboo Stand", sub: "Pledge $25 or more", text: "You get an ergonomic stand made of natural bamboo. You've helped us launch our promotional campaign, and you’ll be added to a special Backer member list.", value: "101"},

                {title: "Black Edition Stand", sub: "Pledge $75 or more", text: "You get a Black Special Edition computer stand and a personal thank you. You’ll be added to our Backer member list. Shipping is included.", value: "64"},

                {title: "Mahogany Special Edition", sub: "Pledge $200 or more", text: "You get two Special Edition Mahogany stands, a Backer T-Shirt, and a personal thank you. You’ll be added to our Backer member list. Shipping is included.", value: "0"},
            ]
        }
    }
}
</script>

<style scoped>
section {
    background: #fff;
    border-radius: 15px;
    max-width: 400px;
    margin: 0 auto;
}

@media only screen and (min-width: 800px) {
    section {
        max-width: 700px;
    }
}
</style>