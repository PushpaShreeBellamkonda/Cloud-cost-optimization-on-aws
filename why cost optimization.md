# Why cost Optimization
Assume we have created an EC2 and also taken some snapshots (backups) of it. <br> 
We might delete the instance but forgot to delete its volume.<br>
Then obviously aws will cost for it and for snapshots<br>
Also we created an s3 bucket and uploaded an object and using it for long time ,then we also we will be charged <br>        
## Stale resources : 
Resources  that   have been using since very long but not deleting them. <br>
Now devops engineer will take care of this issue <br>
**Example** : we created an c2 instance and created few snapshots <br>
Case 1 : only ec2 is deleted <br>
Case 2 : ec2 and its volume is also deleted <br>
In both cases snapshots are not deleted, this is the problem statement <br>
-To solve this  we write a lambda function in python  <br>
-The lambda function will interact with AWS API and does the following <br>
         **Step 1** Fetch all EBS snapshots <br>
         **Step 2** Filter snapshots that are stale <br>
