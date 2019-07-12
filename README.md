# ec-dialog

#### 基于vue2.0开发弹窗项目，一个测试项目demo

## 使用方法

### 安装
    $ npm install ec-dialog
### 引入
    import dialog from 'ec-dialog'
    Vue.use(dialog)
### 基本使用

#### confirm
    this.$ec_confirm({
         title:'提示',
         content:'这里是提示内容',
         submitText:'提交',
         cancelText:'返回'
          }).then(()=>{
              //点击确定
              this.name='守候'
              alert(this.name)
          }).catch((err)=>{
            //点击取消
        })


#### alert
    this.$ec_alert({
            title:'提示2',
            content:'这里是提示内容2'
        }).then(()=>{
            this.name='守候'
            alert(this.name)
    })


#### tips
    this.$ec_tips({
        content:'点赞成功'
    })



#### loading
    let loadingContent = this.$ec_loading({
        content: '玩命加载中'
    });
    console.log(loadingContent)
    //两秒后关闭
    setTimeout(()=>{loadingContent.close();},2000)


#### 配置说明
* title-标题
* content-内容
* submitText-提交按钮文字（默认‘确定’）
* cancelText-取消按钮文字（默认‘取消’）

### dialog

    <ec-dialog :show="show" :title="'提示'">
            <div class="test">
                <table>
                    <tr>
                        <td>1</td>
                        <td>2</td>
                        <td>3</td>
                        <td>4</td>
                    </tr>
                    <tr>
                        <td>1</td>
                        <td>2</td>
                        <td>3</td>
                        <td>4</td>
                    </tr>
                    <tr>
                        <td>1</td>
                        <td>2</td>
                        <td>3</td>
                        <td>4</td>
                    </tr>
                    <tr>
                        <td>1</td>
                        <td>2</td>
                        <td>3</td>
                        <td>4</td>
                    </tr>
                </table>
                <div class="btn">
                    <ec-button :type="'main'" :value="'确定'" @click="submit"></ec-button>
                    <ec-button :type="'cancel'" :value="'取消'" @click="close"></ec-button>
                </div>
            </div>
        </ec-dialog>

js代码

        data(){
                return {
                    'name': 'index',
                    show:true
                }
            },
            methods:{
                close(){
                    alert('close')
                    this.show=false;
                },
                submit(){
                    alert('submit')
                    this.show=false;
                }
            },

#### 配置说明

show:是否显示

title:标题

#### 事件

close：窗口关闭时触发

### 主题颜色

窗口的样式，支持两种，默认情况和'tips'  //theme:'tips'


还有这种


    this.$ec_confirm({
        title:'提示',
        content:'这里是提示内容',
        submitText:'提交',
        cancelText:'返回',
        theme:'tips',//支持的样式'tips'
    }).then(()=>{
        this.name='守候'
        alert(this.name);
    }).catch((err)=>{
    })

默认是蓝色，如果想改变颜色，就多加一个十六进制的颜色值


    this.$ec_confirm({
        title:'提示',
        content:'这里是提示内容',
        submitText:'提交',
        cancelText:'返回',
        theme:'tips',
        color:'#f33'//选择红色主题
    }).then(()=>{
        this.name='守候'
        alert(this.name);
    }).catch((err)=>{
    })

### 动画方式

切换动画，现在支持5种

#### 默认情况

    this.$ec_alert({
        title:'提示2',
        content:'这里是提示内容2',
        color:'#f33',
        theme:'tips'
    }).then(()=>{
        this.name='守候'
        alert(this.name)
    })

#### 从上进入

    this.$ec_alert({
        title:'提示2',
        content:'这里是提示内容2',
        color:'#f33',
        theme:'tips',
        animation:'top-bounce',//从上进入动画
    }).then(()=>{
        this.name='守候'
        alert(this.name)
    })


#### 从下进入

    animation:'bottom-bounce',//从下进入动画


#### 从左进入

    animation:'left-bounce',//从左进入动画

#### 从右进入

    animation:'right-bounce',//从右进入动画

### button

#### 使用方式

<ec-button :type="'main'" :value="'确定'" @click="submit"></ec-button>

#### 配置说明
type:按钮类名  main(蓝)  |  cancel(白)  |  danger(红)  |  success(绿)

size:按钮尺寸  large（大型）  small(小型)    默认中等

value:按钮文字
## LICENSE
MIT




