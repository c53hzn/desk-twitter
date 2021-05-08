<template>
  <footer>
    <p>Created with Vite.js & Vue.js <br>
    	Designed by  
    	<a href="https://www.houzhenni.com" target="_blank" class="no-decor-link">
    		<strong>Jenny HOU</strong>
	    	<i class="fa fa-github font-20"></i>
	    </a>
    </p>
    <div class="go-top" @click="toTop" :class="{'go-top-hidden': isHidden}">
        <div class="arrow"></div>
        <div class="stick"></div>
    </div>
  </footer>
</template>

<script type="text/javascript">
export default {
	data() {
		return {
			isHidden: true
		}
	},
	methods: {
		toTop: function() {
			document.querySelector(".desk-wrap").scrollIntoView({behavior: 'smooth'})
		}
	},
	mounted: function() {
		var that = this;
		window.addEventListener("scroll", function(){
			if (window.scrollY > 199) {
				that.isHidden = false;
			} else {
				that.isHidden = true;
			}
		});
	}
}
</script>

<style type="text/css">
.go-top {
    opacity: 0.6;
    position: fixed;
    bottom: 40px;
    right: 20px;
    border: 1px solid gray;
    width: 38px;
    height: 38px;
    background-color: rgba(249, 249, 249, 1);
    border-radius: 3px;
    cursor: pointer;
    transition: opacity .3s;
}
.go-top:hover {
    opacity: 1;
}
.go-top .arrow {
    position: absolute;
    left: 10px;
    top: -1px;
    width: 0;
    height: 0;
    border: 9px solid transparent;
    border-bottom-color: gray;
}
.go-top .stick {
    position: absolute;
    left: 15px;
    top: 15px;
    width: 8px;
    height: 14px;
    display: block;
    background-color: gray;
    -webkit-border-radius: 1px;
    -moz-border-radius: 1px;
    border-radius: 1px;
}
/* toTop button end */
.go-top-hidden {
	opacity: 0;
	display: none;
}
footer {
	padding: 20px;
	color: white;
	background: hsla(0, 0%, 20%, 1);
}
footer p {
	margin: 0 auto;
	font-size: 14px;
	text-align: center;
}
footer a {
	color: white;
	text-decoration: none;
}
.hidden {
	display: none;
}
</style>