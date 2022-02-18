# APM
Automated Patch Management
APM processor and all APM recipes that we use at FresnoState

This processor and set of recipes allows someone to automatically manage 
updates in JAMF Patch Management. This is different than some others because 
most use the older fancy smart groups.  This processor works by looking at a 
specific policy that you give the name for. The idea is that as the autopkg 
uploads the latest version of an app with jamf uploader (or any pkg uploader)
this processer then pulls the package info from that policy and looks for the 
patch management item of the name given. It then parses the version from the pkg
and looks for the that definition in the patch management item. If found it adds
the package to the patch management definition. It also looks for a gamma patch policy
if found it adds that version and definition to the policy. If not then it will
make the gamma policy. After all of that it will log the the date that the gamma 
was updated to a cache file. With that cache file it checks until the delta has 
been met. Once the delta is met then the prod policy is updated or created. 
