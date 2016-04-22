<!DOCTYPE html>
<html ng-app="App">
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>
	<script src="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
	<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
	<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
	<style></style>
	<body class="clickbody">

	<div class="navbar navbar-inverse">
		<div class="container">
			<div class="navbar-header">
				<button class="navbar-toggle" data-toggle="collapse" data-target="#myNavBar">
					<span class="icon-bar"></span>
					<span class="icon-bar"/></span>
					<span class="icon-bar"/></span>
				</button>
				<div class="navbar-header">
				  <a class="navbar-brand" href="#"><img style="margin-top:-10px" src="WebSiteLogo.png"/></a>
				</div>
			</div>
			<div id="myNavBar" class="navbar-collapse collapse">
				<ul class="nav navbar-nav navbar-right">
					<li class="dropdown">
						<a class="dropdown-toggle" data-toggle="dropdown" href="#">Accuen
						<span class="caret"></span></a>
						<ul class="dropdown-menu">
						  <li><a href="#">Accuen SubLink 1</a></li>
						  <li><a href="#">Accuen SubLink 2</a></li>
						  <li><a href="#">Accuen SubLink 3</a></li> 
						</ul>
					</li>
					<li class="dropdown">
						<a class="dropdown-toggle" data-toggle="dropdown" href="#">John Snow
						<span class="caret"></span></a>
						<ul class="dropdown-menu">
						  <li><a href="#">John SubLink 1</a></li>
						  <li><a href="#">John SubLink 2</a></li>
						  <li><a href="#">John SubLink 3</a></li> 
						</ul>
					</li>
					<li class="">
						<img src="UserImg.png" style="margin-top: 10px;"/>
					</li>
				</ul>
			</div>
		</div>
	</div>

	<div class=" pull-left" style="margin:10px 15px">
		<label class="pull-left">
			Accuen<br>
			Insertion Orders
		</label>
	</div>
	<div class="dropdown pull-right" style="margin:10px 15px">
		<button class="btn btn-primary dropdown-toggle " data-toggle="dropdown" > + INSERTION ORDER 
		</button>
		<ul class="dropdown-menu">
			<li> XML </li>
		</ul>
	</div>
	
	<div ng-app="myApp" ng-controller="namesCtrl">
		<div class="pull-left" style="margin:10px 15px">
			<input id="searchId" type="text" class="text " placeholder="Search insertion orders..." ng-model="test"/>		
		</div>
		<table cellpadding="0" cellspacing="0" border="0" class="display table table-bordered" id="hidden-table-info">
			<thead>
				<tr style="opacity:0.7">
					<th>Name</th>
					<th>% OF GOAL</th>
				</tr>
			</thead>
			<tbody>
				<tr class="gradeA">
					<td class="center"><img src="nameOption.png" />Item 1</td>
						<td>
							<div class="progress">
								<div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100" style="width:60%">
								</div>
								<span class="">60%</span>
							</div>
						</td>
				</tr>
				<tr class="hideme">
					<td colspan="10">
						<div>
							<img src="Graph1.png"/>
						</div>
					</td>   
				 </tr>
				<tr class="gradeA">
					<td class="center"><img src="nameOption.png" />Item 2</td>
					<td>
						<div class="progress">
							<div class="progress-bar" role="progressbar" aria-valuenow="42" aria-valuemin="0" aria-valuemax="100" style="width:42%">
							</div>
							<span class="">42%</span>
						</div>
					</td>
				</tr>
				<tr class="hideme">
					<td colspan="10">
						<div>
							<img src="Graph1.png"/>
						</div>
					</td>   
				 </tr>
			</tbody>
		</table>
	</div>
	<script>
	debugger;
		$('td').addClass("clickh");
		$('.hideme').find('div').hide(); 
		$('.clickh').click(function(e){
			if($(this).is(e.target)){
				$(this).parent().next('.hideme').find('div').slideToggle(500);
				e.stopPropagation();
			}
        });
		$('.clickbody').click(function(e){
			if($(this).is('body')){
				$(this).find('.hideme').find('div').hide(500);
			}
		});
	</script>
	<script>
		angular.module('myApp', []).controller('namesCtrl', function($scope) {
			$scope.names = [
				{name:'Macy\'s Q3-Q4 Furniture Sales',goal:'60'},
				{name:'AT&T General Market 2014',goal:'42'},
				{name:'History Channel - Axe Men Tune in',goal:'42'},
				{name:'Nike World Cup August',goal:'18'},
				{name:'Toyota Fail Giveaway Promo',goal:'0'},
				{name:'Toyota Fail Sales Event',goal:'0'}
				];
			$scope.orderByMe = function(x) {
				$scope.myOrderBy = x;
			}
		});
	</script>
	</body>
</html>
