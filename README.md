# 3D Cube CountDown script #

*Description:*  Cube CountDown script takes advantage of CSS3's transform property to display 3D cubes that rotate to count down to any desired future date.  Specify the top most unit of each counter, whether it's "days", "hours", "minutes", or "seconds".  Two event handlers are available for you to run custom code while the counter is winding down (every second), and also, when the target date/time has been reached.

## Directions ##

Add the following code to the HEAD of your page:

	<link rel="stylesheet" href="ddcubeclass.css" />
	
	<style>
	
	/* 2nd demo specific CSS */
	#dynamicfuturedate .ddcubecountdown{
		display: block; /* display each cube on its own line */
		margin-bottom: 5px;
		font-size: 8px; /* adjust font size to scale up/down the cubes (default is 10px) */
	}
	
	#dynamicfuturedate ul li{
		background: darkred;
	}
	
	</style>
	
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
	
	<script src="ddcubeclass.js"></script>
	
	<script src="ddcubecountdown.js">
	
	/***********************************************
	* 3D Cube Countdown script- (c) Dynamic Drive DHTML code library (www.dynamicdrive.com)
	* Please keep this notice intact
	* Visit Dynamic Drive at http://www.dynamicdrive.com/ for this script and 100s more
	***********************************************/
	
	</script>
	
	<script>
	
	
	jQuery(function($){ // on DOM load
	
	//Eg #1
		var mycountdown = new cubecountdown({
			containerid: 'futuredate',
			targetdate: 'October 17, 2018 11:26:30',
			size: ['10em', '6em'], // specify cube dimensions in "em" only
			unit: ['days']
		})
	
		mycountdown.onEnd = function(){ // when target date has arrived
			$('#futuredate').html('<b>That date has arrived!</b>')
		}
	
	
	//Eg #2
		var christmasday = new Date( new Date().getFullYear(), 11, 25) // construct future date string dynamically
	
		var christmascountdown = new cubecountdown({
			containerid: 'dynamicfuturedate',
			targetdate: christmasday,
			unit: ['days']
		})
	
		christmascountdown.onEnd = function(){ // when target date has arrived
			$('#dynamicfuturedate').html('<b>Christmas has arrived!</b>')
		}
	
	})
	
	</script>

## Menu Markup ##

Add the following sample menu markup to your page:

	<div id="futuredate"></div>
	<div style="margin-left:100px;font-weight:bold">until October 17, 2018 11:26:30!</div>
	
	<br />
	
	<div id="dynamicfuturedate"></div>
	<div style="font-weight:bold">until Christmas!</div>



## More info ##

Visit the script's project page for additional details on setup and documentation: <http://www.dynamicdrive.com/dynamicindex6/ddcubecountdown/index.htm>
