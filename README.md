<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<%@ taglib uri="http://www.springframework.org/tags/form"
	prefix="spring"%>
<%@ page isELIgnored="false"%><!doctype html>
<html>
<head>
<meta charset="utf-8">
<meta name="viewport"
	content="width=device-width, initial-scale=1, shrink-to-fit=no">

<link rel="stylesheet" href="${pageContext.request.contextPath}/css/UHCcustom.css">
<link rel="stylesheet" href="${pageContext.request.contextPath}/css/bootstrap.css">
<link rel="stylesheet" href="${pageContext.request.contextPath}/css/loader.css">
<link rel="stylesheet" href="${pageContext.request.contextPath}/css/all-5.6.3.css">
<link rel="stylesheet" href="${pageContext.request.contextPath}/js/chosen/chosen.min.css"></link>
<script src="${pageContext.request.contextPath}/js/jquery-3.4.1.min.js"></script>
<script src="${pageContext.request.contextPath}/js/popper-1.14.3.min.js"></script>
<script src="${pageContext.request.contextPath}/js/datatables/js/jquery.dataTables.js"></script>
<script src="${pageContext.request.contextPath}/js/bootstrap.js"></script>
<script src="${pageContext.request.contextPath}/js/chosen/chosen.jquery.min.js"></script>

<title>Report-It</title>
<link rel="icon" href="${pageContext.request.contextPath}/assets/PlanBuilderFavIcon.png">
<script>
		$(function () {
			$('#confirmDeleteApp').modal({ backdrop: 'static', keyboard: false, show: false});
			$('#environmentModel').modal({ backdrop: 'static', keyboard: false, show: false});
			$('#applicationModel').modal({ backdrop: 'static', keyboard: false, show: false});
		})

	</script>
</head>
<body>
	<nav class="navbar navbar-expand-lg navbar-light bg-white exPad">
		<a href="${pageContext.request.contextPath}/Home.jsp"> <img src="${pageContext.request.contextPath}/assets/Optum_UHC.jpg" alt="UHC Logo"
			class="img-fluid">
		</a>
		<button class="navbar-toggler" data-toggle="collapse"
			data-target="#collapse_target">
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse justify-content-end"
			id="collapse_target">
			<ul class="nav ">
				<li class="nav-item" data-toggle="tooltip" data-placement="left"
					title="Home"><a class="nav-link text-primary" href="home"><i
						class="fas fa-home"></i></a></li>
			<c:if test="${adminFlag.get()}">
				<li class="nav-item dropdown" data-toggle="tooltip"
					title="Configuration"><a
					class="nav-link text-primary dropdown-toggle"
					data-toggle="dropdown" href="#" role="button"><i
						class="fas fa-cogs"></i></a>
					<div class="dropdown-menu">
						<a class="dropdown-item" href="userList">User Configurations</a> <a
							class="dropdown-item" href="applicationConfigurations">Application
							Configurations</a>
					</div></li>
					</c:if>
				<li class="nav-item dropdown" data-toggle="tooltip"
					title="Documents"><a
					class="nav-link text-primary dropdown-toggle"
					data-toggle="dropdown" href="#" role="button"><i class="fas fa-solid fa-book"></i></a>
					<div class="dropdown-menu">
						<a class="dropdown-item" href="downloadQuickRefGuide">Download Quick <br> Reference Guide</a>  
						<a class="dropdown-item" href="downloadUserGuide">Download User Guide</a> 
					</div>
				</li>
				<li class="nav-item dropdown" data-toggle="tooltip"
					data-placement="left" title="Help"><a
					class="nav-link text-primary dropdown-toggle"
					data-toggle="dropdown" href="#" role="button" aria-haspopup="true"
					aria-expanded="false"><i class="fas fa-question-circle"></i></a>
					<div class="dropdown-menu">
						<a class="dropdown-item" href="terms">Terms of Use</a> <a
							class="dropdown-item"
							href="https://hub.uhg.com/sites/hub/UnitedHealth-Group/d/Legal-Compliance-Regulatory-Affairs/Corporate-Privacy-Office/Documents/UHGPrivacyPolicyManual.pdf">Privacy
							Policy</a> <a class="dropdown-item" href="licenses">Licenses</a>
									<a class="dropdown-item" href="https://optum.service-now.com/itss2/">Report an Issue</a>
					</div></li>
				<li class="nav-item"><a class="nav-link text-warning"
					href="ulogout"><i class="fas fa-sign-out-alt"></i><strong>
							Log Out</strong></a></li>
			</ul>
		</div>
	</nav>
	<spring:form name="Configurations" action="saveConfigurations" modelAttribute="configurations" id="configurationsFormId">
		<input type="hidden" id="applicationListId" value="${configurations.applications}"/>
		<input type="hidden" id="projectListId" value="${projects}"/>
		  
		  
		  			<c:if test="${msg != null}">
                            <div class="row">
                                <div class="col-md-8" style="margin: auto;width: 60%;padding: 10px;">
                                    <div class="alert alert-success alert-dismissable">
                                        <button type="button" class="close" data-dismiss="alert" 
                                                aria-hidden="true">&times;</button>
                                        <strong></strong>${msg}
                                    </div>
                                </div>
                            </div>
                        </c:if>

                        <c:if test="${ermsg != null}">
                            <div class="row">
                                <div class="col-md-8" style="margin: auto;width: 60%;padding: 10px;">
                                   <div class="alert alert-danger alert-dismissable">
											<button type="button" class="close" data-dismiss="alert"
											aria-hidden="true">&times;</button>
											${ermsg}
								</div>
                                </div>
                            </div>
                        </c:if>
                        
         <div class="modal fade" id="confirmDeleteEnvironment" tabindex="-1" role="dialog" aria-labelledby="confirmDeleteEnvironmentLabel" aria-hidden="true">
	        <div class="modal-dialog modal-dialog-centered" role="document">
	        <div class="modal-content">
	            <div class="modal-header">
	            <h5 class="modal-title" id="confirmDeleteEnvironmentLabel">Are you sure you want to delete this environment?</h5>
	            </div>
	            <div class="modal-body">
	                <p></p>
	                <a class="btn btn-outline-primary btn-block"  id="yesDeleteEnvironmentId">Yes</a>
	                <a class="btn btn-outline-primary btn-block"  id="noDeleteEnvironmentId">No</a>
	            </div>
	        </div>
	        </div>
	    </div>          
        <div class="modal fade" id="confirmDeleteApp" tabindex="-1" role="dialog" aria-labelledby="confirmDeleteAppLabel" aria-hidden="true">
	        <div class="modal-dialog modal-dialog-centered" role="document">
	        <div class="modal-content">
	            <div class="modal-header">
	            <h5 class="modal-title" id="confirmDeleteAppLabel">What do you want to delete?</h5>
	            </div>
	            <div class="modal-body">
	                <p></p>
	                <a class="btn btn-outline-primary btn-block"  id="yesDeleteApplicationId">Delete this application</a>
	                <a class="btn btn-outline-primary btn-block"  id="yesDeleteFeatureId">Delete this feature</a>
	                <a class="btn btn-outline-primary btn-block"  id="noDeleteApplicationId">Cancel</a>
	            </div>
	        </div>
	        </div>
	    </div>
	    
	    
	    <div class="modal fade" id="environmentModel" tabindex="-1" role="dialog" aria-labelledby="environmentLabel" aria-hidden="true">
	        <div class="modal-dialog modal-dialog-centered" role="document">
	        <div class="modal-content">
	        
	        <div class="modal-header" style="background-color: #000099; color: white;">
                         <h4 class="modal-title"  id="environmentLabel"> Environment Details</h4>
                        <button type="button" class="close" data-dismiss="modal" id="closeEnvironmentModel" style="color: white;">&times;</button>
                </div>
	            
	            <div class="modal-body">
	                <div class = "row">
	                	<div class="form-group col-6">
	                		<input type="hidden" class="form-control" id="isEnvironmentEdit" name="isEnvironmentEdit" value = "false">
	                	 	<input type="hidden" class="form-control" name="environment.environmentId" id="environmentId">
                            <label class="requiredLabel" for="environmentName">Environment Name</label>
                            <input type="text" class="form-control" style="width: 400px" name="environment.environmentName" id="environmentName" placeholder="Environment Name">
                            <span id="environmentNameError" class="error" hidden = "hidden"> Please enter environment name</span>
                        </div>
                    </div>
                    <div class = "row">
                        <div class="form-group col-6">
                            <label for="environmentDescription">Description</label>
                            <input type="text" class="form-control" style="width: 400px" name="environment.description" id="environmentDescription">
                        </div>
                    </div>
                     <div class = "row">
                        <div class="form-group col-6">
                            <button class="btn btn-success" type="button" id="saveEnvironment">Save</button>
                        </div>
	                </div>
	            </div>
	        </div>
	        </div>
	    </div>
	    
	    <div class="modal fade" id="applicationModel" tabindex="-1" role="dialog" aria-labelledby="applicationLabel" aria-hidden="true">
	        <div class="modal-dialog modal-dialog-centered" role="document">
	        <div class="modal-content">
	        	
	        	<div class="modal-header" style="background-color: #000099; color: white;">
                         <h4 class="modal-title"  id="environmentLabel">Application and Feature Details</h4>
                        <button type="button" class="close" data-dismiss="modal" id="closeApplicationModel" style="color: white;">&times;</button>
                </div>
	            
	            <div class="modal-body">
	                <div class = "row">
	                	<div class="form-group col-6">
	                		<input type="hidden" class="form-control" id="isApplicationEdit" name="isApplicationEdit" value = "false">
	                		<input type="hidden" class="form-control" id="applicationId" name = "application.applicationId">
                            <label class="requiredLabel" for="applicationName">Application Name</label>
                            <input type="text" class="form-control" id="applicationName" name = "application.applicationName" placeholder="Application Name" style="width: 400px">
                             <span id="applicationNameError" class="error" hidden="hidden"> Please enter application name</span>
                        </div>
                         
                    </div>
                    <div class = "row">
                    	<div class="form-group col-6">
                    		<input type="hidden" class="form-control" id="featureId" name = "application.featureId">
                            <label class="requiredLabel" for="featureName">Feature Name</label>
                            <input type="text" class="form-control" id="featureName" placeholder="Feature Name" name = "application.featureName" style="width: 400px">
                            <span id="featureNameError" class="error" hidden="hidden"> Please enter feature name</span>
                        </div>
                    </div>
                    
                    <div class = "row">
                    	<div class="form-group col-6">
                            <label class="requiredLabel" for="featureName">Service Now Assignment Group Name</label>
                            <input type="text" class="form-control" id="serviceNowGroupName" placeholder="Service Now Assignment Group Name" name = "application.serviceNowGroupName" style="width: 400px">
                            <span id="serviceNowGroupNameError" class="error" hidden="hidden"> Please enter service now group name</span>
                        </div>
                    </div>
                    
                    <div class = "row">
							<div class="form-group col-6">
							<input type="hidden" class="form-control" name="application.rallyProjectName" id="rallyProjectName">
								<label class="requiredLabel" for="rallyProject">Project</label> 
								<select class="form-control chosen-select"  id="rallyProject" style="width: 400px" name = "application.rallyProjectId" onchange="getFeatures(this.value)">
									<option value = "">Select..</option>
									<c:forEach items="${rallyProjects}" var="rallyProject"
										varStatus="status">
									<option  value = "${rallyProject.id} ">${rallyProject.name}</option>
									</c:forEach>

								</select>
								 <span id="rallyProjectError" class="error" hidden="hidden"> Please select a rally project</span>
							</div>
                    </div>
                    <div class = "row">
                    <div class="form-group col-6">
                    	<input type="hidden" class="form-control" name="application.rallyParentFeatureName" id="rallyParentFeatureName">
                            <label class="requiredLabel" for="rallyParentFeature">Parent Feature</label>
                            <select class="form-control chosen-select" id="rallyParentFeature" name = "application.rallyParentRef" style="width: 400px">
                            <option value = "">Select..</option>
                            </select>
                            <span id="rallyParentFeatureError" class="error" hidden="hidden"> Please select a rally feature</span>
                        </div>
                    </div>
                    
                     <div class = "row">
                        <div class="form-group col-6">
                            <button class="btn btn-success" type="button" id="saveApplication">Save</button>
                        </div>
	                </div>
	            </div>
	        </div>
	        </div>
	    </div>
		<div class="container" style="padding-top: 1em">
			<div class="card">
				<div class="card-body">
					<div class="tile-body">
						<div class="row">
							<div class="form-group col-md-11 col-lg-11">
								<h4>Environments
								<button type='button' title='Add'
									class='btn btn-rounded btn btn-primary btn-sm'
									id='addEnvironment' style="float: right;">Add</button></h4>
							</div>
						</div>
						<table class="myDataTable" id="environmentListTable" style="width:100%">
							<thead>
								<tr>
									<th style="text-align: center;">S.No</th>
									<th style="text-align: center;">Environment Name</th>
									<th style="text-align: center;">Description</th>
									<th style="text-align: center;">Action</th>
									
								</tr>
							</thead>
							<tbody>
								<c:if test="${configurations.environments != null}">
									<c:set var="snCount" value="1" />
									<c:forEach items="${configurations.environments}"
										var="environmentObj">
										<tr>
											<td style="width:5%">${snCount}</td>
											<td style="width:33%;text-align: center">${environmentObj.environmentName}</td>
											<td style="width:33%;text-align: center">${environmentObj.description}</td>
											<td style="width:33%;text-align: center">
											<a role="button" target="_blank" class="btn btn-sm btn-outline-primary text-primary float-center" onClick="editEnvironment('${environmentObj.environmentId}')"><i class="fas fa-edit"></i></a>
											<a role="button" target="_blank" class="btn btn-sm btn-outline-primary text-primary float-center" onClick="deleteEnvironment('${environmentObj.environmentId}')"><i class="fas fa-trash"></i></a>
											</td>
										</tr>
										<c:set var="snCount" value="${snCount+1}" />
									</c:forEach>
								</c:if>
								
							</tbody>
						</table>
					</div>
				</div>
			</div>
		</div>
		
		<div class="container" style="padding-top: 1em">
			<div class="card">
				<div class="card-body">
					<div class="tile-body">
						<div class="row">
							<div class="form-group col-md-11 col-lg-11">
								<h4>Applications and Features
								<button type='button' title='Add'
									class='btn btn-rounded btn btn-primary btn-sm'
									id='addApplication' style="float: right;">Add</button>
								</h4>
							</div>
						</div>
						<table class="myDataTable" id="applicationListTable" style="width:100%">
							<thead>
								<tr>
									<th>S.No</th>
									<th>Application Name</th>
									<th>Feature Name</th>
									<th>Project</th>
									<th>Parent Feature</th>
									<th>Support Group</th>
									<th>Action</th>
								</tr>
							</thead>
							<tbody>
							<c:if test="${configurations.applications != null}">
									<c:set var="snCount" value="1" />
									<c:forEach items="${configurations.applications}"
										var="applicationObj" >
										<tr>
											<td>${snCount}</td>
											<td>${applicationObj.applicationName}</td>
											<td>${applicationObj.featureName}</td>
											<td>${applicationObj.rallyProjectName}</td>
											<td>${applicationObj.rallyParentFeatureName}</td>
											<td>${applicationObj.serviceNowGroupName}</td>
											<td>
											
											<a role="button" target="_blank" class="btn btn-sm btn-outline-primary text-primary float-center" onClick="editApplication('${applicationObj.applicationId}','${applicationObj.featureId}')"><i class="fas fa-edit"></i></a>
											<a role="button" target="_blank" class="btn btn-sm btn-outline-primary text-primary float-center" onClick="deleteApplicationOrFeature('${applicationObj.applicationId}','${applicationObj.featureId}')"><i class="fas fa-trash"></i></a>
											</td>
											
											
										</tr>
										<c:set var="snCount" value="${snCount+1}" />
									</c:forEach>
								</c:if>
								
								
							</tbody>
						</table>
					</div>
				</div>
			</div>
		</div>
		
		

		<div class="container" style="padding-top: 2em">
			<div class="row">
				<div class="col-6">
					<a class="btn btn-warning btn-block" id="cancelBtn" href="home">Cancel</a>
				</div>
			</div>
		</div>
		<div class="modal fade" id="warnbox" aria-hidden="true">
			<div class="overlay" id="loader-parent" style="width: 100%; height: 100%; display: block">
				<div id="loader" class="pl-loader" style="display: block;">
					<div id="in1" class="inner one"></div>
					<div id="in2" class="inner two"></div>
					<div id="in3" class="inner three"></div>
				</div>
			</div>
		</div>
	</spring:form>
	<div class="copyright" style="padding-top: 2em" align="center">
		<footer style="color: #fff;">
			&copy; <span id="year"></span> United HealthCare Services, Inc.
		</footer>
	</div>
	<script src="<c:url value="js/ApplicationConfiguration.js"/>"
		type="text/javascript"></script>
</body>
</html>
