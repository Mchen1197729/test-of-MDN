### 移动端适配的原理
    1.移动端的适配一般指的都是对元素的宽度和字体大小进行适配 不考虑高度的适配(如果高度超出,自动出现滚动条)
    
    2.一般移动端的设计稿都是以iphone6,7,8以基准来进行设计的.而iphone6,7,8这三款机型的理想视口(window.screen.width)都是375px  
      因此只需满足式子:设计稿上的元素的尺寸:设计稿上的基准值(375)=当前元素的尺寸:当前设备的理想视口  
    
    3.而每个元素的像素值如果希望根据不同的机型而计算出不同的像素 就只能使用rem作为单位 
      然后根据当前的设备的理想视口的宽度去动态计算根元素的字体大小
    
    4.例如:当前元素的尺寸 = 设计稿上元素的尺寸*当前设备的理想视口的宽度/375
      如果将html的font-size设置为:当前设备的理想视口的宽度/375*100 那么元素的尺寸就 = 设计稿上元素的尺寸/100rem  
      这样就可以通过动态的改变根元素的字体大小来实现移动端不同机型的适配了
