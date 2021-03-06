---
layout: api-documentation
title : 'Get Local Labor Rate in Dollars per Hour by Zipcode'
title_active_left_menu: 'Service: Local Labor Rate'
title_parent: Api documentation

amount_version: 1
title-endpoint: 'Get Local Labor Rate in Dollars per Hour by Zipcode'
spec: service_local_labor_rate
version: v1
api: vehicle
dropdown-link: 'v1/api/maintenance/ziplaborrate'


level: 3
description_edpoint: 'Get Local Labor Rate in Dollars per Hour by Zipcode'
title_md : Description
number: 1

---

### Description

Get the local labor rate (dollars per hour) in a specific zip code.

### URL

	https://api.edmunds.com/v1/api/maintenance/ziplaborrate/{zip code}?fmt=json&api_key={api key}
	
### Code Example

You need the [Javascript SDK](https://github.com/EdmundsAPI/edmunds-javascript-sdk) to run this example.

	<!DOCTYPE html>

	<html>
	<head>
		<meta charset=utf-8>
		<title>Edmunds API Example</title>
	</head>

	<body>
		<div id="results-body"></div>
		<script>
		  	window.sdkAsyncInit = function() {
		    	// Instantiate the SDK
				var res = new EDMUNDSAPI('YOUR API KEY');

				// Optional parameters
				var options = {};

				// Callback function to be called when the API response is returned
				function success(res) {
					var body = document.getElementById('results-body');
					body.innerHTML = "The labor rate per hour in 90019 is: $" + res.zipLaborRateHolder[0].laborRate;
				}

				// Oops, Houston we have a problem!
				function fail(data) {
					console.log(data);
				}

				// Fire the API call
				res.api('/v1/api/maintenance/ziplaborrate/90019', options, success, fail);

			    // Additional initialization code such as adding Event Listeners goes here
		  };

		  // Load the SDK asynchronously
		  (function(d, s, id){
		     	var js, sdkjs = d.getElementsByTagName(s)[0];
		     	if (d.getElementById(id)) {return;}
		     	js = d.createElement(s); js.id = id;
		     	js.src = "path/to/sdk/file";
		     	sdkjs.parentNode.insertBefore(js, sdkjs);
		   }(document, 'script', 'edmunds-jssdk'));
		</script>
	</body>
	</html>