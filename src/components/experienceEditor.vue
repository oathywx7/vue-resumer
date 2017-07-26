<template>
    <div>
        <h2>项目经历</h2>
                <el-form >
                    <div class="container" v-for="(exper,index) in experience">
                        <el-form-item label="项目">
                            <el-input v-model="exper.project"></el-input>
                        </el-form-item>               
                        <el-form-item label="描述">
                            <el-input type="textarea" v-model="exper.content"></el-input>
                        </el-form-item>
                        <i class="el-icon-delete" v-on:click="removeexperience(index)"></i>
                        <hr>
                        <p style="padding:8px 0"></p>
                    </div>
                    <el-button type="primary" v-on:click="addexperience">添加</el-button> 
                </el-form>
    </div>
</template>
<script>
    export default {
        props: ['experience'],
        methods: {
            addexperience(){
                this.experience.push({
                    project: '',
                    content: '',
                })
            },
            removeexperience(index){
                this.experience.splice(index,1)
            },
        
    }
    }

</script>