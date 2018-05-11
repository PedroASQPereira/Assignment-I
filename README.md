Assignment1_v2.0

main file: Run_File


GridData - Initialize database where all information from XML if stored

File_Specification - Storing the nametag of the data that we want to read from XML

Parsing - Initialize DOM parser, going throught the File_Specification tagnames to extract data

Extract_Node - Convert node into element and into our designated classes (e.g. BaseVoltage, Substation, etc...)

BusToBranch_Topology - Creating a relational database with the info we got from parsing, based on two dedicated classes, Bus_Topology and Branch_Topology

addAllBus - insert into BusToBranch_Topology classes the corresponding Bus_Topologies (looping through every required class which are EnergyConsumer, BusBar, LinearShunt and Synchronous Machine)

addAllBranch - recursive function that begins in a bus goes through every breaker/transformer/line and their respective connectivity nodes and terminals, until a new bus is found

YMatrix - Initialized the 2D Matrix of complex class

Complex - Defined the real and imaginary parts of a complex number, and it has all the algebraic calculations for the admittances required for Y matrix (all calculations are done in their real values and no in per unit)

BuildYMatrix - Check if there are breakers open and if there are simply remove the corresponding branch from the BusToBranch_Topology

addBusAdmittances - Calculate the admittances of the loads and shunts connected to certain buses and add them to the Ymatrix

addBranchAdmittances - Calculate the admittances of the branch which can contain either lines or transformers and add them to diagonal and non diagonal elements of the Ymatrix
