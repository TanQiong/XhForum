<template>
  <el-card class="list-nav-card">
      <!-- 根据路由的名称来获取高亮菜单index值，再将值赋予activeindex,elment的menu组件default-active属性据此来判断高亮选项 -->
    <el-menu class="listNav" :default-active="activeIndex" mode="horizontal">
      <el-menu-item index="1" v-if="type === 'main'" @click="$router.push({name: 'home'})">
        推荐
      </el-menu-item>
      <el-menu-item index="2" v-if="type === 'main'" @click="$router.push({name: 'hot'})">
        热榜
      </el-menu-item>
      <el-menu-item index="3" v-if="type === 'people'" @click="$router.push({name: 'peopleMain'})">
        回答
      </el-menu-item>
      <el-menu-item index="4" v-if="type === 'people'" @click="$router.push({name: 'peopleAsks'})">
        提问
      </el-menu-item>
      <el-menu-item index="5" v-if="type === 'people'" @click="$router.push({name: 'peopleArticles'})">
        文章
      </el-menu-item>
      <el-menu-item index="6" v-if="type === 'people'" @click="$router.push({name: 'peopleArticles'})">
        收藏夹
      </el-menu-item>
      <el-menu-item index="7" v-if="type === 'people'">
        <el-dropdown>
          <span class="el-dropdown-link">
            更多<i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>收藏夹</el-dropdown-item>
            <el-dropdown-item>关注</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </el-menu-item>
    </el-menu>
  </el-card>
</template>
<script>
export default {
  props: ['type'],
  data () {
    return {
      routerNametoIndex: {
        home: '1',
        hot: '2',
        peopleMain: '3',
        peopleAsks: '4',
        peopleArticles: '5'
      },
      activeIndex: '1'
    }
  },
  mounted () {
    this.activeIndex = this.routerNametoIndex[this.$route.name]
  }
}
</script>
