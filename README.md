# gowhere

> 去哪儿app2019112

##首页轮播插件 展示图标
##热销推荐  周末去哪儿 本地mock数据遍历
#热销推荐 点击进入 展示详情 递归遍历  点击图片轮播插件
####点击地址进入  地址 列表 输入框输入智能显示 匹配城市 点击跳转至首页 首页右侧地址变 vuex  列表每一项点击 也跳转 右侧 26字母列表 点击 滑动 都会跳转到对应字母城市




# proxyTable: {
      '/api': {
        target: 'http://localhost:8008',
 ##//wampserver 的端口号 把mock下面的json放到 www下面的api文件夹中


        // target: 'http://localhost:8080',
        // pathRewrite: {
        //   '^/api': '/static/mock'
        // }
      }
# mounted () {
    this.scroll = new Bscroll(this.$refs.search,{
      click:true
    })
#####用Bscroll的时候要加click才能点击



