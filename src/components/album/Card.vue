<template>
  <div class="col">
        <div class="card shadow-sm">
            <!-- <svg class="bd-placeholder-img card-img-top" width="100%" height="225" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Placeholder: Thumbnail" preserveAspectRatio="xMidYMid slice" focusable="false"><title>Placeholder</title><rect width="100%" height="100%" fill="#55595c"></rect><text x="50%" y="50%" fill="#eceeef" dy=".3em">Thumbnail</text></svg> -->

            <img :src="card.imageUrl" />

            <div class="card-body">

                <textarea v-if="mode == 'EDIT'" v-model="card.content" />

                <p class="card-text" v-else>
                    {{card.content}}
                </p>

                <div class="d-flex justify-content-between align-items-center">
                    <div class="btn-group">
                    <button type="button" class="btn btn-sm btn-outline-secondary" @click="switchMode('VIEW')">View</button>
                    <button type="button" class="btn btn-sm btn-outline-secondary" @click="switchMode('EDIT')">Edit</button>
                    </div>
                    <small class="text-muted">9 mins</small>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['initCard'],
    data() {
        return {
            card: this.initCard,
            mode: 'VIEW'
        }
    },
    methods: {
        switchMode(mode) {
            this.mode = mode
        }
    }
}
</script>

<style>

</style>