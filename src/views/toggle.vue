<template>
  <div id="admin">
    <header class="head-top">用户中心</header>
    <section class="container">
      <aside class="nav">
        <ul class="list">
          <li v-for="item in routes" class="list-li">
            <router-link v-for="(child,index) in item.children" :key="index" :to="{path:child.path}">
              {{ child.alias }}
            </router-link>
          </li>
        </ul>
      </aside>
      <section class="content">
        <router-view></router-view>
      </section>
    </section>
  </div>
</template>

<script>
export default {
  name: 'admin',
  components:{

  },
  data(){
    return {
      routes:this.$router.options.routes
    }
  },
  methods:{
    
  }
}
</script>

<style lang="scss" scoped>
.wh{
  width:100%;
  height:100%;
}

#admin {
  @extend .wh;
  background:#ccc;
  .head-top{
    width:100%;
    height:60px;
    background:orange;
    text-align:center;
    font:bold 20px/60px "宋体";
  }
  .container{
    width:100%;
    height:100%;
    position:absolute;
    top:60px;
    left:0px;
    overflow:hidden;
    background:pink;
    display:flex;
    justify-content:flex-start;
    .nav{
      width:200px;
      height:100%;
      background:yellow;
      .list{
        @extend .wh;
        .list-li{
          list-style:none;
          width:100%;
          height:40px;
          a{
            text-decoration:none;
            display:block;
            width:100%;
            height:40px;
            border:2px solid #000;
          }
        }
      }
    }
    .content{
      flex:1;
      height:100%;
      background:red;
      font-size:50px;
      color:#fff;
    }
  }
}
</style>
