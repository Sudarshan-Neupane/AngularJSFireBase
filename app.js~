var myApp = angular.module('myapp',['firebase']);
myApp.controller('myController',['$scope','$firebaseArray',function($scope,$firebaseArray){
var country = new Firebase('https://incandescent-inferno-3656.firebaseio.com/countries');
$scope.countries = $firebaseArray(country);

$scope.showForm = function(){
	$scope.addFormShow =true;
	$scope.editFormShow = false;
	clearForm();
}
$scope.hideForm = function(){
	//$scope.editFormShow = true;
	$scope.addFormShow = false;

}
function clearForm(){
	$scope.Name='';
	$scope.Code ='';
}


$scope.addCountry = function(){
	$scope.countries.$add({
	Name: $scope.Name,
	Code: $scope.Code
	});
	clearForm();
}
$scope.showCountry = function(code){
	$scope.editFormShow = true;
	$scope.addFormShow = false;
	$scope.Name= code.Name;
	$scope.Code = code.Code;
	$scope.id = code.$id;
}
//for editing the country
$scope.editCountry = function(){
	var id = $scope.id;
	var record = $scope.countries.$getRecord(id);
	record.Name = $scope.Name;
	record.Code = $scope.Code;
	$scope.countries.$save(record);
}
//for delete 
$scope.deletCountry = function(code){
$scope.countries.$remove(code);
}

}
]);
