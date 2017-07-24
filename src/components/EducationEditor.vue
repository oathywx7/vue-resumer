<template>
    <div>
        <h2>学习经历</h2>
                <el-form >
                        <el-form-item label="学校">
                            <el-input v-model="Education.school"></el-input>
                        </el-form-item>               
                        <el-form-item label="描述">
                            <el-input type="textarea" v-model="Education.content"></el-input>
                        </el-form-item>
                   
                </el-form> 
    </div>
</template>
<script>
    export default {
        props: ['Education'],
    }

</script>