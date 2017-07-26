<template>
    <div>
        <h2>工作经历</h2>
                <el-form >
                    <div class="container" v-for="(work,index) in workHistory">
                        <el-form-item label="公司名称">
                            <el-input v-model="work.company"></el-input>
                        </el-form-item>               
                        <el-form-item label="工作内容">
                            <el-input type="textarea" v-model="work.dexc"></el-input>
                        </el-form-item>

                        <el-form-item label="工作时间">
                            <el-input v-model="work.time"></el-input>
                        </el-form-item> 
                        
                        <i class="el-icon-delete" v-on:click="removeworkHistory(index)"></i>
                        <hr>
                        <p style="padding:8px 0"></p>
                    </div>
                    <el-button type="primary" v-on:click="addworkHistory">添加</el-button>                    
                </el-form>
    </div>
</template>
<script>
    export default {
        props: ['workHistory'],
        methods: {
            addworkHistory(){
                this.workHistory.push({
                    company: '',
                    dexc: '',
                    date1: '',
                    date2: '',
                })
            },
            removeworkHistory(index){
                this.workHistory.splice(index,1)
            },
        }
    }

</script>