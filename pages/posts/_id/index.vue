<template>
        <SinglePost :post="singlePost"/>
</template>
<script>
import SinglePost from '@/components/posts/SinglePost'
import axios from 'axios'
export default {
    layout:"coreLayout",
    components:{
        SinglePost
    },
    asyncData(context){
        return axios.get("https://hp-up-bc8ae-default-rtdb.firebaseio.com/posts/"+context.params.id+".json")
                .then(res=>{
                    return {
                        singlePost:{
                            ...res.data,id:context.params.id
                        }
                    }
        }).catch(e=>context.error(e));
    }
}
</script>