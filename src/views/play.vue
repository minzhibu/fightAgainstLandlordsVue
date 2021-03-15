<template>
	<div class="common-layout" @mouseup="testup">
		<el-container>
			<el-header>
				<div class="header-information">
					<img class="main-square" src="../assets/logo.png" />
				</div>
			</el-header>
			<el-main>
				<div class="play-main">
					<div class="pre-play">
						<div class="pre-play-people">
							<img class="pre-play-people-img" draggable="false" src="../assets/1.jpg" />
						</div>
						<div class="pre-play-brand">
							<template v-for="n in testData.length - 1" :key="n">
								<Brand 
									:style="{top: ((n * 10)) + 'px','z-index': (n * 40),left: 0+'px'}" style="height: 125px;width: 85px;left: 4vw;"></Brand>
							</template>
						</div>
					</div>
					<div class="next-play">
						<div class="next-play-people">
							<img class="pre-play-people-img" draggable="false" src="../assets/1.jpg" />
						</div>
						<div class="next-play-brand">
							<template v-for="n in testData.length - 1" :key="n">
								<Brand 
									:style="{top: ((n * 10)) + 'px','z-index': (n * 40),left: 0+'px'}" style="height: 125px;width: 85px;left:40px"></Brand>
							</template>
						</div>
					</div>
					<div class="myself">
						<div class="myself-information">
							<div class="myself-button">
								<el-button type="success" plain>弃权</el-button>
								<el-button type="info" plain>出牌</el-button>
							</div>
							<div class="myself-people">
								<img class="myself-people-img" draggable="false" src="../assets/1.jpg" />
							</div>
							<div 
								class="myself-brand"
								@mousedown="testdown" >
								<template v-for="n in testData.length - 1" :key="n">
									<Brand 
										@mouseenter="testenter(n)" 
										@mousedown="testClick(n)"
										:style="{left: ((n * 40) + 160) + 'px','z-index': (n * 40),bottom: (testData[n] !=0 ? 10 : 0) + 'px'}" ></Brand>
								</template>
							</div>
						</div>
						<div class="myself-state">
							豆子:2000
							倍数:30
						</div>
					</div>
				</div>
			</el-main>
		</el-container>
	</div>
</template>

<script>
	import Brand from '../components/Brand.vue'
	export default {
	data() {
		return {
			squareUrl: '../assets/logo.png',
			testData: [
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0,
				0
			],
			mover: {state: false,num: 0},
		}
	},
	methods: {
		testenter(n){
			if(this.mover.state && this.testData[n] != this.mover.num){
				if(this.testData[n] != 0){
					this.testData[n] = 0;
				}else{
					this.testData[n] = this.mover.num;
				}
			}
		},
		testdown(){
			this.mover.state = true;
			let numTemp = Math.ceil(Math.random()*10) + 1;
			if(numTemp == this.mover.num){
				numTemp = Math.ceil(Math.random()*10) + 1;
			}
			this.mover.num = numTemp;
			console.log(numTemp);
		},
		testup(){
			this.mover.state = false;
		},
		testClick(n){
			this.testData[n] = this.testData[n] == 0? this.mover.num + 1 : 0;
		}
	},
	components:{
		Brand
	}
}
</script>

<style>
	*{
		padding: 0px;
		margin: 0px;
	}
	.el-header{
		height: 50px !important;
		padding: 10px;
		background-color: rgba(47,126,247,0.5);
	}
	
	.el-footer {
		position: fixed;
		height: 200px !important;
		width: 100vw;
		bottom: 0px;
		background-color: rgba(47,126,247,0.1);
	}
	.el-aside {
		background-color: #D3DCE6;
		color: #333;
		text-align: center;
		height: 250px;
	}

	.el-main {
		color: #333;
		text-align: center;
		padding: 0px;
		height: calc(100vh - 80px);
		margin-top: 6px;
	}
	.main-pargination{
		margin-top: 30px;
		margin-right: 20px;
		float: right;
	}
	.header-operation{
		float: right;
		margin-bottom: 5px;
	}
	.main-square{
    width: 29px;
    background-color: #fff;
    border-radius: 80px;
	}
	.header-information{
		float: right;
		margin-right: 5px;
	}
	.play-main{
		
	}
	.pre-play{
		height: 45vh;
		left: 0px;
		position: fixed;
		width: calc(25vw);
		min-width: 200px;
	}
	.next-play{
		height: 45vh;
		right: 0px;
		position: fixed;
		width: calc(25vw);
		min-width: 200px;
	}
	.myself{
		height: 45vh;
		bottom: 0px;
		position: fixed;
		width: 100vw;
	}
	.myself-information{
		height: 90%;
	}
	.myself-state{
		height: 6%;
		margin-top: 0.5%;
	}
	.myself-brand{
		height: 75%;
		display: inline-block;
		width: 88%;
		margin-left: 0px;
		position: relative;
	}
	.myself-people{
		height: 75%;
		display: inline-block;
		width: 11.5%;
		margin-left: 0px;
		position: relative;
	}
	.myself-button{
		height: 18%;
	}
	.myself-people-img{
    width: 11vw;
    height: 11vw;
    position: absolute;
    top: 7vh;
    left: 0px;
    border-radius: 50%;
    margin-left: 40%;
	}
	.pre-play > div{
		height: 100%;
		display: inline-block;
		width: 49%;
		float: left;
	}
	.next-play > div{
		height: 100%;
		display: inline-block;
		width: 49%;
		float: right;
	}
	.pre-play-brand{
		position: relative;
	}
	.pre-play-people-img{
		width: 11vw;
		height: 11vw;
		margin-top: 2vw;
		border-radius: 50%;
	}
</style>
