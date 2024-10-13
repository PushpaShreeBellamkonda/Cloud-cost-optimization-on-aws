**step1.create an ec2 instance**



**step2.No snapshots are there so,create one snapshot to that instance**







**step3 Create a lambda function using python  script,deploy it and test it**







-Default execution time for lambda is “3 seconds “ <br>
-So it will fail asking describe snapshots <br>

**step4: go to configuration  > edit > increase timeout = 10 sec  > save**




**step5 Now we have to give permissions to it for that goto configuration > permissions > role name > Now add permissions**




**step6 In permissions > add permissions > create inline policy**




**-policies to be attached**: Describe snapshots, Delete snapshots, Describe instances , Describe volumes  ,we can also give “all ec2 actions” <br>








**step8 Now attach this policy to the role,no go to lambda and run it again**




**step9 Now delete ec2 instance which will also delete volume as well ,but snapshot is still available**







**step10 now go to code and run again**



-it says that the snapshot is deleted,as the associated snapshot is not found <br>




**In this way we optimize the cost in aws**

















