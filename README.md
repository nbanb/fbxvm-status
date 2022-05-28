# fbxvm-status
Simple tool to print Freebox Virtual Machines status (using API lib : `fbx-delta-nba_bash_api.sh`)
#### To be run on Freebox Delta hardware from FREE (French Internet Provider)



--------------------------------------------------------------------------------------------------------------------
### README of fbxvm-status program
--------------------------------------------------------------------------------------------------------------------



sourcing lib : `fbx-delta-nba_bash_api.sh`

You can get the library here on this branch (at the time I'm writing, changes are not merged on the original project, so use the branch):
https://github.com/nbanb/fbx-delta-nba_bash_api.sh/tree/nbanb-freebox-api

You need to have `curl` and `openssl` installed.

Get the source:

    $ curl -L https://github.com/nbanb/fbx-delta-nba_bash_api.sh/raw/nbanb-freebox-api/fbx-delta-nba_bash_api.sh > fbx-delta-nba_bash_api.sh


First get a token which allow this app to login Feebox Delta API :

#### *  authorize_application *app_id* *app_name* *app_version* *device_name*
It is used to obtain a token to identify a new application (need to be done only once)
##### Example
```bash
$ source ./fbx-delta-nba_bash_api.sh
$ authorize_application  'MyWonderfull.app'  'My Wonderfull App'  '1.0.0'  'Deb 11'
Please grant/deny access to the app on the Freebox LCD...
Authorization granted

MY_APP_ID="MyWonderfull.app"
MY_APP_TOKEN="4uZTLMMwSyiPB42tSCWLpSSZbXIYi+d+F32tVMx2j1p8oSUUk4Awr/OMZne4RRlY"
```


#### Now you can download and update fbxvm-status with your just obtained values.

```bash
$ curl -L https://raw.githubusercontent.com/nbanb/fbxvm-status/main/fbxvm-status >fbxvm-status 
$ chmod +x fbxvm-status
```

Update `fbxvm-status` program with your just obtain values :

```bash
MY_APP_ID="YourNewFBXVM.app" 
MY_APP_TOKEN="YourNewFBXVM.app.JustObtainToken"
```

#### That's all, now you are ready to use this tool which print Freebox Delta's VM status

__________________________________________________________________________________________

#### NB : 

If you need a tool to control nearly all parameters of your Freebox Delta's Virtual Machines directly from 
your current bash session using FreeboxOS REST API, you can use `fbxvm-ctrl` program which is available here : 

https://github.com/nbanb/fbxvm-ctrl


or directly :

```bash
curl -L https://raw.githubusercontent.com/nbanb/fbxvm-ctrl/main/fbxvm-ctrl > ./fbxvm-ctrl
chmod +x ./fbxvm-ctrl
```






