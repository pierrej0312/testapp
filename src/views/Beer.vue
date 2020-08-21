<template>
<div>
    {{ id }}
</div>
</template>

<script>
export default {
    name: 'User',
    props: {

    },
    data() {
        return {
            beer: {}
        }
    },
    created() {
        let url = "https://api.punkapi.com/v2/beers/2"+this.$route.params.id
        this.$axios.get(url)
        .then(response => {
            this.beer = response.data[0]
        })
    },
}
</script>