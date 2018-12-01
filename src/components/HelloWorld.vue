<template>
	<div>
		<button @click="clickBtn">click</button>
		<van-dialog
			v-model="show"
			show-cancel-button
			:before-close="beforeClose"
		>
			<van-field
				v-model="username"
				label="用户名"
				placeholder="请输入用户名"
			/>
			<van-field
				v-model="password"
				type="password"
				label="密码"
				placeholder="请输入密码"
			/>
		</van-dialog>
	</div>
</template>

<script>
import { Dialog } from 'vant';
export default {
  name: 'HelloWorld',
  data () {
    return {
			show: false,
      username: '',
      password: ''
    }
	},
	methods:{
		beforeClose(action, done) {
      if (action === 'confirm') {
        setTimeout(done, 0);
      } else {
        done();
      }
    },
		clickBtn(){
			this.show= true
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
