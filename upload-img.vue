<template>
  <div class='finish_room'>
  	   <div class='finish_room2'>
       	   <div v-for='(item ,index ) in imgs' class='room_img'>
       	   	  <img :src="item">
       	   </div>
           <div class='room_add_btn'>
           	    <span>上传图片</span>
           	    <input @change='add_img'  type="file">
           </div>
       </div>
  </div>
</template>
<script >
	module.exports={
          data:function(){
          	  return{
                    imgs:[],
          	  }
          },
          props:{},
          methods:{
		 	  add_img(event){
		 	  	var reader =new FileReader();
		 	  	var img1=event.target.files[0];
                reader.readAsDataURL(img1);
                var that=this;
                reader.onloadend=function(){
                   	that.imgs.push(reader.result)    
				}
		 	  }
          }
		  

	}

</script>
<style scoped >
	 .finish_room{
		  width: auto;
		  height: auto;
	}
     .finish_room2{
   	 width: 100%;
   	 height: auto;
   	 padding-top: 15px;
   	 padding-bottom: 15px;
   	 display: flex;
   	 align-items: center;
   	  border-bottom: 2px solid #e1e1e1;
   }
   .finish_room2 .room_img{
   	 width: 150px;
   	 height: 100px;
   	 margin-right: 10px;
   	 position: relative;
   	 overflow: hidden;
   }
   .finish_room2 .room_img img{
   	 width: 100%;
   	 height: 100%;
   }
   .finish_room2>.room_img span{
   	  position: absolute;
   	  width: auto;
   	  height: auto;
   	  right: 5px;
   	  bottom:3px;
   }
   .room_add_btn{
   	width: 80px;
	height: 40px;
	border: 1px solid #e1e1e1;
	position: relative;
	line-height: 40px;
	text-align: center;
	background: #00a6c6;
	color: #fff;
	border-radius: 4px;
   }
  .room_add_btn input{
  	  position: absolute;
  	  top: 0px;
  	  left: 0px;
  	  width: 100%;
  	  height: 100%;
  	  z-index: 99999;
  	  opacity: 0;
  }

</style>