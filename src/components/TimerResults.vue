<template>
    <div>
        <p>Reaction time - {{ score  }} ms</p>
        <p class="rank"> {{ rank }}  </p>
    </div>
</template>


<script>

export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Good job"
        }
        else if (this.score < 300) {
            this.rank = "You sleept ?"
        }
        else {
            this.rank = "Time to wake up, go take a cofee"
        }
    }
}


</script>


<style>
    .rank {
        font-size: 1.4rem;
        color: #7fb2e6;
        font-weight: 700;
        text-decoration: underline;
        font-style: italic;
    }


</style>