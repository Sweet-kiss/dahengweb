<template>
  <div class="head">
     <div class="head_w">
       <div class="top_w">
          <div class="logo_w"><img src="./img/logo.png" alt=""></div>
          <div class="phone">
             <span><img src="./img/phone.png" alt=""></span>
             <span class="phone_number">15352532523</span>
          </div>
        </div>
     </div>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
.head_w {
	height: 80px;
	background-color: #f8f8f8;
	overflow: hidden;
}
.top_w {
	width: 1200px;
	overflow: hidden;
	height: 80px;
	margin: 0 auto;
}
.logo {
	width: 100px;
	height: 80px;
}
.logo_w {
	float: left;
}
.logo_w img {
	width: 100px;
	height: 60px;
	margin-top: 8px;
}
.phone {
	float: left;
	padding: 10px 20px;
}
.phone img {
	width: 40px;
	float: left;
	margin-top: 6px;
	margin-left: 20px;
}
.phone_number {
	display: inline-block;
	height: 70px;
	line-height: 45px;
	font-size: 27px;
	padding: 0px 15px;
	font-family: "Berlin Sans FB Dem";
	font-weight: bold;
	color: #fd9106;
}
</style>
