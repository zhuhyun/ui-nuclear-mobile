<template>
    <WingBlank>
      <WhiteSpace></WhiteSpace>
        <Button @click.native="textonly">text only</Button>
      <WhiteSpace></WhiteSpace>
      <Button @click.native="withoutmask">without mask</Button>
      <WhiteSpace></WhiteSpace>
      <Button @click.native="cumstomicon">cumstom icon</Button>
      <WhiteSpace></WhiteSpace>
      <Button @click.native="toastsuccess">success</Button>
      <WhiteSpace></WhiteSpace>
      <Button @click.native="toastfail">fail</Button>
      <WhiteSpace></WhiteSpace>
      <Button @click.native="toastloading">loading</Button>
    </WingBlank>
</template>

<script>
  import Toast from '@/components/Toast'
  import WingBlank from '@/components/WingBlank'
  import Button from '@/components/Button'
  import WhiteSpace from '@/components/WhiteSpace'

  export default{
    components: {
      WingBlank,
      Button,
      WhiteSpace,
      Toast
    },
    data () {
      return {
        visible: true
      }
    },
    methods: {
      textonly () {
        Toast({
          message: '操作成功',
          duration: 2000,
          onClose: () => {
            console.log('onClose callback')
          }
        })
      },
      withoutmask () {
        Toast({
          message: 'Toast without mask',
          duration: 2000,
          mask: false
        })
      },
      cumstomicon () {
        Toast({
          iconClass: 'loading'
        })
      },
      toastsuccess () {
        Toast({
          iconClass: 'check',
          message: '操作成功'
        })
      },
      toastfail () {
        Toast({
          iconClass: 'cross',
          message: '操作失败'
        })
      },
      toastloading () {
        Toast({
          iconClass: 'loading',
          message: 'loading...'
        })
      }
    }
  }
</script>
