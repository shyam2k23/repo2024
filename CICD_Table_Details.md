--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Content in Table format 
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
|   |           |                 |                      | Tools                        | Applicability Level                                         | Role performed by            |
| - | --------- | --------------- | -------------------- | ---------------------------- | ----------------------------------------------------------- | ---------------------------- |
| 1 | Plan      |                 |                      | Confluence                   | Project level                                               |                              |
|   |           |                 |                      | Jira                         | Project level                                               |                              |
|   |           |                 |                      |                              |                                                             |                              |
| 2 | Code      |                 |                      |                              |                                                             |                              |
|   |           | Version control |                      | Git                          | Project level                                               | Developer                    |
|   |           | Language        |                      | Java                         | Class level                                                 | Developer                    |
|   |           | Framework       |                      | Spring                       | Class level                                                 | Developer                    |
|   |           | IDE             |                      | Eclipse, Intellij            | Project level                                               | Developer                    |
|   |           |                 |                      |                              |                                                             |                              |
| 3 | Build     |                 |                      |                              |                                                             |                              |
|   |           | Code build      |                      | Maven, Gradle                | Project level                                               | Developer                    |
|   |           |                 |                      |                              |                                                             |                              |
|   |           |                 |                      |                              |                                                             |                              |
| 4 | Test      | Code Testing    | Microbenchmark tests | JMH                          | Class or method level                                       | Developer                    |
|   |           |                 | Unit tests           | Junit                        | Class or method level                                       | Developer                    |
|   |           |                 | Integration tests    | Spring boot integration test | Module level - A functionality such as rest controller test | Developer                    |
|   |           |                 | Functional tests     |                              | Project level                                               | Tester                       |
|   |           |                 | Performance tests    |                              | JMeter                                                      | Lead Developer               |
|   |           |                 |                      |                              |                                                             |                              |
| 5 | Release   |                 |                      | Jenkins                      |                                                             | Lead Developer(CICD)         |
|   |           |                 |                      |                              |                                                             |                              |
| 6 | Deploy    |                 |                      | Docker                       |                                                             | Lead Developer(CICD)         |
|   |           |                 |                      | Kubernetes                   |                                                             | Lead Developer(CICD)         |
|   |           |                 |                      | Open shift                   |                                                             | Lead Developer(CICD)         |
|   |           |                 |                      | AWS EC2/EKS/ECS              |                                                             | Lead Developer(CICD)         |
|   |           |                 |                      |                              |                                                             |                              |
| 7 | Operation |                 |                      | Kubernetes                   |                                                             | Lead Support Developer(CICD) |
|   |           |                 |                      | Terraform                    |                                                             | Lead Support Developer(CICD) |
|   |           |                 |                      | Openshift/ECS                |                                                             | Lead Support Developer(CICD) |
|   |           |                 |                      |                              |                                                             |                              |
| 8 | Monitor   |                 |                      |                              |                                                             |                              |
|   |           | Logging         |                      | ELK, Grafana,                |                                                             | Support Team                 |
|   |           | Monitoring      |                      | Prometheus, Datadog, Spl     |                                                             | Support Team                 |
|   |           | Observability   |                      |                              |                                                             | Support Team                 |
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Image
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![image](https://github.com/user-attachments/assets/b010fbb8-0655-43d3-8826-15c29549d629)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Contents Raw
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

					Tools	Applicability Level	Role performed by
1	Plan				Confluence	Project level	
					Jira	Project level	
							
2	Code						
		Version control			Git	Project level	Developer
		Language			Java	Class level	Developer
		Framework			Spring	Class level	Developer
		IDE			Eclipse, Intellij	Project level	Developer
							
3	Build						
		Code build			Maven, Gradle	Project level	Developer
							
							
4	Test	Code Testing		Microbenchmark tests	JMH	Class or method level	Developer
				Unit tests 	Junit	Class or method level	Developer
				Integration tests 	Spring boot integration test	Module level - A functionality such as rest controller test 	Developer
				Functional tests 		Project level 	Tester
				Performance tests		JMeter	Lead Developer
							
5	Release				Jenkins		Lead Developer(CICD)
							
6	Deploy				Docker		Lead Developer(CICD)
					Kubernetes		Lead Developer(CICD)
					Open shift		Lead Developer(CICD)
					AWS EC2/EKS/ECS		Lead Developer(CICD)
							
7	Operation				Kubernetes		Lead Support Developer(CICD)
					Terraform		Lead Support Developer(CICD)
					Openshift/ECS		Lead Support Developer(CICD)
							
8	Monitor						
		Logging			ELK, Grafana, 		Support Team
		Monitoring		 	Prometheus, Datadog, Spl		Support Team
		Observability					Support Team
![image](https://github.com/user-attachments/assets/3e26a195-3c4f-4e7c-9b31-6131941c7f56)


