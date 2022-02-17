<template>
    <div :class="openModal === true ? 'd-block' : 'd-none'" class="backdrop">
        <div v-if="!modal" :class="openModal === true ? 'd-block' : 'd-none'" class="container">
            <div class="modal-mobile bg-white rounded">
                <div class="modal-header d-flex align-items-center">
                    <p class="p-0 m-0 fw-bold">Back this project</p>

                    <a @click="openModal = !openModal" href="#"><img src="/images/icon-close-modal.svg" alt="icon-close"></a>
                </div>

                <div class="modal-body">
                    <p class="text-muted">Want to support us in bringing Mastercraft Bamboo Monitor Riser out in the world.</p>

                    <div class="boxes">
                        <div @click="enableOptions1" :class="firstEl === true ? border : ''" class="box border rounded p-3 d-flex flex-column mb-3 gap-3">
                            <div class="box-header d-flex gap-3 align-items-center">
                                <input type="radio" :checked="firstEl">

                                <p class="m-0 fw-bold">Pledge without reward</p>
                            </div>

                            <p>
                                Choose to support us without a reward if you simply believe in our project. As a backer, you will be signed up to receive product updates via email.
                            </p>

                            <div v-if="firstEl" class="box-body border-top text-center">
                                <span class="mt-3 d-block text-muted">Enter your pledge</span>

                                <div class="buttons d-flex justify-content-center gap-4 mt-3">
                                    <a href="#" class="btn btn-primary" @click="btnContinue">Continue</a>
                                </div>
                            </div>
                        </div>

                        <div @click="enableOptions2" :class="secondEl === true ? border : ''" class="box border rounded p-3 d-flex flex-column mb-3 gap-3">
                            <div class="box-header d-flex gap-3 align-items-center">
                                <input type="radio" :checked="secondEl">

                                <p class="m-0 fw-bold d-flex flex-column">
                                    Bamboo Stand
                                    <span class="text-primary" style="font-size: 11px;">Pledge $25 or more</span>
                                </p>
                            </div>

                            <p>
                                You get an ergonomic stand made of natural bamboo. You've helped us launch our promotional campaign, and you’ll be added to a special Backer member list.
                            </p>

                            <p class="price fw-bold">
                                101
                                <span style="font-weight: normal;">left</span>
                            </p>

                            <div v-if="secondEl" class="box-body border-top text-center">
                                <span class="mt-3 d-block text-muted">Enter your pledge</span>

                                <div class="buttons d-flex justify-content-center gap-4 mt-3">
                                    <input type="number" min="25" class="w-25 p-1 rounded border" placeholder="$25">

                                    <a href="#" class="btn btn-primary" @click="btnContinue">Continue</a>
                                </div>
                            </div>
                        </div>

                        <div @click="enableOptions3" :class="thirdEL === true ? border : ''" class="box border rounded p-3 d-flex flex-column mb-3 gap-3">
                            <div class="box-header d-flex gap-3 align-items-center">
                                <input type="radio" :checked="thirdEL">

                                <p class="m-0 fw-bold d-flex flex-column">
                                    Black Edition Stand
                                    <span class="text-primary" style="font-size: 11px;">Pledge $75 or more</span>
                                </p>
                            </div>

                            <p>
                                You get a Black Special Edition computer stand and a personal thank you. You’ll be added to our Backer member list. Shipping is included.
                            </p>

                            <p class="price fw-bold">
                                64
                                <span style="font-weight: normal;">left</span>
                            </p>

                            <div v-if="thirdEL" class="box-body border-top text-center">
                                <span class="mt-3 d-block text-muted">Enter your pledge</span>

                                <div class="buttons d-flex justify-content-center gap-4 mt-3">
                                    <input type="number" min="75" class="w-25 p-1 rounded border" placeholder="$75">

                                    <a href="#" class="btn btn-primary" @click="btnContinue">Continue</a>
                                </div>
                            </div>
                        </div>

                        <div class="box border rounded p-3 d-flex flex-column mb-3 gap-3">
                            <div class="box-header d-flex gap-3 align-items-center">
                                <input type="radio" disabled>

                                <p class="m-0 fw-bold d-flex flex-column text-muted">
                                    Mahogany Special Edition
                                    <span style="font-size: 11px;">Pledge $200 or more</span>
                                </p>
                            </div>

                            <p class="text-muted">
                                You get two Special Edition Mahogany stands, a Backer T-Shirt, and a personal thank you. You’ll be added to our Backer member list. Shipping is included.
                            </p>

                            <p class="price fw-bold text-muted">
                                0
                                <span style="font-weight: normal;">left</span>
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div v-if="completed" class="container">
            <div class="modal-mobile modal-complete bg-white mx-auto rounded" style="max-width: 400px;">
                <div class="headerComplete text-center py-3">
                    <img src="/images/icon-check.svg" alt="">

                    <p class="fw-bold mt-3 fs-4">Thanks for your support!</p>

                    <p>
                        Your pledge brings us one step closer to sharing Mastercraft Bamboo Monitor Riser worldwide. You will get an email once our campaign is completed.
                    </p>

                    <a href="#" class="btn btn-primary" @click="openModal = !openModal">Got it!</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['openModal'],
    data() {
        return {
            clicked: false,
            firstEl: false,
            secondEl: false,
            thirdEL: false,
            modal: false,
            completed: false,
            active: false,
            border: "border-primary",
        }
    },

    methods: {
        enableOptions1() {
            this.firstEl = !this.firstEl
        },

        enableOptions2() {
            this.secondEl = !this.secondEl
        },

        enableOptions3() {
            this.thirdEL = !this.thirdEL
        },

        btnContinue() {
            this.modal = !this.modal;
            this.completed = !this.completed;
        },
    }
}
</script>

<style scoped>
.backdrop {
    position: absolute;
    background-color: rgba(0, 0, 0, 0.5);
    top: 0;
    left: 0;
    width: 100%;
    height: 159rem;
}

.modal-mobile {
    margin-top: 7rem;
}

@media only screen and (min-width: 800px) {
    .backdrop {
        height: 120rem;
    }
}
</style>