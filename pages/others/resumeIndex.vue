<!-- 个人简历 -->
<template>
	<view class="page">
		<scroll-view scroll-y="true" style="margin-bottom: 20px;">
			<view class="header">
				<view class="avatar">
					<image src="@/static/faces/resume.jpg"></image>
				</view>
				<view class="slogan">
					"<text>个人简历 </text>"
				</view>
			</view>
			<view class="job">
				求职意向:Java开发工程师
			</view>
			<view class="info">
				<view class="title">
					<text class="title_name">基本资料</text>
					<text class="title_line"></text>
				</view>
				<!-- 个人基本信息 -->
				<view class="info_content">
					<view class="info_item">
						姓名：{{userInfo.name}}
					</view>
					<view class="info_item">
						出生年月：{{userInfo.birthdate}}
					</view>
					<view class="info_item">
						性别：{{userInfo.gender}}
					</view>
					<view class="info_item">
						籍贯：{{userInfo.origin}}
					</view>
					<view class="info_item">
						学历：{{userInfo.education}}
					</view>
					<view class="info_item">
						专业：{{userInfo.major}}
					</view>
					<view class="info_item">
						tel：{{userInfo.tel}}
					</view>
					<view class="info_item">
						email：{{userInfo.email}}
					</view>
				</view>
			</view>
			
			<!-- 个人技能 -->
			<view class="list">
				<view class="title">
					<text class="title_name">技能</text>
					<text class="title_line"></text>
				</view>
				<view class="list_content">
					<view v-for="(item,index) in userInfo.skill_array" :key="index" class="list_item">
						- {{ item }}
					</view>
				</view>
			</view>
			
			<!-- 工作经历 -->
			<!-- 工作经历 -->
			<view class="list">
			  <view class="title">
			    <text class="title_name">工作经历</text>
			    <text class="title_line"></text>
			  </view>
			  <view class="list_content">
			    <view class="item_header">
			      <text class="header_name">公司名称</text>
			      <text class="header_position">岗位</text>
			      <text class="header_duration">工作时间</text>
			    </view>
			    <view v-for="(item, index) in userInfo.workExperience" :key="index" class="list_item">
			      <view class="item_content">
			        <text>{{ item.company }}</text>
			        <text>{{ item.position }}</text>
			        <text>{{ item.duration }}</text>
			      </view>
			    </view>
			  </view>
			</view>

			
			<!-- 项目经验 -->
			<view class="project-experience">
			    <view class="title">
			      <text class="title_name">项目经验</text>
			      <text class="title_line"></text>
			    </view>
			    <view class="project-list">
			      <view class="project-item" v-for="(project, index) in userInfo.projects" :key="index">
			        <view class="project-title">
			          <text class="project-name">{{ project.name }}: </text>
			          <text class="project-date">开发周期:{{ project.date }}</text>
			        </view>
			        <view class="project-content">
			          <view class="project-env">
			            <text class="label">开发环境:</text>
			            <text class="detail">{{ project.environment }}</text>
			          </view>
			          <view class="project-tech">
			            <text class="label">开发技术:</text>
			            <text class="detail">{{ project.technology }}</text>
			          </view>
			          <view class="project-desc">
			            <text class="label">项目描述:</text>
			            <text class="detail">{{ project.description }}</text>
			          </view>
			          <view class="project-responsibility">
			            <text class="label">责任描述:</text>
			            <text class="detail">{{ project.responsibilities }}</text>
			          </view>
			          <view class="project-tech-desc">
			            <text class="label">技术描述:</text>
			            <text class="detail">{{ project.technologyDescription }}</text>
			          </view>
			        </view>
			      </view>
			    </view>
			  </view>
			  
			<!-- 自我评价 -->
			<view class="self_evaluation">
			  <view class="title">
			    <text class="title_name">自我评价</text>
			    <text class="title_line"></text>
			  </view>
			  <view class="evaluation_content">
			    <view v-for="(item, index) in userInfo.selfEvaluation" :key="index" class="evaluation_item">
			      {{index + 1}} · {{ item }}
			    </view>
			  </view>
			</view>
			
			

		</scroll-view>
		
	</view>
</template>

<script>
	var app = getApp();
	export default {
		components: {
		},
		data() {
			return {
				userInfo: {
					// 基本信息
					name: '王哲',
					birthdate: '1997年06月',
					gender: '男',
					origin: '陕西西安',
					education: '本科',
					major: '通信工程',
					tel: '18391489943(同微信)',
					email: '18391489943@163.com',
					// 工作技能
					skill_array: ["熟练掌握 Java 语言，具有扎实的编程基础和良好的编程习惯以及代码规范。", "熟练使用 MySQL 数据库，熟悉 sql 指令和优化，了解MySQL的日志系统。", "熟悉 Spring、SpringMVC、Mybatis、Mybatis Plus、SpringBoot 等开源框架。", "熟悉 Redis 的原理和在项目中的使用。", "熟悉 SpringCloud、SpringCloudAlibaba的Nacos、sentinel、openfeign等组件。", "熟悉 Sa-Token、shiro、Spring Security 安全框架。", "熟悉 RabbitMQ、了解 RabbitMQ 的确认机制和延迟队列。", "熟悉 RocketMQ、了解其组成结构以及基础的使用。", "熟悉 Elasticsearch 全文搜索。", "熟悉 JVM 内存分布，常见垃圾回收算法。", "熟悉 Postman、jmeter、junit、swagger对接口进行测试。", "熟悉 Maven、Git 项目管理工具。", "熟悉 Linux、Docker。", "熟悉HTML、CSS、JS、JQ、JSP、VUE、微信小程序等前端技术。", "了解 SSH框架，Activity工作流引擎、Oracle数据库、PostgreSQL数据库。"],
					// 工作经历
					workExperience: [{
					  company: "北京金之盾",
					  position: "Java开发工程师",
					  duration: "2023.3 - 2024.8"
					}, {
					  company: "广东劲天科技",
					  position: "Java开发工程师",
					  duration: "2020.8 - 2022.12"
					}],
					// 项目经验
					projects: [{
					  name: "断流侦办",
					  date: "2022.10-2024.8",
					  environment: "IDEA+MAVEN+JDK1.8+Oracle+ClickHouse+Tomcat",
					  technology: "Springboot，MybatisPlus，Oracle，Quartz，Redis，vue3，Element-Plus",
					  description: "随着金融行业的快速发展，银行交易数据量日益增长，如何有效监管这些交易以防范金融风险和打击违法活动成为一项重要任务。同时，公安系统也需要对可疑人员进行筛选，以维护社会治安。为此，我们开发了这个系统。该系统的目标是通过对银行和公安系统中的标签进行分析，实现对用户的筛选和分类，以便发现潜在的违法交易行为。",
					  responsibilities: "参与项目的需求功能分析与建立数据库和该项目所用到的表。完成案件模块、涉毒涉赌模块，对应前端页面开发，接口开发，功能优化，bug修复，系统运维技术支撑等工作。完成前端功能组件封装，页面优化等工作。",
					  technologyDescription: "细聊。"
					},{
					  name: "一览招聘",
					  date: "2023.4-2024.8",
					  environment: "IDEA+MAVEN+JDK1.8+Mysql+Tomcat",
					  technology: "Springboot，MybatisPlus，MySQL，Redis，Dubbo，Quartz，RabbitMq，Uniapp",
					  description: "本项目旨在帮助企业高效地管理招聘流程，包括职位发布、简历筛选、面试安排等功能。",
					  responsibilities: "参与项目的需求功能分析的讨论。完成用户模块、聊天模块、用户标签模块前后端的设计开发。完成管理系统开发。",
					  technologyDescription: "细聊。"
					},{
					  name: "劲桩",
					  date: "2020.8-2022.12",
					  environment: "IDEA+MAVEN+JDK1.8+Mysql+Tomcat",
					  technology: "Springboot，MybatisPlus，MySQL，Redis，Elasticsearch，logstash，RabbitMq，Kibana",
					  description: "劲桩 -为用户精心打造的车生活生态智能平台,集合覆盖全市的充电网络,为广大新能源车主提供一键找桩,扫码充电,在线支付。本平台加速充电桩互联互通,有效提升充电桩运营效率和能源补给,减少碳排放。",
					  responsibilities: "参与充电桩项目的需求功能分析的讨论与建立数据库和该项目所用到的表。独立完成充电桩项目中优惠券模块，充电桩维修模块和充电桩搜索模块等功能。使用 Aop 技术完成日志监控。完成接口的单元测试,配合前端人员的数据对接,部分接口文档的书写。",
					  technologyDescription: "细聊。"
					}, {
					  name: "诊疗系统",
					  date: "2020.8-2022.12",
					  environment: "IDEA+MAVEN+JDK1.8+Mysql+Tomcat",
					  technology: "SpringBoot, Mybatis-Plus, Redis, Elasticsearch, logstash, Vant2, Minio, Sa-Token",
					  description: "诊疗是一款针对广大患者，提供在线咨询、看病、挂号、支付的健康类服务软件。为医院提供完整的医疗流程服务，使专家医师一对一健康指导服务，免去挂号难，排队久的困扰。提问流程简单便捷，让患者朋友随时随地地享受 VIP 健康咨询服务。",
					  responsibilities: "参与项目的需求分析的讨论以该项目所需数据库表的创建。完成患者端的挂号、问诊模块。完成医生端的接诊模块、发布百科文章，以及对话模块。完成医护人员的管理模块。参与 TRTC 视频问诊模块。使用AOP 技术完成日志监控。完成接口测试、医生端的前端页面的展示。",
					  technologyDescription: "细聊。"
					}, {
					  name: "OA 系统",
					  date: "2020.8-2022.12",
					  environment: "IDEA+MAVEN+JDK1.8+Mysql+Tomcat",
					  technology: "SpringBoot，SpringSecurity，Maven，MybatisPlus，Axios，ElementUI",
					  description: "该项目是包含流程、人事、沟通、财务等 10 多个功能模块的开发，并实现功能的前后端分离技术，办公管理功能的可视化配置化。",
					  responsibilities: "参与项目的需求功能分析的讨论与建立数据库和该项目所用到的表。独立完成项目中聊天模块、敏感词过滤模块、人事管理和安全框架的登录和权限校验模块。配合前端人员完成所负责功能模块页面的展示。编写接口文档和项目总结。",
					  technologyDescription: "细聊。"
					}, {
					  name: "企业采购管理系统",
					  date: "2020.8-2022.12",
					  environment: "IDEA+MAVEN+JDK1.8+Mysql+Tomcat",
					  technology: "Spring，SpringMVC，MyBatis, Shiro, Element-ui",
					  description: "采购管理系统是通过采购申请、采购订货、进料检验、仓库收料、采购退货、购货发票处理、供应商管理、价格及供货信息管理、订单管理，以及质量检验管理等功能综合运用的管理系统，对采购物流和资金流的全部过程进行有效的双向控制和跟踪，实现完善的企业物资供应信息管理。",
					  responsibilities: "参与企业采购管理系统的需求分析的讨论以该项目所需数据库表的创建。完成采购模块、审核模块、质检模块。使用 Element-ui 完成前端页面的显示。",
					  technologyDescription: "细聊。"
					}],
					// 个人优势
					selfEvaluation: ["本人对环境的适应能力强，能和周围的人沟通相处融洽，具有很强的团队精神", "在以往学习和工作中，对工作负责同时也能细心完成本职工作", "思维逻辑较强，思路清晰", "为人乐观开朗，对生活和工作抱着积极的态度", "对 bug 有基本的处理和解决能力"]
				},
			}
		},
		onLoad() {
			var me = this;
			
		},
		methods: {
			
		},
		// ... 其他页面配置
		onNavigationBarButtonTap(e) {
			// 判断是否是我们要处理的按钮
			if (e.index === 0) { // 假设这是第一个按钮
				// 使用uni.navigateTo进行页面跳转
				uni.navigateTo({
					url: '/pages/welcome/welcome' // 跳转的目标页面路径
				});
			}
		}
	}
</script>

<style>
	@import url("resume.css");
</style>