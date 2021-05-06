<template>
  <div class="resume-wrap main-content" v-if="posts.length">
    <DeskPost 
    author="Jenny Zhenni HOU" 
    v-for="(post,i) in posts" 
    :key="post.id"
    :id="post.id" :time="post.time" :content="post.content"
    ></DeskPost>
  </div>
</template>

<script>
import getDesk from './getdesk';
import config from './desk.config';
import yaml from "yaml";
import DeskPost from "./components/desk-post.vue";

export default {
	name: "desk",
	data() {
		return {
      posts: [
        {
          id: "",
          date: "",
          content: [
            ""
          ]
        }
      ]
		};
  },
	mounted() {
		this.loadPosts();
	},
	components: {
    DeskPost
	},
  computed: {
    // myPosts() {
    //   console.log(this.posts)
    //   return this.posts;
    // }
  },
  methods: {
  	loadPosts() {
  		var that = this;
      var paths = config.paths;
      var reqArr = [];
      for (let i = 0; i < paths.length; i++) {
        reqArr.push(getDesk(paths[i]));
      }
		  Promise.all(reqArr).then(arr=>{
        for (let m = 0; m < arr.length; m++) {
          arr[m] = yaml.parse(arr[m]);
        }
        that.posts = arr;
		  });
  	}
  }
};
</script>

<style type="text/css">
* {
	box-sizing: border-box;
}
.main-content {
  margin: 20px auto;
  padding: 20px 40px;
  width: 1080px;
  min-height: calc(100vh - 189px);
  background: white;
  border: 1px solid silver;
  border-radius: 5px;
}
@media (max-width: 1080px) {
	.main-content {
    margin: 0px;
    padding: 10px;
    width: auto;
    min-height: calc(100vh - 112px);
    border: none;
    border-radius: 0px;
	}   
}
.resume-wrap {
  position: relative;
}
.changeBtnOuter {
  margin-bottom: 10px;
  display: flex;
}
.changeBtns {
  flex:1 1 auto;
}
.changeBtns select {
	height: 20px;
}
.changeBtnOuter button {
	border-radius: 0px;
}
.changeBtn {
  margin-right: 5px;
}
.align-right {
  text-align: right;
}
</style>