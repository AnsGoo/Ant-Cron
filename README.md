# Ant-cron

这是一个cron表达式生成插件,基于vue与Ant-desgin-vue实现

## 依赖
- Vue 2.0.0+
- ant-design-vue 1.4.4+

## 使用方式
```javascript
<a-form :form="form" @submit="handleSubmit">     
    <a-form-item
    :labelCol="labelCol"
    :wrapperCol="wrapperCol"
    label="cron表达式">
    <a-cron ref="innerVueCron" v-decorator="['cronExpression', {'initialValue':'0 0 0 2 * ?',rules: 
        [{ required: true, message: '请输入cron表达式!' }]}]"  @change="setCorn"></a-cron>
    </a-form-item>
</a-form>
...


setCorn(data){
    this.$nextTick(() => {
        this.form.setFieldsValue({cronExpression: data})
    })
}
```
## 参考项目

- [vue-cron](https://github.com/1615450788/vue-cron)

- [ant-design-vue 开发的cron表达式组件](https://blog.csdn.net/chizhuo9591/article/details/100732548)

## 改进点

- 解决了部分bug
    
## 联系方式

邮箱 : haiven_123@163.com

