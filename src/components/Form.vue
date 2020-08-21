<template>
    <div>
        <h1 v-show="alert">Bonjour {{last}} {{first}}</h1>
        <form action="">
            <input placeholder="email" type="mail">
            <input v-model="last" placeholder="lastname" type="text">
            <input v-model="first" placeholder="firstname" type="text">
            <textarea placeholder="comment" cols="30" rows="10"></textarea>
            <button @click.prevent="sendAlert">Envoyer</button>
            <router-link to="/" tag="button">Home</router-link>
        </form>
    </div>
</template>
<style lang="scss" scoped>
    form{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        input{
            margin-bottom: 10px;
        }
    }
</style>
<script>
export default {
    data(){
        return{
            last : "",
            first : "",
            alert : false
        }
    },
    methods : {
        sendAlert(){
            if(this.last != "" && this.first != ""){
                this.alert = true
                setTimeout(() => {
                    this.alert = false
                    // this.$router.push('/')
                    // this.$router.go(-1)
                    this.$router.push({name:'Home'})
                }, 1000);
            }
        }
    }
}
</script>