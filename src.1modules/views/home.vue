<template>
    <div>
        <div>$store:{{$store.state.count}}</div>
        <!-- <div>$computed:{{getCount}}</div> -->
        <div>mapstate:{{count}}</div>
        <!-- <div>mapstatelist:{{list}}</div> -->


        <div>{{$store.getters.getList}}</div>
        <div>{{getList}}</div>
        <div>{{getLength}}</div>

        <div @click="addActions(5)">点击</div>
        <button @click="addlist({grade:'1610A',count:50})">添加</button>
        <my-add></my-add>
        <my-del></my-del>
    </div>  
</template>
<script>
import myAdd from '../components/add';
import myDel from '../components/del';
import {mapState,mapGetters,mapMutations,mapActions} from 'vuex'; 
export default {
    props:{

    },
    components:{
        myAdd,
        myDel
    },
    data(){
        return {

        }
    },
    computed:{
        // count(){
        //     return this.$store.list.file
        // },
        ...mapState(['count','list']),
        ...mapGetters(['getList','getLength'])
    },
    methods:{
        ...mapMutations(['addlist']),
        ...mapActions(['addActions']),
        // addActions(){
        //     this.$store.dispatch('',99);
        // }
    },
    created(){
        console.log(this);
    },
    mounted(){

    }
}
</script>
<style scoped lang="">

</style>
