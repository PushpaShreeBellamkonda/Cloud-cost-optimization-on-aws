**step1.create an ec2 instance**

![image](https://github.com/user-attachments/assets/1701dc56-6d5c-43a4-b7a2-465850dfeb76)


**step2.No snapshots are there so,create one snapshot to that instance**

![image](https://github.com/user-attachments/assets/a4aab5ca-15b6-4667-ac7a-5b53626dc976)


![image](https://github.com/user-attachments/assets/871ee679-9d36-433b-8ccf-b0015329a098)


**step3 Create a lambda function using python  script,deploy it and test it**

![image](https://github.com/user-attachments/assets/7105cb12-999e-43f9-a9c4-b38a45600de6)


![image](https://github.com/user-attachments/assets/993fb8a9-f7af-4841-8c4c-6840eb656e58)


-Default execution time for lambda is “3 seconds “ <br>
-So it will fail asking describe snapshots <br>

**step4: go to configuration  > edit > increase timeout = 10 sec  > save**

![image](https://github.com/user-attachments/assets/42374f3c-12dd-47b7-9aab-42db46348ec6)


**step5 Now we have to give permissions to it for that goto configuration > permissions > role name > Now add permissions**

![image](https://github.com/user-attachments/assets/e9bda89e-b2fb-46d1-baeb-f7e9a1c6ed80)


**step6 In permissions > add permissions > create inline policy**

![image](https://github.com/user-attachments/assets/8d82624d-233d-4ead-8fc0-ca139583a3b2)


**-policies to be attached**: Describe snapshots, Delete snapshots, Describe instances , Describe volumes  ,we can also give “all ec2 actions” <br>


![image](https://github.com/user-attachments/assets/65440f9f-503d-4a26-82e6-893ef6566f86)


![image](https://github.com/user-attachments/assets/1cdac317-e586-4d45-a85e-2912419cd3d6)


**step8 Now attach this policy to the role,no go to lambda and run it again**

![image](https://github.com/user-attachments/assets/4056bae5-cb78-4011-901b-0d589736721e)


**step9 Now delete ec2 instance which will also delete volume as well ,but snapshot is still available**

![image](https://github.com/user-attachments/assets/bda23a47-bfe6-4139-8697-6f4e0a66af55)


![image](https://github.com/user-attachments/assets/78baecdd-cdf8-4618-80ac-0a776d9a624c)


**step10 now go to code and run again**

![image](https://github.com/user-attachments/assets/56b19a73-7ca0-41f4-bdb6-1eb06239b8b8)

-it says that the snapshot is deleted,as the associated snapshot is not found <br>

![image](https://github.com/user-attachments/assets/1c87a69e-281e-4081-9e5f-27a5b4a6a981)


**In this way we optimize the cost in aws**

















