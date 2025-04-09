Perform the below updates at the end of each session:

![image](https://github.com/user-attachments/assets/317936c1-8382-49c2-8ed0-e2fc5a617a47)

![image](https://github.com/user-attachments/assets/7111a32d-72f8-47e2-8553-97271f1e3c1e)

Manually stop the jumpserver.

Next session:
ASG -> Control Plane ASG -> Edit  -> Change all fields to from 0 to 1 -> update
ASG -> Nodes Plane  -> Edit  -> Change all fields to from 0 to 2 -> update
Verify the instances.

Kops jumpserver -> Start instance

Run the below command if you are not able to retrieve the data when you run kubectl command. The below command comes in handy if you have downscaled your cluster and have scaled it up again. 
```
kops export kubeconfig --admin
```
