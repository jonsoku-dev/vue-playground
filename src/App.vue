<template>
  <div>
    <keep-alive>
      <component :is="component"></component>
    </keep-alive>
    <button @click="component = 'form-register'">show register</button>
    <button @click="component = 'form-login'">show login</button>
  </div>
</template>

<script>
import FormRegister from '@/components/FormRegister'
import FormLogin from '@/components/FormLogin'

export default {

  name: 'App',
  data() {
    return {
      component: 'form-register'
    }
  },
  components: {
    'form-register' : FormRegister,
    'form-login' : FormLogin
  },
  methods: {
    scroll() {
      window.onscroll = () => {
        let bottomOfWindow = 
          document.documentElement.scrollTop + 
            window.innerHeight === document.documentElement.offsetHeight;
        if(bottomOfWindow) {
          console.log(bottomOfWindow, 'bottom')
          this.$nextTick(function() {
            if(this.component === 'form-login'){
              this.component = 'form-register'
            }else{
              this.component = 'form-login'
            }
          })
        }else {
          console.log(bottomOfWindow, 'not bottom')
        }
      }
    }
  },
  beforeCreate() {
    console.log(this.component, 'beforeCreate')
  },
  created() {
    // Data fetch 같은 렌더링이 되기 전에 실행되는 로직을 작성하는 곳
    console.log(this.component, 'created')
  },
  beforeMount() {
    console.log(this.component, 'beforeMount')
  },
  mounted() {
    // 사용자의 동작에 따른 로직을 작성하는 곳 
    console.log(this.component, 'mounted')
    this.scroll()
  },
  beforeUpdate() {
    console.log(this.component, 'beforeUpdate')
  },
  updated() {
    console.log(this.component, 'updated')
  }
}
</script>

