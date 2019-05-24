# Vue 

  ## 动态样式绑定
    
    1.class绑定:class="['contact-item',{'bge':item.istop===1}]"

    2.style绑定::style="msg.status==='0'?'justify-content:flex-end':''"

  ## 事件

    1.长按:@longpress

    2.点击:@click

    3.触摸开始:@touchstart

    4.触摸结束:@touchend @touchcancel

    5.触摸移动:@touchmove

    6.防止冒泡事件:@click.stop.prevent