<template>
    <div>
        <h2>个人信息</h2>

        <el-form v-bind:submit="onSubmit"><!--:label-position="labelPosition" label-width="80px" :model="profile">-->
            <el-form-item label="姓名">
                <el-input v-model="Profile.name"></el-input>
            </el-form-item>
            <el-form-item label="城市">
                <el-input v-model="Profile.city"></el-input>
            </el-form-item>
            <el-form-item label="出生日期">
                <el-input v-model="Profile.birth"></el-input>
            </el-form-item>
            
        </el-form>
    </div>
</template>
<script>
    export default {
        props: ['Profile']
    }

</script>