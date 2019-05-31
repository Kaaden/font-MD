# Vue 

  ## MVVM(Model-View-ViewModel)的理解

     1.Model代表数据模型，也可以在Model中定义数据修改和操作的业务逻辑

     2.View 代表UI 组件，它负责将数据模型转化成UI 展现出来

     3.ViewModel 监听模型数据的改变和控制视图行为、处理用户交互，简单理解就是一个同步View 和 Model的对象，连接Model和View

     Model和View。在MVVM架构下，View 和 Model 之间并没有直接的联系，而是通过ViewModel进行交互，Model 和 ViewModel 之间的交互是双向的， 因此View 数据的变化会同步到Model中，而Model 数据的变化也会立即反应到View 上。ViewModel 通过双向数据绑定把 View 层和 Model 层连接了起来，而View 和 Model 之间的同步工作完全是自动的，无需人为干涉，因此开发者只需关注业务逻辑，不需要手动操作DOM, 不需要关注数据状态的同步问题，复杂的数据状态维护完全由 MVVM 来统一管理

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