# Vue 

  ## MVVM(Model-View-ViewModel)的理解

     1.Model代表数据模型，也可以在Model中定义数据修改和操作的业务逻辑

     2.View 代表UI 组件，它负责将数据模型转化成UI 展现出来

     3.ViewModel 监听模型数据的改变和控制视图行为、处理用户交互，简单理解就是一个同步View 和 Model的对象，连接Model和View

     Model和View。在MVVM架构下，View 和 Model 之间并没有直接的联系，而是通过ViewModel进行交互，Model 和 ViewModel 之间的交互是双向的， 因此View 数据的变化会同步到Model中，而Model 数据的变化也会立即反应到View 上。ViewModel 通过双向数据绑定把 View 层和 Model 层连接了起来，而View 和 Model 之间的同步工作完全是自动的，无需人为干涉，因此开发者只需关注业务逻辑，不需要手动操作DOM, 不需要关注数据状态的同步问题，复杂的数据状态维护完全由 MVVM 来统一管理

  ## 生命周期
     
     1.beforeCreate（创建前） 在数据观测和初始化事件还未开始

     2.created（创建后） 完成数据观测，属性和方法的运算，初始化事件，$el属性还没有显示出来

     3.beforeMount（载入前） 在挂载开始之前被调用，相关的render函数首次被调用。实例已完成以下的配置：编译模板，把data里面的数据和模板生成html。注意此时还没有挂载html到页面上。

     4.mounted（载入后） 在el 被新创建的 vm.$el 替换，并挂载到实例上去之后调用。实例已完成以下的配置：用上面编译好的html内容替换el属性指向的DOM对象。完成模板中的html渲染到html页面中。此过程中进行ajax交互。beforeUpdate（更新前） 在数据更新之前调用，发生在虚拟DOM重新渲染和打补丁之前。可以在该钩子中进一步地更改状态，不会触发附加的重渲染过程

     5.updated（更新后） 在由于数据更改导致的虚拟DOM重新渲染和打补丁之后调用。调用时，组件DOM已经更新，所以可以执行依赖于DOM的操作。然而在大多数情况下，应该避免在此期间更改状态，因为这可能会导致更新无限循环。该钩子在服务器端渲染期间不被调用

     6.beforeDestroy（销毁前） 在实例销毁之前调用。实例仍然完全可用

     7.destroyed（销毁后） 在实例销毁之后调用。调用后，所有的事件监听器会被移除，所有的子实例也会被销毁。该钩子在服务器端渲染期间不被调用

     什么是vue的生命周期：Vue 实例从创建到销毁的过程，就是生命周期。从开始创建、初始化数据、编译模板、挂载Dom→渲染、更新→渲染、销毁等一系列过程，称之为 Vue 的生命周期

     vue生命周期总共有几个阶段：它可以总共分为8个阶段：创建前/后, 载入前/后,更新前/后,销毁前/销毁后

     第一次页面加载会触发哪几个钩子：beforeCreate, created, beforeMount, mounted

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