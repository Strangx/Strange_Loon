/*
 network-changed script-path=https://raw.githubusercontent.com/Loon0x00/LoonExampleConfig/master/Script/netChanged.js
 */

 //Get the relevant configuration of Loon and return it in json format
 var confStr = $config.getConfig()
 console.log(confStr)

 var conf = JSON.parse(confStr)
 if (conf.ssid == "your ssid name") {
     /*
     Set global operating mode
     0: Global Direct
     1:By Rule
     2: Global Proxy
     */
     $config.setRunningModel(0)
     //Set the strategy corresponding to the select strategy group, if the sub-strategy does not exist, the original strategy will remain unchanged
     $config.setSelectPolicy("⛔ ad blocking","DIRECT")
     $notification.post("Network changed","Change Running Model to Global Direct","⛔ Ad blocking to DIRECT")
 } else {
     $config.setRunningModel(1)
     $config.setSelectPolicy("⛔ ad blocking","REJECT")
     $notification.post("Network changed","Change Running Model to Filter by rule","⛔ Ad blocking to REJECT")
 }

 //Set the policies of multiple policy groups at the same time
 $config.setSelectPolicy(["Foreign Website","Ad Blocking","Google Service"],["HK Node 1","REJECT","Node Selection"])

 //Get the sub-strategy of the relevant strategy, in json format
 var subPolicys = $config.getSubPolicys("Node Options")
 console.log(subPolicys);
