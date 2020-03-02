
# VUE整体布局
```
  import Ccc from './ccc'  //声明子组件
  export default {
    name: "App",
    data() {
      return {
          a:1,  //组件内申明变量
          b:2
      };
    },

    props:{  //接收父组件数据
      id: {
        type: String,
        default: 'chart'
      },
    },

    components:{  //声明子组件
      Ccc
    },

    computed:{  //计算属性
      c(){
        retrun this.a+this.b
      }
    }

    methods: {  //组件内方法
      //例如：
      abc:function(){
             
      }
    }，

    watch:{  //监听组件内某值变化
      abc(new,old){
      }
    }，

    mounted() { //模版挂载后执行（只执行一次）
      this.abc()
    },

    //不常用的生命周期
    beforeCreate(){//组件实例化完成，数据和事件还未加载时执行
    }，
    created(){//组件实例化完成，数据和事件加载完成时执行
    }，
    beforeUpdate(){//数据更新完成，但DOM还未更新的时候执行
    }，
    Updated(){//数据和DOM都更新完成后执行
    }
    beforeDestroy(){//开始销毁实例时调用
    }
    activated(){//需要配合动态组件 keep-live 属性使用。在动态组件初始化渲染的过程中调用该方法(未使用)
    }
  };
```
# 选项 /生命周期钩子
<details>
<summary>展开</summary>

周期|解释|个人理解|备注
---|:--:|:--:|:--:|
beforeCreate|在实例初始化之后，数据观测和事件配置之前调用|组件实例化完成，数据和事件还未加载|
created|实例创建完成之后被调用|组件实例化完成，并加载完数据和事件后|
beforeMount|在挂载开始之前被调用||
mounted|挂载到实例上之后再去调用钩子|模版编译挂载之后|在模版挂载后，只调用一次
beforeUpdate|数据更新时调用|更新数据，但并未更新DOM的时候|在data或props更新，并更新的数据或有关计算属性在DOM上有引用时，才会执行
updated|数据更新之后调用该钩子|数据和DOM都更新完成后|在data或props更新，并更新的数据或有关计算属性在DOM上有引用时，才会执行
activated|组件激活时调用||
deactivated|组件停用时调用||
beforeDestroy|实例销毁之前调用||
destroyed Vue|实例销毁之后调用||

</details>




# 选项/数据
<details>
<summary>展开</summary>

配置|解释|实例|
---|:--:|:--:|
data|实例的数据对象|`data() {return {a:1}},`|
props|接收来自父组件的数据|`props:{id: {type: String,default: 'chart'}}`|
propsData|只用于new创建的实例中|:--:|
computed|计算属性|`computed:{c(){retrun this.a+this.b}}`|
methods|组件内方法|`mounted(){this.abc()}`|
watch|监听组件内某值变化|`watch:{abc(new,old){}}`|

</details>



# v-指令
<details>
<summary>展开</summary>

指令|解释|
---|:--:|
v-text|更新元素的文本内容|
v-html|更新元素的innerHTML|
v-show|根据表达式之真假值，切换元素display css属性|
v-if|根据表达式的真假条件渲染元素|
v-else|为v-if 或者v-else-if 添加else块|
v-for|基于源数据多次渲染元素活模板块|
v-on|缩写@，绑定事件监听器，事件类型由参数指定|
v-bind|缩写：动态的绑定一个或多个特性|
v-model|在表单控件或者组件上创建双向数据绑定|
v-pre|跳过这个元素和它的子元素的编译过程|
v-cloak|这个指令保持在元素上直到关联实例编译结束|
v-once|只渲染元素和组件一次|

</details>



# 全局配置
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
silent|设置日志与警告|
optionMergeStrategies|合并策略|
devtools|配置是否允许vue-devtools|
errorHandler|错误追踪|
ignoredElements|忽略在Vue之外的自定义元素|
keyCodes|自定义键位别名|
performance|在浏览器中启用对组件初始化|
productionTip|启动时生成生产提示|　

</details>

# 全局API
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
Vue.extend(options)|创建构造器，参数是一个选项对象|
Vue.nextTick([callback,context])| 在下次更新DOM 更新循环之后执行延迟回调|
Vue.set(object,key,value)|设置对象的属性|
Vue.delete(object,key) |删除对象的属性|
Vue.directive(id,[definition])|注册或获取全局指令|
Vue.filter(id,[definition])|注册或获取全局过滤器|
Vue.component(id,[definition])|注册或获取全局组件|
Vue.use(plugin)|安装Vue.js 插件|
Vue.mixin(mixin)|全局混合|
Vue.compile(template)|在render函数中编译模板字符串|

</details>



# 选项/DOM
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
el |DOM元素作为|
template |字符串模板|
render| 字符串模板的替代方案|

</details>






# 选项 / 资源
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
dirctives Vue|实例可用指令的的哈希表|
filters Vue|实例可用过滤器的哈希表|
components vues|实例可用组件的哈希表|

</details>



# 选项/杂项
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
parent |指定已创建的实例之父实例|
mixins|选项接受一个混合对象的数组|
name|允许组件模板递归的调用自身|
extends |允许声明扩展另一个组件|
delimiters|改变纯文本插入分隔符|
functional|是组建无状态和无实例|　

</details>

# 实例属性
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
vm.$data Vue|实例观察的数据对象|
vm.$el Vue|实例使用的根DOM 元素|
vm.$options|用于当前Vue实例的初始化选项|
vm.$parent|父实例，如果当前实例有的话|
vm.$root|当前组件树的根Vue实例|
vm.$slots|用来访问被slot 分发的内容|
vm.$scopedSlots|一个对象，其中包含了所有拥有ref 注册的子组件|
vm.$isServer|当前Vue实例是否运行于服务器|

</details>



# 实例方法/数据
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
vm.$watch(expOrFn,callback,[options])|观察Vue 实例变化的一个表达式或计算属性
vm.$set(object,key,value)|这是全局Vue.set 的别名|
vm.$delete(object,key)|这是全局 Vue.delete 的别名|　　

</details>

# 实例方法/事件
<details>
<summary>展开</summary>

配置|解释|
---|:--:|
vm.on(event,callback)|监听当前实例上的自定义事件|
vm.$once(event,callback)|监听一个自定义事件，但只触发一次|
vm.$off([event,callback])|移除事件监听器|
vm.$emit(event,[...args])|触发实例上的事件|　　

</details>





# 特殊属性
<details>
<summary>展开</summary>

指令|解释|
---|:--:|
key|主要用于vue的虚拟DOM 算法|
ref|被用来给元素或子组件注册引用信息|
slot|用于标记往哪个slot中插入子组件的内容|

</details>




# 内置的组件
<details>
<summary>展开</summary>

指令|解释|
---|:--:|
component|渲染一个元素为动态组件|
transition|元素作为单个元素或组件的过度效果|
transition-group|元素作为多个元素/组件的过度效果|
keep-alive|主要用于保留组件状态或者避免重复渲染|
slot|元素作为组件模板之中的内容分发槽|

</details>
