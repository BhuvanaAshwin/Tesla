<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="description" content="">
<meta name="author" content="">
<title>TESLA</title>

<!-- Bootstrap Core CSS -->
<link href="css/bootstrap.min.css" rel="stylesheet">

<!-- Custom CSS -->
<link href="css/style.css" rel="stylesheet">

<!-- HTML5 Shim and Respond.js IE8 support of HTML5 elements and media queries -->
<!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
<!--[if lt IE 9]>
        <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>
        <script src="https://oss.maxcdn.com/libs/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.5.8/angular.min.js"></script>
</head>

<body ng-app="subscribeApp">

<!-- Navigation -->
<nav class="navbar navbar-inverse navbar-fixed-top" role="navigation">
  <div class="container"> 
    <!-- Brand and toggle get grouped for better mobile display -->
    <div class="navbar-header text-center"> <a class="navbar-brand" href="#"> TESLA </a> </div>
  </div>
  <!-- /.container --> 
</nav>

<!-- Page Content -->

<video autoplay loop muted poster="video/home-hero-sx-2016.jpg" id="background">
  <source src="video/home-video-sx-2016.mp4" type="video/mp4">
  <source src="video/home-video-sx-2016.webm" type="video/webm">
</video>
<div class="subscribe-panel">
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <h3><span>Be the first to own the new Tesla Model 3.</span> Sign up to our mailing list to find out more. </h3>
      </div>
    </div>
    <div class="subscribe-form" ng-controller="formCtrlr">
      <form novalidate class="subscribe-form">
        <div class="row">
          <div class="col-md-4 col-sm-6 col-xs-12">
            <input type="email" ng-model="user.email" required placeholder="Your Email"/>
          </div>
          <div class="col-md-2 col-sm-6 col-xs-12">
            <input type="text" ng-model="user.firstName" required placeholder="First Name"/>
          </div>
          <div class="col-md-2 col-sm-6 col-xs-12">
            <input type="text" ng-model="user.lastName" required placeholder="Last Name"/>
          </div>
          <div class="col-md-2 col-sm-6 col-xs-12">
            <select ng-model="user.country" ng-options="x for x in country" required>
              <option value="" ng-selected="selected">Select Country</option>
            </select>
          </div>
          <div class="col-md-2 col-sm-12 col-xs-12">
            <input type="submit" ng-click="update(user)" value="Submit" class="btn btn-primary" />
          </div>
        </div>
      </form>
    </div>
  </div>
</div>
<!-- /.container --> 

<!-- jQuery --> 
<script src="js/jquery.js"></script> 

<!-- Bootstrap Core JavaScript --> 
<script src="js/bootstrap.min.js"></script> 
<script>
	 angular.module('subscribeApp', [])
    .controller('formCtrlr', ['$scope', function($scope) {
      $scope.master = {};
 $scope.country = ["Australia", "India", "United States", "Denmark"];
      $scope.update = function(user) {
        $scope.master = angular.copy(user);
		console.log("Email:", $scope.user.email);
		console.log("First Name:", $scope.user.firstName);
		console.log("Last Name:", $scope.user.lastName);
		console.log("Country:", $scope.user.country);
		
      };
   
    }]);
	</script>
</body>
</html>
