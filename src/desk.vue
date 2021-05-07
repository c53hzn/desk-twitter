<template>
  <div class="desk-wrap">
    <main class="desk-main">
      <div class="banner main-color">
        <div class="upper">
          <span class="left"></span>
          <span>&nbsp;&nbsp;FROM THE DESK OF&nbsp;&nbsp;</span>
          <span class="right"></span>
        </div>
        <div class="lower">
          ZHENNI J. HOU
        </div>
      </div>
      <DeskPost 
      url="https://www.houzhenni.com/desk"
      author="Zhenni J. HOU" 
      v-for="(post) in posts" 
      :key="post.id"
      :id="post.id" :time="post.time" :content="post.content"
      :picture="post.picture"
      ></DeskPost>
    </main>
    <aside class="desk-side">
      <div class="main-color" id="my-info">
        <div class="silver-bg"></div>
        <div class="pic">
          <img src="https://www.houzhenni.com/img/mypic.png">
        </div>
        <div class="intro">
          自学前端开发，专业电商运营，熟练掌握 PS 和 Excel 的 72 种用法，欢迎来我的小站玩耍~
        </div>
      </div>
      <div class="support main-color-bg">
        <a target="_blank" href="https://afdian.net/@c53hzn">支持我</a>
      </div>
    </aside>
  </div>    
</template>

<script>
import getDesk from './getdesk';
import config from './desk.config';
import yaml from "yaml";
import DeskPost from "./components/Desk-Post.vue";

export default {
	name: "desk",
	data() {
		return {
      posts: []
		};
  },
	mounted() {
		this.loadPosts();
	},
	components: {
    DeskPost
	},
  methods: {
  	loadPosts() {
  		var that = this;
      getDesk(config.path).then(a=>{
        that.posts = yaml.parse(a).reverse();
      });
  	}
  }
};
</script>

<style type="text/css">
* {
	box-sizing: border-box;
}
.main-color {
  color: #182b54;
  border-color: #182b54;
}
.main-color-bg {
  background: #182b54;
}
.desk-wrap {
  margin: 10px auto;
  padding: 10px 0px;
  width: 800px;
  min-height: calc(100vh - 169px);
  display: flex;
  justify-content: space-between;
}
.desk-main {
  margin: 0px 10px 10px 0px;
  flex-grow: 1;
}
.desk-side {
  margin: 200px 0px 10px 20px;
  width: 200px;
}
.desk-main .banner {
  margin: 40px auto;
  width: 480px;
  text-align: center;
  font-weight: bold;
}
.desk-main .banner .upper {
  font-size: 24px;
  display: flex;
  justify-content: space-between;
}
.desk-main .banner .upper .left {
  border-top: 8px solid;
  border-left: 8px solid;
  border-top-left-radius: 8px;
  flex-grow: 1;
  transform: translateY(12px);
}
.desk-main .banner .upper .right {
  border-top: 8px solid;
  border-right: 8px solid;
  border-top-right-radius: 8px;
  flex-grow: 1;
  transform: translateY(12px);
}
.desk-main .banner .lower {
  padding: 10px;
  font-size: 40px;
  border-left: 8px solid;
  border-right: 8px solid;
  border-bottom: 8px solid;
}

#my-info {
  position: relative;
}
#my-info .silver-bg {
  position: absolute;
  top: 100px;
  width: 200px;
  height: 100px;
  background: rgba(192,192,192,0.4);
  z-index: -1;
}
#my-info:hover {
  border-color: black;
}
#my-info .pic {
  width: 200px;
  height: 200px;
  padding: 4px;
  background: white;
  border:1px solid;
  border-radius: 100%;
}
#my-info .pic img {
  width: 100%;
  display: block;
}
#my-info .intro {
  padding: 16px 10px;
  font-size: 15px;
  font-weight: bold;
  text-align: justify;
  background: rgba(192,192,192,0.4);
}
.desk-side .support {
  text-align: center;
}
.desk-side .support a {
  padding: 10px 0px;
  text-decoration: none;
  color: white;
  display: block;
}

@media all and (max-width: 1024px) {
  .desk-wrap {
    width: 800px;
  }
}
@media all and (max-width: 768px) {
  .desk-wrap {
    padding: 10px;
    width: 100%;
  }
  .desk-main .banner {
    margin: 0px auto 20px auto;
    width: 100%;
    font-size: 18px;
  }
}
@media all and (max-width: 425px) {
  .desk-wrap {
    flex-wrap: wrap;
  }
  .desk-main {
    margin: 0px;
    width: 100%;
  }
  .desk-side {
    margin: 10px auto;
    width: 100%;
  }
  #my-info {
    background: rgba(192,192,192,0.4);
  }
  #my-info .silver-bg {
    background: none;
  }
  #my-info .intro {
    background: none;
  }
  #my-info .pic {
    margin: 0px auto;
  }
}
</style>