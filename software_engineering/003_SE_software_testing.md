reference - [TutorialPoint](https://www.tutorialspoint.com/software_engineering/se_quality_qa1.htm)  
# Software Testing

Software testing may be defined as a process whose objective is to find the problem in implementation of a program. 
Execution of this program is very much needed for the software project. 
According to IEEE testing means, the process of exercise or evaluating a system or its component by manual or automated means to
- Audit about the necessary needs completed by software testing.
- Get the value of difference between proposed result and actual result.

For making the simple process of software testing it is required that activities are broken in small size. 
Generally this method is used and system is divided in sub systems. All those sub system tested individually before the process of system testing start. 
Under the process of software testing three steps are taken. Individual module is the main part of focus during unit testing step. 
After the unit testing, all individual modules are combined with each other. 
After this step software testing process start and developer have focus on complete software system.

## Unit Testing
This is the first step of the process of software testing and on this step programmer confirm about the function performed by the module. The software have smallest unit which is called module. After the development of source code unit testing start and it verifies for the right syntax. The primary goal of the unit testing is to get the minimum unit which will be able to taste and confirm that it works or not. Every single module tested separately. After testing all individual modules are combined with each other. Some tests are taken under the process of unit testing process which is:

- **Nature test of module** - In the test of a module nature we verify that the flow of information is positive in tested module under that situation which is specified for the unit test.
- **Performable test** - This checkout point have the objective to calculate the time period of response, started time, last time and during the whole process time and communication between links.
- **Local data structure test** - Storage of local data is checked under this step that all the data and information collected in systematic way or not.
- **Boundary test** - This test is performed for the surety that the information provided by the software is true or not under those conditions which are given by the users.
- **Independent path test** - Under this test it is checked that the given task is properly executed or not and working ok. Only with the help of this test can check it.
- **Error handling test** - The error which occurred during the process is properly handled or not. This type of information provided under this test.

### Process of unit testing
In the process of unit testing there is need to required data or information about other module. With the help of driver and stubs we can easily get. A programmer which gives the test and passes it to where module tested is called driver. Which programs used to replace module and subordinates of the module being tested is called stubs. Stubs and driver are the need of unit testing process. Quantity of stubs and drives can be reduced if they have the quality of simplicity.

----------------

## Integration Test
Integration testing is the next step of software testing. In this test much kind of modules which are individual tested are combined with each other in to subsystem which is then tested. The main objective of unit testing is to get the information about the independent module working condition is positive but the main drawback of unit testing has no such condition which gives the guaranty that these modules provide the positive result after the attachment as a whole system. So this is reason of performing integration test. We need to check following errors which can affect the integration of module.
- Outside data can create the problem.
- Out of module testing could be away from the expectation.
- It is possible that integration result is not in favor of that process or module.

Generally integration testing has use two method.
### Top down Integration Testing
This type of method has a wide area of thought. It's needed a high level module after testing and integrated first. Under this approach module replaced and providing new stubs. This process continues at that level till time it integrates all modules and tested. In this approach high level logic and flow of data used which decrease the drivers need.

#### Benefits
- Firstly up level modules tested.
- Both approach "breadth and depth" supported.
- One driver at the most is required.

#### Draw backs
- Low level modules take long time for verification.
- Not proper data find in the stub for feedback in the favor of calling module.
- Level of supporting is low for the limited functionality.
- Complicates test management required for the stub.

### Bottom up Integration Testing
This approach gives the importance to lower level modules. In this level modules tests first and with the help of a driver integrated first. We can add one or more modules combined or jointed with each other. After the integration of all the modules this process became closed.

#### Benefits
- When we start this process with actual module then stubs not required.
- Low level module verified early in this approach.

#### Draw backs
- Complicates test management required for drivers.
- Release of limited functionality supported by low level.
- Verification of high level module time taken.

## System testing
The system testing process is the base of a software system. The main objective of system testing is that the software satisfied the client requirement. System testing is a series of that entire test with fully exercise which base is computer system. Every task has a separate objective and series of different test its clear that all part of system are combined with a systematic way and doing their work very well. There are three types of testing in system testing.

1.  **Recovery Testing** - The base of designed in Recovery testing is that type we can observed easily that how much quick a system covers its points if the system became fail. We have many kind of program which recovers quickly from the errors and started at time or operated at given time. A fault has much cause but recovery testing clarified that system covered all fault and performing well. A human always desired that a system have the capacity to recover very fast without human touch. The recovery system determined that the repair condition is acceptable or not.

2. **Security testing**
   - A protective application made in software, with the help of this application it provide safety from local and those person who have not right to use the system.
   - With the help of security testing other computer cannot get the benefit to access this and its information.

3. **Stress testing** - Stress testing cannot be performed in normal condition. With the help of this a system use in that condition when demand increased or decreased quickly.

   - How a input function performed when the speed of input became more than expectations.
   - More excessive search and hunting of data on click is also involved in stress testing.

