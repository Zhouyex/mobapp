<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <h1>s</h1> -->

    <div class="content" ref="searchBar">

      <div class="topinp">
        <!-- <input type="text" placeholder="输入内容"> -->
        <el-input v-model="input" placeholder="请输入内容" suffix-icon="el-icon-search"></el-input>
      </div>

      <h2>
        <van-button type="default">默认按钮</van-button>
        轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。
      </h2>
      <div class="flo" :class="searchBarFixed == true ? 'isFixed' :''">
        吸顶
      </div>
      <div class="flo-show " v-show="searchBarFixed">

      </div>
      <h2>提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。轻量应用服务器 （Simple Application Server），是可快速搭建且易于管理的轻量级云服务器；提供基于单台服务器的应用部署，安全管理，运维监控等服务，一站式提升您的服务器使用体验和效率。
      </h2>

      <div class="tabbar" id="fixedHeaderRoot">
        123
      </div>

    </div>

  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import { Button } from 'vant';
export default {
  name: "home",
  components: {
    // HelloWorld
    Button
  },
  data() {
    return {
      offsetTop: 0,
      offsetHeight: 0,
      headerFixed: false,
      searchBarFixed: false,
      input:""
    };
  },
  mounted() {
    // window.addEventListener("scroll", this.handleScroll(),true);


    this.box = this.$refs.searchBar;
    var $this = this;
    console.log(this.box)
    // 监听这个dom的scroll事件
    this.box.onscroll = () => {
      console.log("on scroll");
      $this.handleScroll();
    };
    // console.log(this.box.onscroll);
  },
  methods: {
    // handleScroll() {
    //   var scrollTop =
    //     window.pageYOffset ||
    //     document.documentElement.scrollTop ||
    //     document.body.scrollTop;
    //   console.log(scrollTop);
    // }

    handleScroll() {
      var scrollTop =
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop;

        // console.log(scrollTop)
      let box = this.$refs.searchBar;

      // console.log(
      //   "box.scrolltop:" + box.scrollTop + " box.offsetTop:" + box.offsetTop
      // );
      // console.log("box.scrolltop:" + box.scrollTop);
      console.log($('.flo').offset().top); //40  


      let tarjuli = $('.flo').offset().top; //距离

      if (box.scrollTop >= 400) {
      // if (tarjuli <= 40) {
        this.searchBarFixed = true;
        // console.log(this.searchBarFixed);
      } else {
        this.searchBarFixed = false;
      }
    }
  }
};
</script>

<style lang="less">
.home {
  width: 100%;
  height: 100%;
}

.topinp {
  width: 100%;
  height: 40px;
  background-color: pink;

  position: fixed;
  top: 0;
}

.tabbar {
  width: 100%;
  height: 40px;
  background-color: #777;

  position: fixed;
  bottom: 0;
}

.content {
  width: 100%;
  // height: calc(100% - 80px);
  height: 100%;

  overflow-y: scroll;

  background-color: #ccc;
  padding-top: 40px;
  padding-bottom: 40px;
}
.flo {
  width: 100%;
  height: 40px;
  background-color: #333;
  z-index: 999;
}
.flo-show {
  width: 100%;
  height: 40px;
  background-color: #333;
}
.isFixed {
  // position: fixed;
  position:sticky;
  background-color: #333;
  top: 40px;
  z-index: 999;
}
</style>
