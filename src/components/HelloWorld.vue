  <template>
  <div>
    <a-form :form="form" @submit="handleSubmit">     
      <a-form-item
        :labelCol="labelCol"
        :wrapperCol="wrapperCol"
        label="cron表达式">
        <a-cron ref="innerVueCron" v-decorator="['cronExpression', {'initialValue':'0 0 0 2 * ?',rules: 
          [{ required: true, message: '请输入cron表达式!' }]}]"  @change="setCorn"></a-cron>
      </a-form-item>
    </a-form>
  </div>
</template>

<script>
import ACron from "@/components/Acron";

export default {
  components: { ACron },
  data () {
    return {
      visible: false,
      formLayout: 'horizontal',
      form: this.$form.createForm(this, { name: 'coordinated' }),
      labelCol: {
          xs: { span: 5 },
          sm: { span: 5 },
          md: { span: 5 },
          lg: { span: 5 },
        },
        wrapperCol: {
          xs: { span: 14 },
          sm: { span: 14 },
          md: { span: 14 },
          lg: { span: 14 },
        },
    }
  },
  methods: {
    handleSubmit (e) {
      e.preventDefault()
      this.form.validateFields((err, values) => {
        if (!err) {
          console.log('Received values of form: ', values)
        }
      })
    },
    setCorn(data){
      if(data !== undefined){
        this.$nextTick(() => {
         this.form.setFieldsValue({cronExpression: data})
      })
      }
      
    }
  }
}
</script>
