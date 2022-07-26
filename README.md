# Data warehouse requirements task

Welcome to a test exercise for system analytics. You will be given a short, three paragraph long, description of a software product called "Data warehouse". Based on the description you are expected to create two outputs: three user stories, small data architecture containing at-least three items. The description may not contain complete information for each identifiable user story or data structure. If such an occasion arises you should highlight any of such pieces of missing information and point out questions by which these gaps can be filled. Do also note that you do not have to incorporate all the requirements from the description to the user stories and data structures, choose freely on which parts you want to focus on. 

Estimated time to complete this task is ca 1-2 hours. That should also serve as a hint of expected level of detail in the submission. Good luck!

### Expected outputs

- Three user stories following the classical format of "*As a [persona], I [want to], [so that].*". Keep the scope of the stories smaller than 2 person-weeks (so they would fit into a single sprint of one developer).

- (Partial) data architecture of the data warehouse. Format should be kept similar to the UML Class Diagram. Please highlight relationships between data structures if any exists.  

### Submission

1. Fork this repository

2. Format your main document as a `markdown` file (architecture can be embedded as a picture) and add it the repository.

3. Send a link to your public repository via e-mail.

### Evaluation

Your submission will be evaluated in the following categories:

- Quality of the user stories

- Quality of the data architecture

- Capability to generate questions for missing information

- Capability to use technologies such as `git` and `markdown` for submission

## Data warehouse description

In context of  a Cyber Range architecture a data warehouse is a sub-system that is capable of storing various exercise artifacts. Those include, but are not limited to: virtual machines, operating systems,
software, configuration files, text, audio, video, etc. All stored artifacts must contain information for integrity checking, version control, ownership and licensing. Data warehouse must support organizing, storing, yanking and retrieving operations. Artifact metadata for those must be available without downloading the entire artifact to the users machine. Artifacts also may be dependant upon other artifacts, therefore, the system must be capable of generating a reproducible dependency graph.

Data warehouse defines two types of users: administrators and regular users. The system does not store local user authentication information. Instead, external services (AD, LDAP, etc) are used for authentication and authorization purposes. Authorization for downloading an artifact is determined by a access rule set by the artifacts author, all other actions can only be performed by the author. Name, version and checksum of all artifacts can be accessed without any authentication. Differentiating factors between the regular user and the administrator are: administrator can set the authentication configuration, administrator can access all the operations on all the artifacts without authorization. 

Users can communicate with the data warehouse through the following three interfaces: a web-client, an API and a CLI-client. Furthermore, CLI will be used by the automation tools to incorporate functionality of the data warehouse into external systems. For example, CLI can be used in the exercise deployment phase, where virtual-machine definitions are used for creating templates on the hypervisor. In addition, CLI must support working with multiple instances of data warehouse at the same. This may occur in a hypothetical situation where necessary packages are divided between two different data warehouses. 
