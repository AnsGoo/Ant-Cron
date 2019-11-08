# Ant-cron

这是一个cron表达式生成插件,基于vue与Ant-desgin-vue实现

## 依赖
- Vue 2.0.0+
- ant-design-vue 1.4.4+

## 使用方式
```html
<a-form :form="form" @submit="handleSubmit">     
    <a-form-item
    :labelCol="labelCol"
    :wrapperCol="wrapperCol"
    label="cron表达式">
    <a-cron ref="innerVueCron" v-decorator="['cronExpression', {'initialValue':'0 0 0 2 * ?',rules: 
        [{ required: true, message: '请输入cron表达式!' }]}]"  @change="setCorn"></a-cron>
    </a-form-item>
</a-form>
```

```javascript

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

- 解决了当`cron`表达式中没有年份时，解析异常的bug
- 解决了当`cron`表达中指定时间为一个时间，例如：`0 0 0 2 * ?`，无法解析的bug
- 设置了年份最小值为当前年份的bug

## 版本通知

### 2019-11-8

- 修复了`* * * ? * 1#1 *`解析错误的bug
- 改进了单击输入框出现model层，改为单击图标出现model层
- 支持 `SUM` `MON` 等星期的写法的反向解析,大小写不敏感
- 支持 复制`cron`表达式进行反向解析

### 2019-11-6

-  创建项目，改进部分bug



## 联系方式

邮箱 : haiven_123@163.com

