<template>
	<div class="common-layout">
		<el-container>
			<el-header>
				<div class="header-information">
					<img class="main-square" src="../assets/logo.png" />
				</div>
			</el-header>
			<el-main>
				<div class="header-operation">
					<el-button size="mini" type="success">创建房间</el-button>
				</div>
				<el-table
					:data="testData"
					style="width: 100%">
					<el-table-column
						label="房号"
						width="180">
						<template #default="scope">
							<span style="margin-left: 10px">{{ scope.row.roomId }}</span>
						</template>
					</el-table-column>
					<el-table-column
						label="房间名称"
						width="180"
						>
						<template #default="scope">
						<div class="name-wrapper">
							<el-tag size="medium">{{ scope.row.roomName }}</el-tag>
						</div>
						</template>
					</el-table-column>
					<el-table-column label="房主名称">
						<template #default="scope">
							<p>{{ scope.row.Homeowners }}</p>
						</template>
					</el-table-column>
					<el-table-column label="房间类型">
						<template #default="scope">
							<p>{{ scope.row.roomType }}</p>
						</template>
					</el-table-column>
					<el-table-column label="密码">
						<template #default="scope">
							<template v-if="scope.row.passwrod == 'yes'">
								<i class="el-icon-lock"></i>
							</template>
							<template v-else>
								<i class="el-icon-unlock"></i>
							</template>
						</template>
					</el-table-column>
					<el-table-column label="人员">
						<template #default="scope">
							<p>{{ scope.row.personnel }}</p>
						</template>
					</el-table-column>
					<el-table-column label="房间状态">
						<template #default="scope">
							<p>{{ scope.row.roomState }}</p>
						</template>
					</el-table-column>
					<el-table-column label="操作">
						<template #default="scope">
							<el-button
								size="mini"
								type="primary"
								@click="handleEdit(scope.$index, scope.row)">进入房间</el-button>
						</template>
					</el-table-column>
				</el-table>
				<div
					class="main-pargination">
					<el-pagination
						background
						layout="prev, pager, next"
						:total="1000">
					</el-pagination>
				</div>
				
			</el-main>
			<el-footer>
				
			</el-footer>
		</el-container>
	</div>
</template>

<script>
 export default {
	data() {
		return {
			size: 16,
			squareUrl: '../assets/logo.png',
			tableData: [{
				date: '2016-05-02',
				name: '王小虎',
				address: '上海市普陀区金沙江路 1518 弄'
			}, {
				date: '2016-05-04',
				name: '王小虎',
				address: '上海市普陀区金沙江路 1517 弄'
			}, {
				date: '2016-05-01',
				name: '王小虎',
				address: '上海市普陀区金沙江路 1519 弄'
			}, {
				date: '2016-05-03',
				name: '王小虎',
				address: '上海市普陀区金沙江路 1516 弄'
			}],
			testData: [
				{
					roomId: '1',
					roomName: '测试房间号1',
					Homeowners: '房主1',
					roomType: '斗地主',
					passwrod: 'yes',
					personnel: '1/3',
					roomState: '准备',
				},
				{
					roomId: '2',
					roomName: '测试房间号2',
					Homeowners: '房主2',
					roomType: '斗地主',
					passwrod: 'yes',
					personnel: '2/3',
					roomState: '准备',
				},
				{
					roomId: '3',
					roomName: '测试房间号3',
					Homeowners: '房主3',
					roomType: '斗地主',
					passwrod: 'yes',
					personnel: '3/3',
					roomState: '游戏',
				}
			]
		}
	},
	methods: {
		handleEdit(index, row) {
			console.log(index, row);
		},
		handleDelete(index, row) {
			console.log(index, row);
		}
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
		height: calc(100vh - 200px);
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
</style>
