<template>
  <div id="login" style="position: relative">
    <div style="width: 300px;" class="login-box">

      <Tabs value="name1">

        <TabPane label="登录" name="name1">
          <Form ref="formInline" :model="formInline" :rules="ruleInline" inline >
            <FormItem prop="user" style="display: block" class="input">
              <Input type="text" v-model="formInline.user" placeholder="Username"  >
              <Icon type="ios-person-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <FormItem prop="password" style="display: block" class="input">
              <Input type="password" v-model="formInline.password" placeholder="Password" >
              <Icon type="ios-locked-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <FormItem>
              <Button type="primary" @click="handleSubmit('formInline')" class="btn">登录</Button>
              <p class="forgetPsd"><a >忘记密码？</a></p>
            </FormItem>
          </Form>
        </TabPane>

        <!--<TabPane label="标签二" name="name2">标签二的内容</TabPane>-->

        <TabPane label="注册" name="name2" class="" style="display: block">
          <Form ref="formInline" :model="formInline" :rules="ruleInline" inline>
            <FormItem prop="user" style="display: block" class="input">
              <Input type="text" v-model="formInline.user" placeholder="Username"  >
              <Icon type="ios-person-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <FormItem prop="user" style="display: block" class="input">
              <Input type="text" v-model="formInline.user" placeholder="phon/mail"  >
              <Icon type="ios-person-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
              <FormItem prop="password" style="display: block" class="input">
              <Input type="password" v-model="formInline.password" placeholder="Password" >
              <Icon type="ios-locked-outline" slot="prepend"></Icon>
              </Input>
            </FormItem>
            <FormItem >
              <Button type="primary" @click="handleSubmit('formInline')" class="btn" >注册</Button>
            </FormItem>
          </Form>
        </TabPane>
      </Tabs>


    </div>

  </div>
</template>


<script type="text/ecmascript-6">

  export default {
    data () {
       return {
         formInline: {
           user: '',
           password: ''
         },
         ruleInline: {
           user: [
             { required: true, message: '请填写用户名', trigger: 'blur' }
           ],
           password: [
             { required: true, message: '请填写密码', trigger: 'blur' },
             { type: 'string', min: 6, message: '密码长度不能小于6位', trigger: 'blur' }
           ]
         }
       }
    },

    beforeCreate () {
      console.group('beforeCreate 创建前状态===============》');
      console.log("%c%s", "color:red" , "el     : " + this.$el); //undefined
      console.log("%c%s", "color:red","data   : " + this.$data); //undefined
      console.log("%c%s", "color:red","message: " + this.message)
    },

    created () {
      console.group('created 创建完毕状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el); //undefined
      console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化
      console.log("%c%s", "color:red","message: " + this.message); //已被初始化
    },

    beforeMount () {
      console.group('beforeMount 挂载前状态===============》');
      console.log("%c%s", "color:red","el     : " + (this.$el)); //已被初始化
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化
      console.log("%c%s", "color:red","message: " + this.message); //已被初始化
    },

    mounted () {
      console.group('mounted 挂载结束状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el); //已被初始化
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data); //已被初始化
      console.log("%c%s", "color:red","message: " + this.message); //已被初始化
    },

    beforeUpdate () {
      console.group('beforeUpdate 更新前状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el);
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data);
      console.log("%c%s", "color:red","message: " + this.message);
    },

    updated () {
      console.group('updated 更新完成状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el);
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data);
      console.log("%c%s", "color:red","message: " + this.message);
    },

    beforeDestroy () {
      console.group('beforeDestroy 销毁前状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el);
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data);
      console.log("%c%s", "color:red","message: " + this.message);
    },

    destroyed () {
      console.group('destroyed 销毁完成状态===============》');
      console.log("%c%s", "color:red","el     : " + this.$el);
      console.log(this.$el);
      console.log("%c%s", "color:red","data   : " + this.$data);
      console.log("%c%s", "color:red","message: " + this.message)
    },

    methods: {
      handleSubmit(name) {
        this.$refs[name].validate((valid) => {
          if (valid) {
            this.$Message.success('提交成功!');
          } else {
            this.$Message.error('表单验证失败!');
          }
        })
      }
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped >


  .login-box {
    width: 300px;
    border: solid 1px #999;
    border-radius: 8px;
    position: absolute;
    top: 150px;
    left: calc(50% - 10px);
  }

  .input {
    padding: 0 10px 0 20px;
  }

  .btn {
    width: 200px;
    margin-left: 45px;
  }

  .forgetPsd {
    text-align: center;
    padding-left: 50px;
    line-height: 50px;

  }

  a{
    font-size: 14px;
    color: #666;

  }
  a:hover {
      color: blue;
    }
</style>
