<template>
    <el-row>
        <el-col :span="3">
            <el-menu
                    :default-active="this.$route.path !== '/admin' ? this.$route.path : '/admin/site'"
                    class="el-menu-vertical-demo"
                    :router="true">
                <el-menu-item index="/admin/site">
                    <i class="el-icon-setting"/>
                    <span slot="title">站点设置</span>
                </el-menu-item>
                <el-menu-item index="/admin/storage">
                    <i class="el-icon-s-operation"/>
                    <span slot="title">存储策略</span>
                </el-menu-item>
                <el-menu-item index="/admin/password">
                    <i class="el-icon-key"/>
                    <span slot="title">修改密码</span>
                </el-menu-item>
                <el-menu-item index="/admin/cache">
                    <i class="el-icon-collection"/>
                    <span slot="title">缓存管理</span>
                </el-menu-item>
                <el-menu-item index="/admin/api">
                    <i class="el-icon-document"/>
                    <span slot="title">API 文档</span>
                </el-menu-item>
            </el-menu>
        </el-col>
        <el-col :span="16">
            <keep-alive exclude="CacheManager,SiteSetting">
                <router-view/>
            </keep-alive>
        </el-col>
    </el-row>
</template>

<script>
    export default {
        name: "Index",
        data() {
            return {
                active: '/admin/storage'
            }
        }
    }
</script>

<style scoped>
    .el-row {
        height: 100vh;
    }
    .el-menu {
        height: 100vh;
    }
</style>