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
            id: this.$route.params .id
        }
    }
}
</script>