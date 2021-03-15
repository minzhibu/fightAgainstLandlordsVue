<template>
	<div>
		<div class="login-box">
			<div class="login-title">
				<span>登录 </span>·<span style="color: #969696;"> 注册</span>
			</div>
			<div class="login-user-name">
				账号
				<input />
			</div>
			<div class="login-password">
				密码
				<input />
			</div>
			<button class="button-login">登录</button>
			<div>
				<span class="small-text">注册账号</span>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		
	}
</script>

<style>
	*{
		padding: 0px;
		margin: 0px;
	}
	.login-box{
		box-shadow: 0 2px 4px rgb(0 0 0 / 12%), 0 0 6px rgb(0 0 0 / 4%);
		margin-left: 55%;
		margin-top: 10%;
		padding: 40px 70px;
		width: 280px;
		height: 280px;
		border-radius: 5px;
	}
	.login-box-parent{
	}
	.button-login{
		width: 100%;
		/* margin-left: 10%; */
		height: 35px;
		background: #2f7ef7;
		border-radius: 50px;
		border: 0px;
		color: white;
		font-size: 16px;
	}
	.login-title{
		font-size: 23px;
		font-weight: 900;
		color: #2f7ef7;
		margin-bottom: 30px;
		text-align: center;
	}
	.login-user-name{
		margin-bottom: 15px;
	}
	.login-password{
		margin-bottom: 20px;
	}
	.login-user-name input{
		height: 22px;
		width: 80%;
	}
	.login-password input{
		height: 22px;
		width: 80%;
	}
	.small-text{
		color: #393939;
		font-size: 12px;
	}
</style>
