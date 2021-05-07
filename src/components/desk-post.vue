<template>
	<div class="desk-unit">
    <div class="share main-color">
      <div class="media">
        <a target="_blank" :href="'https://www.facebook.com/sharer/sharer.php?u='+url"><i class="fa fa-facebook-f"></i></a>
      </div>
      <div class="media">
        <a target="_blank" :href="'http://twitter.com/share?url='+url"><i class="fa fa-twitter"></i></a>
      </div>
      <div class="media heart" @click="redHeart" :class="{'txt-red':isRed}">
        <i class="fa fa-heart"></i>
      </div>
    </div>
    <div>
      <div>
        <span class="author main-color">{{author}}</span>
        <span class="time">{{time}}</span>
      </div>
      <div class="content">
        <p v-for="(p,i) in content" :key="'p'+i">
          {{p}}
        </p>
      </div>
      <div class="picture" v-if="picture">
        <div class="img" v-for="(pic,i) in picture" :key="'pic'+i">
          <img :src="pic">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isRed: false
    }
  },
  props: {
    url: {
      type: String,
      required: true
    },
    author: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    },
    time: {
      type: String,
      required: true
    },
    content: {
      type: Array,
      required: true
    },
    picture: {
      type: Array,
    }
  },
  methods: {
    redHeart() {
      this.isRed = true;
    }
  }
}
</script>

<style>
.desk-unit {
  margin: 0px 0px 10px 0px;
  padding: 0px 0px 10px 0px;
  border-top: 2px solid rgba(192,192,192,0.4);
  display: flex;
  justify-content: flex-start;
}
.desk-unit .author {
  padding: 16px 0px 16px 0px;
  font-size: 24px;
  font-weight: bold;
}
.desk-unit .time {
  margin-left: 10px;
  color: silver;
}
.desk-unit .content p {
  text-align: justify;
}
.desk-unit .share {
  font-size: 24px;
}
.desk-unit .share .media {
  margin-right: 10px;
  text-align: center;
  background: rgba(192,192,192,0.4);
  cursor: pointer;
}
.desk-unit .share .media:hover {
  background: rgba(192,192,192,0.2);
  transition: background .5s;
}
.desk-unit .share .media a {
  padding: 10px;
  width: 100%;
  height: 100%;
  color: inherit;
  display: block;
}
.desk-unit .media.heart {
  padding: 10px;
}
.main-color {
  color: #182b54;
}
.txt-red {
  color: red;
}
.desk-unit .picture {
  display: flex;
  flex-wrap: wrap;
}
.desk-unit .picture .img {
  width: 33%;
  padding: 4px;
}
.desk-unit .picture .img img {
  width: 100%;
}

@media all and (max-width: 425px) {
  .desk-unit .time {
    margin-left: 0px;
    display: block;
  }
}
</style>