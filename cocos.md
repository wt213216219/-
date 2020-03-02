this.node：该组件所属的节点实例
this.enabled：是否每帧执行该组件的 update 方法，同时也用来控制渲染组件是否显示
update(dt)：作为组件的成员方法，在组件的 enabled 属性为 true 时，其中的代码会每帧执行
lateUpdate：在所有组件的 update 都执行完之后才进行
onLoad()：组件所在节点进行初始化时（节点添加到节点树时）执行
start()：会在该组件第一次 update 之前执行，通常用于需要在所有组件的 onLoad 初始化完毕后执行的逻辑


this.node.active = false/true 设置节点的激活状态




var animation = this.node.getComponent(cc.Animation);
获取动画的播放总时长
var duration = animState.duration;
// 获取动画的播放时间
var time = animState.time;
animation.on('play',      this.onPlay,        this);
animation.on('stop',      this.onStop,        this);
animation.on('lastframe', this.onLastFrame,   this);
animation.on('finished',  this.onFinished,    this);
animation.on('pause',     this.onPause,       this);
animation.on('resume',    this.onResume,      this);