Z-Stars 1.0 - 2014.07.09
★☆☆☆☆
=====================
一个评论星星儿的sass函数
  核心部分 
  (需要浏览器支持 calc()属性，之后会增加自定义星儿及修复兼容性)
  -------------------------------------------------------------
   1★ == 10% * 2 ; 5★ == 100% ; - (letter-spacing/2) 间距差值
   循环出 .st-1 至 .st-10 名字; 
   .st-1{width:calc(10% - (letter-spacing/2));}
   .st-10{width:calc(100% - (letter-spacing/2));}
  -------------------------------------------------------------
  
  // 默认变量
  -----------------
  $solid:     ☆☆☆☆☆!default;
  $hollow:    ★★★★★!default;
  @mixin stars(
        $size:      14px,       //大小
        $color:     #f80,       //前景色
        $bg-color:  $color,     //背景色
        $spacing:   4px,        //间距
        $bg-icon:   $solid,     //背景样式
        $icon:      $hollow     //前景样式   
    ){
      ...
    }
  
  
  // sass
  --------------------
  .stars{
    @include stars($size, $color, $bg-color, $spacing, $bg-icon, $icon){
        // Add Style
    };
  }
  // css
  -------------------
  .stars {
  ...
  font-size: 14px;
  }
  .stars:before, .stars:after {
    ...
    color: #ff8800;
    letter-spacing: 4px;
    content: "☆☆☆☆☆"; }
  .stars:after {
    ...
    color: #ff8800;
    content: "★★★★★"; }
  .stars.st-1:after {
    width: calc(10% - 2px ); }
  .stars.st-2:after {
    width: calc(20% - 2px ); }
  ...
  
  // html
  ------------------
    <span class="stars st-1"></span>
    <span class="stars st-2"></span>
    <span class="stars st-3"></span>
    ...
