# PhoneGapSample<!DOCTYPE html>
<!--
    Copyright (c) 2012-2016 Adobe Systems Incorporated. All rights reserved.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
     KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
-->
<html>

<head>
    <meta charset="utf-8" />
    <meta name="format-detection" content="telephone=no" />
    <meta name="msapplication-tap-highlight" content="no" />
    <meta name="viewport" content="user-scalable=no, initial-scale=1, maximum-scale=1, minimum-scale=1, width=device-width" />
    <!-- This is a wide open CSP declaration. To lock this down for production, see below. -->
    <meta http-equiv="Content-Security-Policy" content="default-src * 'unsafe-inline'; style-src 'self' 'unsafe-inline'; media-src *" />
    <!-- Good default declaration:
    * gap: is required only on iOS (when using UIWebView) and is needed for JS->native communication
    * https://ssl.gstatic.com is required only on Android and is needed for TalkBack to function properly
    * Disables use of eval() and inline scripts in order to mitigate risk of XSS vulnerabilities. To change this:
        * Enable inline JS: add 'unsafe-inline' to default-src
        * Enable eval(): add 'unsafe-eval' to default-src
    * Create your own at http://cspisawesome.com
    -->
    <!-- <meta http-equiv="Content-Security-Policy" content="default-src 'self' data: gap: 'unsafe-inline' https://ssl.gstatic.com; style-src 'self' 'unsafe-inline'; media-src *" /> -->

    
    <title>Local Storage</title>

</head>

<body>
    
	<button type="button" onclick="addCountry()">Add Canada</button> </br></br>
	<button type="button" onclick="get1Data()">Get USA</button> </br></br>
	<button type="button" onclick="getAllData()">Get All</button> </br></br>
	<button type="button" onclick="removeAllData()">Remove All</button> </br></br>
		<script type="text/javascript" src="cordova.js"></script>
		<script type="text/javascript">
	  document.addEventListener("deviceready", onDeviceReady, false);
	  function onDeviceReady(){
		localStorage.setItem("IN", "india");
		localStorage.setItem("FR", "France");
		localStorage.setItem("USA", "usa");
	  }
	  function addCountry(){
		localStorage.setItem("CA", "canada");
		alert ("canada added");
	  }
	 function get1Data(){
		var usa = localStorage.getItem("USA");
		alert ("country name is" + usa);
	 }
	 function getAllData(){
		 for ( var i in localStorage) 
		alert (localStorage.getItem(i));
	 }
	 function removeAllData() {
		window.localStorage.clear();
		alert ("All gone");
	 }
	</script>
</body>

</html>
