# CountryState
Simple PHP Script to get all country with states.

This script can:

1. Find out all country list with country code
2. Find out all states by country code
3. Check state is valid or not by Country Short Code, ISO Code etc.

<?php

#here is all example you should use, BD parameter passed as country code of Bangladesh, you should use your own; 

$cs = new CountryState();
$countries = $cs->countries();
$getStates = $cs->getStates('BD');
$countriesStates = $cs->countriesStates();

#	you should test first before use
	print_r($countries);
	print_r($getStates);
	print_r($countriesStates);



#	to get country list only
	foreach($countries as $country){
		echo $country;
		echo '<hr>';
	}

#	to get states by Country Code
	$getStates = $cs->getStates('BD');
	foreach($getStates as $state){
		echo $state;
		echo '<hr>';
	}

#	to get country with Country Code
	foreach($countriesStates as $csval => $cskey){
		echo ucwords($cskey['c']); 
		echo ' - '; 
		echo $cskey['s'];
		echo '<hr>';
	}

# 	to see clean/clear view to understand 
	echo '<pre>';
	print_r($countriesStates);
	echo '</pre>';



 
