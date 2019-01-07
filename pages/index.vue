<template>
<div>
	<intro-text/>
	<hr>
	<el-row type="flex" justify="space-around" style="flex-flow: row wrap;">
		<h2>Techology</h2>
	</el-row>
    <el-row class="row-bg" type="flex" justify="space-around" style="flex-flow: row wrap; padding: 50px;">
      <h3 :sm="12" :lg="6"> Hardware <el-switch v-model="Hardware"></el-switch></h3>
      <h3 :sm="12" :lg="6"> Backend <el-switch v-model="Backend"></el-switch></h3>
      <h3 :sm="12" :lg="6"> Frontend <el-switch v-model="Frontend"></el-switch></h3>
    </el-row>
	<el-row type="flex" justify="space-around" style="flex-flow: row wrap;">
<!-- /*
 
 ██╗  ██╗ █████╗ ██████╗ ██████╗ ██╗    ██╗ █████╗ ██████╗ ███████╗
 ██║  ██║██╔══██╗██╔══██╗██╔══██╗██║    ██║██╔══██╗██╔══██╗██╔════╝
 ███████║███████║██████╔╝██║  ██║██║ █╗ ██║███████║██████╔╝█████╗  
 ██╔══██║██╔══██║██╔══██╗██║  ██║██║███╗██║██╔══██║██╔══██╗██╔══╝  
 ██║  ██║██║  ██║██║  ██║██████╔╝╚███╔███╔╝██║  ██║██║  ██║███████╗
 ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═════╝  ╚══╝╚══╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝
                                                                   
 
*/ -->
		<el-col v-if="Hardware" :sm="12" :lg="6">
				<h3>Hardware</h3>
				<el-radio-group v-model="hardware.devicetyp">
					<el-radio :label="0">Prototyp</el-radio> <br>
					<el-radio :label="1">Production grade</el-radio> <br>
					<el-radio :label="2">Mass market</el-radio><br>
				</el-radio-group><br>
				<el-checkbox v-model="hardware.customBoards">Custom boards</el-checkbox> <br>
				<el-checkbox v-model="hardware.customFirmware">Custom firmware</el-checkbox> <br>
				<el-checkbox v-model="hardware.externManufactures">Extern manufactures</el-checkbox> <br>
				<el-checkbox v-model="hardware.govermentRegulations">Possible goverment regulations</el-checkbox> <br>
		</el-col>
<!-- /*
 
 ██████╗  █████╗  ██████╗██╗  ██╗███████╗███╗   ██╗██████╗ 
 ██╔══██╗██╔══██╗██╔════╝██║ ██╔╝██╔════╝████╗  ██║██╔══██╗
 ██████╔╝███████║██║     █████╔╝ █████╗  ██╔██╗ ██║██║  ██║
 ██╔══██╗██╔══██║██║     ██╔═██╗ ██╔══╝  ██║╚██╗██║██║  ██║
 ██████╔╝██║  ██║╚██████╗██║  ██╗███████╗██║ ╚████║██████╔╝
 ╚═════╝ ╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═══╝╚═════╝ 
                                                           
 
*/ -->
		<el-col v-if="Backend" :sm="12" :lg="6">
			<h3>Backend</h3>
			<el-radio-group v-model="backend.hits">
				<el-radio :label="0">&lt; 250k hits/month</el-radio> <br>
				<el-radio :label="1">&lt; 1 million hits/month</el-radio> <br>
				<el-radio :label="2">>= 10 million hits/month</el-radio><br>
			</el-radio-group><br>
			<el-checkbox v-model="backend.database">Database</el-checkbox><br>
			<el-radio-group v-if="backend.database" v-model="backend.databaseEntries">
				<el-radio :label="0">&lt; 1 million entries</el-radio><br>
				<el-radio :label="1">&lt; 100 million entries</el-radio><br>
				<el-radio :label="2">>= 100 million entries</el-radio><br>
			</el-radio-group><br>
			<el-checkbox v-if="backend.database" v-model="backend.multipleDatabases">Multiple types of databases</el-checkbox> <br>
			<el-checkbox v-model="backend.payment">Payment handling</el-checkbox> <br>
			<el-checkbox v-model="backend.cloudhosted">Cloudhosted</el-checkbox> <br>
			<el-checkbox v-model="backend.legacycode">Legacy-Code</el-checkbox> <br>
			<el-checkbox v-model="backend.crawling">Crawling</el-checkbox> <br>			
			<el-checkbox v-model="backend.machineLearning">Machine Learning</el-checkbox> <br>
		</el-col>
<!-- /*
 
 ███████╗██████╗  ██████╗ ███╗   ██╗████████╗███████╗███╗   ██╗██████╗ 
 ██╔════╝██╔══██╗██╔═══██╗████╗  ██║╚══██╔══╝██╔════╝████╗  ██║██╔══██╗
 █████╗  ██████╔╝██║   ██║██╔██╗ ██║   ██║   █████╗  ██╔██╗ ██║██║  ██║
 ██╔══╝  ██╔══██╗██║   ██║██║╚██╗██║   ██║   ██╔══╝  ██║╚██╗██║██║  ██║
 ██║     ██║  ██║╚██████╔╝██║ ╚████║   ██║   ███████╗██║ ╚████║██████╔╝
 ╚═╝     ╚═╝  ╚═╝ ╚═════╝ ╚═╝  ╚═══╝   ╚═╝   ╚══════╝╚═╝  ╚═══╝╚═════╝ 
                                                                       
 
*/ -->
		<el-col v-if="Frontend" :sm="12" :lg="6">
			<h3>Frontend</h3>
				<el-radio-group v-model="frontend.staticSites">
					<el-radio :label="0">&lt; 15 static sites</el-radio> <br>
					<el-radio :label="1">&lt; 100 static sites</el-radio> <br>
					<el-radio :label="2">>= 100 static sites</el-radio><br>
				</el-radio-group><br>
				<el-radio-group v-model="frontend.interactiveComponents">
					<el-radio :label="0">&lt; 5 Interactive components</el-radio> <br>
					<el-radio :label="1">&lt; 30 Interactive components</el-radio> <br>
					<el-radio :label="2">>= 30 Interactive components</el-radio><br>
				</el-radio-group><br>
			<el-checkbox v-model="frontend.modernJsFramework">Modern js framework</el-checkbox> <br>
			<el-checkbox v-model="frontend.webApp">Web app</el-checkbox> <br>
			<el-checkbox v-model="frontend.dashboard">Dashboard</el-checkbox> <br>
			<el-checkbox v-model="frontend.userManagementSystem">User management system</el-checkbox> <br>
			<el-checkbox v-model="frontend.complexDesign">Complex design</el-checkbox> <br>
			<el-checkbox v-model="frontend.responsiveDesign">Responsive design</el-checkbox> <br>
			<el-checkbox v-model="frontend.seoOptimization">SEO optimization</el-checkbox> <br>
		</el-col>
<!-- /*
 
  ██████╗  ██████╗  ██████╗ ██████╗     ██████╗ ██████╗  █████╗  ██████╗████████╗██╗ ██████╗███████╗███████╗
 ██╔════╝ ██╔═══██╗██╔═══██╗██╔══██╗    ██╔══██╗██╔══██╗██╔══██╗██╔════╝╚══██╔══╝██║██╔════╝██╔════╝██╔════╝
 ██║  ███╗██║   ██║██║   ██║██║  ██║    ██████╔╝██████╔╝███████║██║        ██║   ██║██║     █████╗  ███████╗
 ██║   ██║██║   ██║██║   ██║██║  ██║    ██╔═══╝ ██╔══██╗██╔══██║██║        ██║   ██║██║     ██╔══╝  ╚════██║
 ╚██████╔╝╚██████╔╝╚██████╔╝██████╔╝    ██║     ██║  ██║██║  ██║╚██████╗   ██║   ██║╚██████╗███████╗███████║
  ╚═════╝  ╚═════╝  ╚═════╝ ╚═════╝     ╚═╝     ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝   ╚═╝   ╚═╝ ╚═════╝╚══════╝╚══════╝
                                                                                                            
 
*/ -->
		<el-col :sm="12" :lg="6">
			<h3>Good Practices</h3>
			<el-checkbox v-model="goodPractices.maintainedDocumentation">Well maintained documentation</el-checkbox> <br>
			<el-checkbox v-model="goodPractices.testingEnviroment">Testing environment</el-checkbox> <br>
			<el-checkbox v-model="goodPractices.unitAndIntegrationTesting">Unit and Integration Testing</el-checkbox> <br>
			<el-checkbox v-model="goodPractices.stagingEnviroment">Staging environment</el-checkbox> <br>
			<el-checkbox v-model="goodPractices.applicationMonitoring">Application monitoring</el-checkbox> <br>
			<el-checkbox v-model="goodPractices.securityChecks">Security Checks</el-checkbox> <br>
		</el-col>
	</el-row>
<!-- /*
 
 ████████╗███████╗ █████╗ ███╗   ███╗
 ╚══██╔══╝██╔════╝██╔══██╗████╗ ████║
    ██║   █████╗  ███████║██╔████╔██║
    ██║   ██╔══╝  ██╔══██║██║╚██╔╝██║
    ██║   ███████╗██║  ██║██║ ╚═╝ ██║
    ╚═╝   ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝
                                     
 
*/ -->
	<hr>
	<el-row type="flex" justify="space-around" style="flex-flow: row wrap;">
		<h2>Team</h2>
	</el-row>
	<el-row type="flex" align="middle" justify="center" style="flex-flow: row wrap;">
		<el-col :span="4" :xs="24" :sm="12" :md="4">
			<span style="padding-bottom: 15px;">Number of developers</span><br><br>
			<el-input-number v-model="team.numberDevelopers" size="mini" @change="handleChange()" :min="1" :max="8"></el-input-number>
		</el-col>
		<el-col :span="10" :xs="24" :sm="12" :md="8">
			<el-checkbox v-model="team.agileDevelopment">Agile development</el-checkbox> <br>
			<el-checkbox v-model="team.languageBarrier">Possible language barrier between developers and/or managers</el-checkbox> <br>
			<el-checkbox v-model="team.sameLocation">All Developers at same location</el-checkbox> <br>
			<el-checkbox v-model="team.outsourcedDevolopers">Outsourced developers</el-checkbox> <br>
			<el-checkbox v-if="team.outsourcedDevolopers" v-model="team.outsourcingNewbee">First time working with outsourced developers</el-checkbox> <br>
			<el-checkbox v-model="team.newTechnologies">Some team members are new to some technologies</el-checkbox> <br>
		</el-col>
	</el-row>
	<el-row>
		<el-row type="flex" justify="space-around" style="flex-flow: row wrap;" :gutter="24" class="row-bg">
		<el-col :span="8" :xs="24" :sm="12" :md="8" v-for="(developer, i) in team.developers" :key="developer.id">
					<h3>{{team.developers[i].name || 'Developer #' + (i+1)}}</h3>
					<el-input placeholder="Developer's name" v-model="team.developers[i].name" clearable></el-input>
					<div class="block">
						<span class="demonstration">Years of experience</span>
						<el-slider v-model="team.developers[i].experience" :step="1" :min="0" :max="8" show-stops show-input></el-slider>
					</div>
          <el-row class="row-bg" :gutter="10" type="flex" justify="space-around" style="flex-flow: row wrap; padding: 10px;">
            <el-radio v-model="team.developers[i].profession" border size="medium" label="Fullstack">Fullstack</el-radio>
            <el-radio v-model="team.developers[i].profession" border size="medium" label="Backend">Backend</el-radio>
            <el-radio v-model="team.developers[i].profession" border size="medium" label="Frontend">Frontend</el-radio>
          </el-row>
          <el-row class="row-bg" :gutter="10" type="flex" justify="space-around" style="flex-flow: row wrap; padding: 10px;">
            <el-radio v-model="team.developers[i].time" border size="medium" label="Fulltime">Fulltime</el-radio>
            <el-radio v-model="team.developers[i].time" border size="medium" label="Flexible">Flexible</el-radio>
            <el-radio v-model="team.developers[i].time" border size="medium" label="Halftime">Halftime</el-radio>
          </el-row>
           <el-row class="row-bg" :gutter="10" type="flex" justify="space-around" style="flex-flow: row wrap; padding: 10px;">
            <el-radio v-model="team.developers[i].payment" border size="medium" label="Well">Well payed</el-radio>
            <el-radio v-model="team.developers[i].payment" border size="medium" label="Fair">Fair payed</el-radio>
            <el-radio v-model="team.developers[i].payment" border size="medium" label="Low">Low payed</el-radio>
           </el-row>
		</el-col>
		</el-row>
	</el-row>
<!-- /*
 
  ██████╗██╗     ██╗███████╗███╗   ██╗████████╗
 ██╔════╝██║     ██║██╔════╝████╗  ██║╚══██╔══╝
 ██║     ██║     ██║█████╗  ██╔██╗ ██║   ██║   
 ██║     ██║     ██║██╔══╝  ██║╚██╗██║   ██║   
 ╚██████╗███████╗██║███████╗██║ ╚████║   ██║   
  ╚═════╝╚══════╝╚═╝╚══════╝╚═╝  ╚═══╝   ╚═╝   
                                               
 
*/ -->
		<el-row>
			<h2>Client</h2>
					<el-checkbox v-model="checked">Client | Inhouse | Private</el-checkbox> <br>
					<el-checkbox v-model="checked">Client is technologically illiterate</el-checkbox> <br>
			</el-row>
		<el-row>
			<h1>Result:</h1>
			Manhours: {{manHoursTotal}}
		</el-row>
  </div>
</template>

<script>
	import IntroText from '~/components/IntroText.vue';
	  class Developer {
		  constructor(name, profession, experience = 2, time, payment) {
			  this.name = name;
			  this.profession = profession;
			  this.experience = experience;
			  this.time = time;
			  this.payment = payment;
			  this.id = 0;
		  }
	  }

export default {
	components : {
		IntroText
	},
  data: function() {
        return {
			checked: true,
			Hardware: false,
			Backend: true,
			Frontend: true,
			manHoursTotal: 1,
			manhoursDelta : {
				frontend :0,
				backend: 0,
				overhead: 0
			},
			hardware : {
				devicetyp: 0,
				customBoards: false,
				customFirmware: false,
				externManufactures: true,
				govermentRegulations: false
			},
			backend: {
				hits: 0,
				database: true,
				databaseEntries: 0,
				multipleDatabases: false,
				payment: false,
				cloudhosted: false,
				legacycode: false,
				crawling: false,
				machineLearning: false,
			},
			frontend: {
				staticSites: 0,
				interactiveComponents: 1,
				modernJsFramework: true,
				cssFramework: true,
				webApp: false,
				dashboard: true,
				userManagementSystem: false,
				complexDesign: false,
				responsiveDesign: true,
				seoOptimization: true,
			},
			goodPractices : {
				maintainedDocumentation : true,
				testingEnviroment : true,
				unitAndIntegrationTesting : false,
				stagingEnviroment : true,
				applicationMonitoring : true,
				securityChecks : false
			},
			team : {
				numberDevelopers: 1,
				developers: [new Developer()],
				agileDevelopment: true,
				sameLocation: true,
				outsourcedDevolopers: false,
				outsourcingNewbee: false,
				languageBarrier: false,
				newTechnologies: false,			
			},
			client : {

			}
		}
      },
	  methods : {
		  handleChange : function() {
			  if (this.team.numberDevelopers > this.team.developers.length) {
				this.team.developers.push(new Developer());
			  } else {
			  	this.team.developers.length = this.team.numberDevelopers;
			  }
		  }
	  },
}
</script>

<style>
hr {
	margin: 25px;
}
</style>