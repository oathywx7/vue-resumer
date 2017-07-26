<template>
    <div>
        <h2>获奖证书</h2>
                <el-form >
                    <div class="container" v-for="(Trophy,index) in Trophy">
                        <el-form-item label="奖项">
                            <el-input v-model="Trophy.name"></el-input>
                        </el-form-item>               
                        <el-form-item label="描述">
                            <el-input type="textarea" v-model="Trophy.content"></el-input>
                        </el-form-item>
                        <i class="el-icon-delete" v-on:click="removeTrophy(index)"></i>
                        <hr>
                        <p style="padding:8px 0"></p>
                    </div>
                    <el-button type="primary" v-on:click="addTrophy">添加</el-button> 
                </el-form>  
    </div>
</template>
<script>
    export default {
        props: ['Trophy'],
        methods: {
             addTrophy(){
                this.Trophy.push({
                    name: '',
                    content: '',
                })
            },
            removeTrophy(index){
                this.Trophy.splice(index,1)
            }
        
    }
    }

</script>