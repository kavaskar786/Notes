## 2024-06-20 12:12
INTRODUCTION OF MS
1. Defnition
	1. micro services is defined as the small services(small applications) connected to make one complete application
	2. leaves very small foot print (consumes only memory it requires and processor)
	3. software
	4. ms is differ from module by having the distinction of hosting property
	5. boundry is it should need to have the purpose or service
	6. free of programming language(can use any language) and also free of transfer language(like json, xml, soap, etc..,)
2. DDD
	1. domain design driven
3. REST API
	1. tool which will make the Micro Services to communicate
	2. by providing API calls
4. Message brokers-Apache artemis,active MQ, rabbit MQ
5. Event Streaming - where ever action performed there is a event.(apache kafka)
	1. one event in service leads to the other service
6. DOCERS -
7. CUBERNETICS- for scaling
8. CONTAINER - container is a concept of using only the necessory software(in the available OS) instead of installing operating system(like vitual machine)
9. Transaction 
	1. only be done or not (no intermediate)
	2. had set of operations in it.
10. course
	1. application of MS
		1. CONTAINER TECHNOLOGY
		2. SCALABILITY
		3. TOLERANCE
		4. coupling and decoupling is possible
		5. programming lang is not specified
		6. technology agnostic
	2. architecture of MS
		1. composed of serveral applicaion
		2. communication btn these app leads to the business solution
		3. modification done efficiently
		4. organized around bussiness
		5. smart endpoints
		6. services provides an API endpoints
		7. usually stateless REST API
		8. API  mais standard
		9. easy of devleopers to consume
		10. suppots devops
		11. open source
	3. systen design and operations
		1. designing services depends on business
		2. each function can be developed into the microservice
		3. and divided futher if needed
		4. and one serivce exposed to others
		5. perisiten layer and store comes along with the module
			1. the encourages modularity
			2. encourages colabration
		6. microservices use cases
			1. business
			2. cpu processing
				1. file compression
				2. file converting
				3. video rendering
				4. NLP
				5. financial analysis
				6. modeling and predictive analysis
			3. ram processing
			4. database
		7. early versions of microservices
			1. EAI(enterprice application integration)(1820)
			2. RPC(remote procedure call)
				1. gave rise COBRA AND DCE and remote method invocation
			3. SOAP(simple object access protocol)
			4. SOA(service oriented architectrue)
			5. representational state transfer(rest)
			6. 
		8. monolothic approach
			1. several layers
				1. UI
				2. one or more applications 
				3. persistence layer
			2. monolothic approach dis
				1. sigle point of failure
				2. technology trap(built arround one vendor technology )
				3. horizontal scaling
				4. continious delivery
		9. SOA 
			1. cost centers within IT
				1. time to market
				2. manpower
				3. downtime
				4. infrastructure
				5. quality and performance
			2. Costs and Benefits
				1. Microservices and SOA offer similar ROI(Return of Investment)
				2. The ability to separate concerns and therefore make deployment more agile offers several benefits
					1. Better information flow
					2. Configuration flexibility, so mashups are possible
					3. Test individual services instead of the entire application
					4. Security as we expose only what is needed to accomplish a particular task
				3. SOA provides organizations with several savings options:
					1. Service reuse
					2. Integration savings
					3. Application management
					4. Other savings
			3. Implementation
				1. Implementation relies on
					1. Access or interface layer
					2. Business logic layer
					3. Services layer
					4. Data layer
					5. Service components
				2. SOA implementation requires both runtime environments as well as supporting tools
				3. Other implementation concerns:
					1. Security
					2. Supporting processes
					3. Supporting components
				4. three popular styles exist for actual implementation:
					1. gatewayusing APIs
					2. message broker style
					3. point to point style
				![[Pasted image 20240620175306.png]]
				1. Early Approaches
					1. Three major approaches stand out:
						1. Enterprise Application Integration (EAI)
						2. Common Object Request Broker Architecture (CORBA)
						3. Simple Object Access Protocol (SOAP)
					2. all these will allows communication btn services
					3. COBRA
						1. Traditional client-server type of approach
						2. Based on the Object model
						3. Supports modularization
						4. Objects can
							1. Run on any platform
							2. Reside anywhere on the network
							3. Be written in any language
					4. SOAP
						1. Data messaging rules
						2. Programming language agnostic and also<mark style="background: #FF5582A6;"> for OS.</mark>
						3. XML based
						4. Made up of An envelope
						5. A set of coding rules
						6. A convention for representing calls and responses
		10. Event Sourcing
			1. Object state determined by events
			2. Read-only event store
			3. Events can be "replayed"
			4. Advantages
				1. Answers "how" questions
				2. Auditing
				3. Integrity
			5. 2-phase commit process
			6. Current state of data
			7. Historical account of state
			8. Databases are distributed
			9. NoSQL databases
				1.  No support for ACID transactions
				2. No support for 2PC
			10. event trigges other events
			11. example of when stock level changes
		11. CQRS(command query responsibility segregation)
			1. separating read operations from update operations
				1. adv
					1. performance
					2. scalability
					3. security
				2. dis
					1. mismatches
					2. locking of records
					3. other security issues
				3. one model initiates all queries
				4. diff model maipulates data
				5. sep 
		12. some other patterns(three easy appterns)
			1. microsoft azure identified nine patterns
				1. the aggregator pattern
					1. reduces the inter-sevice communication
				2. proxy pattern
					1. req directed by proxy service
				3. chain pattern
		13. how to depoy the changes
			1. changes on the fly
			2. shorter life cycle
			3. push changes to a production as needed
			4. automation is implied
			5. microsevices + devops = increased uptime
			6. benefits
				1. shorter builds
				2. replicated
				3. agile enviroinment
		14. dependencies in microservices
			1. one depends on another
				1. may involve db or not
			2. considerations
				1. single datablse
				2. large volumes
				3. locking
			3. database changes
			4. design with dependency in mind
			5. sevices calling each other
			6. data sharing; data can be
				1. static 
				2. mutable
		15. modularized systems
			1. smoother testing
			2. better development and deployment
			3. microservices are modules
			4. they are also independent applications
			5. modularity principles;
				1. encapsulation
				2. well-defined interfaces
				3. explicit dependencies
			6. with microservices
				1. better team coordination
				2. less complexity
				3. 



2024-06-25 09:50
1. challenges is in microservices
	1. maintenence of communication btn microservices
	2. maintaining ip address and port number
	3. load balancing
	4. security
	5. server down
2. 



