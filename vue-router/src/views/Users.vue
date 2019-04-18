<template>
   <v-layout
    row wrap pt-5 text-xs-center
    style="max-width:500px;margin:0 auto;"
   >
    <v-flex xs12>
        <h1>User</h1>
        <p>유저를 검색해 주세요.</p>
    </v-flex>
    <v-flex xs12>
        <v-text-field
            v-model="userId"
            label="유저 번호를 입력하세요."
        ></v-text-field>
        <v-btn @click="$router.push({
            name:'users-detail', 
            params: {
                id:userId
            }
        })">검색</v-btn>
        <v-flex xs12>
            <router-view></router-view>
        </v-flex>
    </v-flex>
   </v-layout>
</template>


<script>
export default {
    data(){
        return {
            userId:null
        }
    },
    beforeRouteEnter(to, from, next) {
        console.log('beforeEnter')
        next()
    },
    beforeRouteLeave(to, from, next) {
        console.log('before Leave')
        next()
    },
    created(){
        console.log(this.$router)
        console.log(this.$route)
        console.log('created')
    },
    destroyed(){
        console.log('destroyed')
    }

}
</script>
