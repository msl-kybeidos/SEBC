# Hive Service #
* State<br />
	**curl -u msl-kybeidos:cloudera 'http://localhost:7180/api/v12/custers/msl-kybeidos/services/hive'**
	```json
	{
	  "name" : "hive",
	  "type" : "HIVE",
	  "clusterRef" : {
	    "clusterName" : "cluster"
	  },
	  "serviceUrl" : "http://CM:7180/cmf/serviceRedirect/hive",
	  "roleInstancesUrl" : "http://CM:7180/cmf/serviceRedirect/hive/instances",
	  "serviceState" : "STARTED",
	  "healthSummary" : "GOOD",
	  "healthChecks" : [ {
	    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
	    "summary" : "GOOD",
	    "suppressed" : false
	  }, {
	    "name" : "HIVE_HIVESERVER2S_HEALTHY",
	    "summary" : "GOOD",
	    "suppressed" : false
	  } ],
	  "configStalenessStatus" : "FRESH",
	  "clientConfigStalenessStatus" : "FRESH",
	  "maintenanceMode" : false,
	  "maintenanceOwners" : [ ],
	  "displayName" : "Hive",
	  "entityStatus" : "GOOD_HEALTH"
	}
	```
* Stop<br />
	**curl -u msl-kybeidos:cloudera 'http://localhost:7180/api/v12/custers/msl-kybeidos/services/hive/commands/stop'**
	```json
	{
	  "id" : 620,
	  "name" : "Stop",
	  "startTime" : "2016-11-17T21:06:19.330Z",
	  "active" : true,
	  "serviceRef" : {
	    "clusterName" : "cluster",
	    "serviceName" : "hive"
	  }
	}
	```
* Start<br />
	**curl -u msl-kybeidos:cloudera 'http://localhost:7180/api/v12/custers/msl-kybeidos/services/hive/commands/start'**
	```json
	{
	  "id" : 624,
	  "name" : "Start",
	  "startTime" : "2016-11-17T21:08:12.825Z",
	  "active" : true,
	  "serviceRef" : {
	    "clusterName" : "cluster",
	    "serviceName" : "hive"
	  }
	}
	```