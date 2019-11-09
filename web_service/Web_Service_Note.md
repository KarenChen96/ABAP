BC416 Web Service

# Unit 1. Overview
## Lesson 1. Introduction to Web service
### What is a Web service

Features:
- A Web service is an independent, modularized, self-describing application function or service.
- Based on XML standards, these application functions can be manipulated via Internet protocols.

### Web Service Paradigm
> Service Provider

If the service is a Web service:
- Service Provider will have a corrresponding XML-based description(WSDL document). 
- The service can be implemented by any proramming language.
- Bases on the HTTP transport protocol, Simple Object Access Protocol (SOAP) is established as the quasi-standard access protocol. (:thinking: what's the difference between the transport protocol and the access protocol????)

> Service Registry
- When publishing a service, the service provider transmits its own information ans a description of the service it is offering.
- The service registery therefore provides a description of the Web service (an abstract layer) but no detailed implementation.

> Service Requester (Client)
- An application can either access a Web serive, or bind to the service request (The application can create a Web service client proxy at runtime in order to access the Web service).
- An application can obtain the necessary information for accessing the service from: 
    - The service description stored in the service registery;
    - Use the service directly if recognizeing the provider and the call details. (No need to find the service in the registery.)

### Central Internet Standard for Web Services
- WSDL: A standard description of the Web service used for Web services are to be called from any applications.
- UDDI: A "register of companies" helpful for finding the right business partner and corresponding service quotation.
    - UDDI provides:
        - UDDI specification providing a description of how to locate and register services.
        - UDDI Business Registery containing a list of registered companies with their services offering.
- SOAP: An appropriate protocol used to call/execute Web services (in decentralized, distributed landscapes) based on Internet technologies. 

Some used terms:
- XML: eXtensible markup language for exchanging etructured documents over the Internet.
- SOAP: it specifies a package of XML documents for transport via Internet protocols such HTTP(S), SMTP, FTP. It's used to call Web services in distributed system landscape.
- WSDL: It's an XML-based description language for Web services, is an integral part of UDDI.
- UDDI: It's a Web-based registry can be accessed via the Internet. It doesn't store documents or specifications, only references to them.

:thinking: Understand the Credit-check example!

### Web Service Supprt in SAP NetWeaver Application Server
- Existing BAPI, remote-enabled function modules, Enterprise JavaBeans(EJBs), Java classes, ans SAP XI server proxies can be used to set up a Web service. (:Thinking: What are their functionality? When and How tp use them?)
- SAP NetWeaver AS implements the basic standards for Web services here: XML, SOAP, WSDL, UDDI. 
- Web Service Framework is provided as a separate infrastructure for the development, publication, and use of Web services. It consists of:
    - A distributed and interperable SOAP runtime (Web AS ABAP or Java).
    - ABAP Workbench/SAP NetWeaver Developer Studio provides an environment for publishing, searching, and calling Web services. It enables SAP NetWeaver AS to act as both a server and a client.
        - The Web AS ABAP development environment; Web services can be crated and are integrated in SE80 (ABAP Workbench).
        - The Web AS Java development environment; Web services can be crated and are integrated in SAP NetWeaver Developer Studio.
    - Tools for supprting UDDI registration.
- SOAP requests for Web services implemented in ABAP are processed using the Internet Communication Framework(ICF).

> :thinking:
SAP Web Application Server contains: 
- Mandatory: development environment; Web service Meta data; Web service Runtime(???);
- As a server: Virtual Interface, Standard Interfaces (provided by BAPI etc.), Business Application(???). A server then can provide a web service.
- As a client: Web service proxy, Web service Client Application(???).
> Confused: what's the relationship between the Business Application and a Web service?


### SAP NetWeaver AS as a Web service provider
In this case, it allows SAP users to use Existing BAPI, remote-enabled function modules, Enterprise JavaBeans(EJBs), Java classes, ans SAP XI server proxies for setting up a web service.

2 different procedures to prepare a Web service:
- web service creation wizard: contains predefined profiles with predefined settings.
- step-by-step procedure: allow to iplement individual customizations.

> Virtual Interface
SAP users use SAP NetWeaver AS as the backend server, use existing BAPI etc as the tools to set up a web service. These tools provide some standard interfaces, then map these interfaces to the Virtual interface to be provided to the client.

### SAP NetWeaver AS as a Web service client

A client proxy must be generated before a We service can be implmented in an application.
- It is generated using the Web service's WSDL document (can be found in the UDDI business registry using a URL/HTTP destination or in a local file).
- A client proxy acts as a processor to connect the server of the service, so that the developer can concentrate on the business applicaiton.

### SAP's Web service Solution
An undelying platform of a Web service should support open technology standards for Web services.

Therefore, SAP provides the SAP NetWeaver whose AS supprts these technologies. And, SAP system integrates many business processes as Web services.

## Lesson 2. ESA and Web Services
Core terms in SAP NetWeaver environment: composite applicantions, enterprise services, Web Services.
### Evolution of SAP Basis to NetWeaver AS
Discernible(distinguishable) trend: 
  monolithic application wit proprietry protocols & programming languages ==> open standards & flexible system architectures.

### Current Challenges in Companies with Expanding IT Landscapes

### Enterprise Services Architecture: New Options for Integration
SAP NetWeaver comes in to avoid tight coupled architecture.
> This is an infrastructure... T0-be-continue...

# Unit 2: Fundamentals of ABAP Web service technology
Key: RFC, BAPI, HTTP, XML, SOAP.

## Lesson 1: Basics of RFC and BAPIs
### Function module
> Function Module Basics
- A function module comprises the actual source tcode executed at runtime, the interface/signature, the properties.
- The interface incorporates: Import/Export parameters, Table parameters, Exception parameters.

- Examine function modules: The function library (part of the Function Builder/SE37) or in the Object Navigator(SE80).
- The properties of a function module are important for the external utilization, as the remote-enabled attribute must be set here.
- RFC: Remote Function Call; RFM: Remote Function Module.
- ABAP Dictionary: Display Structure/Data Element. (:thinking: Not very clear about Data Element)

> Function Module Test
:thinking: Don't know how...

> BAPI (Business Application Programming Interface)
BAPIs can be regarded as a subgroup of RFC-enabled function modules.

## Lesson 2: Basics of HTTP
- Reference: https://www.w3.org/Protocols/
- Introduce how communication via the Internet works and teh TCP/IP reference model
- Introcude HTTP (application) protocol based on TCP/IP (communication) protocol. 

### When the Internet was Born
- Origin  of Internet: ARPANET developed by a U.S. militrary network Advanced Research Projects Agency in 1969.
- Reuquirement of this decentralized system: 1. prevent total network failure; 2. facilitate communication between different computer types.
- A need for a new data transport protocol gave rise to TCP/IP which was developed in 1970.
    - TCP/IP is available for almost allhardware ans most OS.

### The TCP/IP Reference Model
It describes the structure of and interaction between the network protocols, and arranges them into 4 tiers. It is also referred to as a protocol stack. (We can design any network structure as we like, so don't be confused with the layered structure you learned before.)

> To Be Continue: details about each layer

### HTTP: A Special TCP/IP-Based Protocol
- HTTP (HyperText Transport Protocol), developed by Tim Berners-Lee, is an application protocol.
- It is used in the communication between client and server based on messages in text format. The server listens to a port at the request of a client.
- A Web service can be called from an HTTP client using a URL (Uniform Resource Location).
    - URL = transport protocol (http://) + host name + domain name with the top level domain. (domain? :thinking:)
    - The specific for the TCP port is required only if the connection is handled through a port other than stamdard port 80.
    - Paths and files are separated using a forward slash (/). If no path or file is specified, a default file is returned.
 
### Format of HTTP Messages
Messages exchaning between the client and server consist maily of HTTP header & the actual data.
The header entries are arranged into 4 categories:
- Request Line / Status Line: 
    - Request: specify which object is to be accessed with which method; the protocol version; 
    - Response: the protocol version & the status code
- General Header: Contained both in the requests and in the responses. 
    - These queryable fileds exist: Cache-Control, Connection, Date, Pragma, Transfer-Encoding, Upgrade, and Via. 
- Request/Response Header:
    - The response header transmits additional information about the server: Age, Location, etc.
- Entity Header: Describes the data part of the message.
    - Transmits information about the length or about the last change to the document.
    - If no entity body, it also provides information about the resources.
- Entity Body: Contains the actual data that was requested. This can be either the **client's user data** or **the server's response**.

### HTTP Status Code
1xx - Information code
2xx - Request succeed: received, understood, and accepted by the server.
3xx - Request is redirecte by the server
4xx - Request couldn't be processed by the server because of the client 
5xx - The server couldn't process the request because of an error.

### HTTP Methods
- GET/POST/PUT/DELETE
- HEAD/TRACE/CONNECT


## Lesson3: Basics of XML
World Wide Web Consortium(W3C)

### HTML(Hypertext Markup Language)
- HTML is developed by the founder of the Internet, Tim Berners-Lee.
- HTML documents are test filkes thta contain data and associated formatting instructions in the form of HTML tags.
- Cons: No provisions were made for adding extratags to the HTML vocabulary.

### XML( Extensible Markup Language)
- XML documents mirror the structured data and can be exchanged using common Internet protocols.

### XML Syntax
- Every XML document begins with an XML declaration thta identifies the XML version.
- Unlike HTML, it only contains universal data description but no element formatting.
- An element without element contant can be: <tagNmae attrName="attrWert" />.
- If a sign occurs in the XML syntax, it shoulbe be substitued by a placeholder. 

        < => &lt    > => &gt    & => &amp
- An XML document can be interpreted as a tree structure because of its tag hierarchy (root node, parent node, child node).

### Document Type Definition(DTD)
- Usage: when the same stucatures are to be used repeatly for differnet XML documents, or certain rules pertaining to the sequence and repeatability of elements are to be followed. (与元素顺序和重复性相关的某些规则)
- Functionality: check the validity of the XML structure

Example:
    
    // XML document declaration
    <?xml version="1.0" encoding="utf-8"?>

    <!DOCTYPE connections SYSTEM "connections.dtd">
    ......

### XML Schema
- XML Schema Description language(XSD): The syntax within the schema based on XML.
- "schemaLocation"/"noNamespaceSchemaLocation" attribute is used to establish a link to the schrema in the XML root element.
    
        <XMLRootNode xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespceSchemaLocation="schema01.xsd >

- <xsd:schema> is used as the root element in the schema document. 
- Define elements and attributes using <xsd:element> & <xsd:attribute>

### Validity and Well-Formed XML Documents

### XML Namespace
- Every namespace is uniquely defined by a Uniform Resource Identifier(URI). A URL can be used as a URI.
- The xmlns attribute, which contains teh namespace as an attribute value, is added to the tag to assign the namespace. 

        <connections xmlns="http://www.company1.com/xyz"
                     xmlns:nsl="http://www.company2.com">

- Qualified name is used when elements fomr different namspaces are mixed. (:thinking:)

### Transformation of XML
- Stylesheets can be used to make the data of an XML document visible. This data can be prepared foe the World Wide Web with Cascading Stylesheets(CSS). But Extensible Styplesheet Language is better.
- XSL(Extensible Stylesheet Language) can be used to display information on the Internet and create the most diverse output formats.
- Transformation: coversion of XML structures to other structures.
- A control file, such as an XSL stylesheet, is used to define the conversion rules for the elements of the XML file.
- The process of converting to the intermediate document is referred to as XSL Transfomr(XSLT).


## Lesson 4: Basics of SOAP (Simple Object Access Protocol)

### SOAP Intoduction
- SOAP is a transfer and packaging protocol standarized by W3C. 
- It's fcuntion is to exchange structured and typed information and messages **based on XML** between applications in **a decentralized, shared environment** such as the Internet.
- The SOAP specification doesn't stipulate transport protocol but it's connected with the HTTP transport protocol commonly so that applications can communicate with remote systems via a standard Internet protocol.
- SOAP is platform- and programming language independent.
- When using SOAP vais HTTP, the content type of the HTTP message should be set to text/xml, and SOAPAction should be set in the HTTP header.
    - SOAPAction entry enable firewalls to identify SOAP messages and let them through without checking the XML data.

### Structure of a SOAP Message
The SOAP Envelop incorporates 2 elements:
1. Optional SOAP header, containing the information about how to process the SOAP messages; (There may be more than one header block, because once the message is processed by an intermediate agent, this agent will add a header block.)
2. Mandatory SOAP body, contianing the actual user data of the message(payload) in XML format.

Main componentsof a SOAP message:
- *xmlns*: 
    - define the namespace for formatting a SOAP message. 
    - The attribute points to the underlying XML schema. 
    - It is assigned within the Envelop root element.
    
> TO BE CONTINUE...

### The SOAP Communication Model
- The messages may pass through different intermediate stations (called agents). 
- The route covered by a message is called a message path.
- SOAP specifies which parts of a SOAP message to be processed by which agent. 
- The SOAP body is only intended for the end node within the message profile.
- Message path is undefined and random.

### SOAP Faults for Error Handling
- SOAP fault element is inserted in the message body id a processing error occurs.
- The fault element can only be included once.

### Remote Procedure Call with SOAP
The Remote Procedure Call is a widely used SOAP application. 
- The method call is encoded as follows: The method call is modeled as a structure ans the interface parameters are the child elementsof this structure.
- The result of the method is also sent back to the client within a SOAP message. A SOAP fault element is returned is an error occured.

### Seperation of Technologies

### SOAP at SAP


# Unit 3: Web Service for SAP NetWeaver Application Server 6.40

## Lesson 1: Introduction to the Internet Control Framework(ICF)
Target: Know how the HTTP calls to ABAP system are processed.

### System Architecture
- A classcial SAP R/3 system has a three-layer client/server architecture: presentation layer, applicaiton layer, db layer. 
- SAP Web Application Server adds a new process, **the Internet Communication Manager(ICM)** on the SAP Kernel.
- This new process enables direct processing of requests that are created using a Web browser and HTTP protocol, for example, from the Internet or intranet.

### Internet Communication Framework
- ICF provides the environment for handling HTTP requests in an SAP system workflow (server and client).
- The ICF consists of ABAP classes and interfaces whose instances can be initiated to allow access to the request and response data.
- The IF_HTTP_SERVER interface for servers and the IF_HTTP_CLIENT interface for clients.



### HTTP Service Tree


## Lesson 2: SAP NetWeaver AS(Application Server) as a Web Sevice Server

Based on the standard interfaces of a business application, any self-contained, modularized functionality that is implemented as a BAPI, RFC-enables fuction module, Enterprise JavaBean (session bean), or Java class lends itself to the deployment as a Web service with the help of SAP NetWeaver technology. => functionlaity lends itself to (适用于) the deployment as a Web Service.

Target: learn how a Web Service is created and registered on the server side.

### Web Service Creation Wizard: The Fast Route to a Web Service
The following objects are generated by the Web Service Creaiton Wizard:
- Virtual Interface: A visual representation of a Web service. Using VIs, we can define several views for one implementation and publish them separately as a Web service. 
- Web Service Definition(WSD): For one VI, you can create several Web service definitions with differing features. Features like the cpmmunication type, authentication level, transpaort properties are assigned in abstract form in a WSD.
- Web Service Config

### Using the Web Service Creation Wizard

Endpoint type: function moudle, function group, BAPI

### Web Service Homepage

### Approach to Creat a Web Service
- Step 1: Implement the business logic: Business processes that are to be released as ABAP Web services can be encapsulated within RFC-enabled function module/function groups/BAPIs/XI message interfaces.
- Step 2: Define the virtual interface; 


## Lesson 3: WSDL Introduction

### Definition of WSDL
Web Service Description Language: provides a description of distributed systems and information about the automation of data exchange between applications (in XML format).

A service is described as an accumulation of ens points(ports) and the messageS that these work with.

Service providers use WSDL to provide the requirements and functions of the Web service.

WSDL is not fixed on nay special message or network protocol.

WSDL is used to define operational interface which defines language- and platform-independent messages for exchange.

### Use of WSDL
The same Web service can be called from different systems, independent of their technical features. 
The implementation of the Web service client is not dependent on the technical structure of the server.
Consumers are generated from an implementation-independent service definition.
The technical details are configures in the Web service comsumer's runtime environment.
????:thinking:

### WSDL Elements
                                        Binding
Abstract description of the interface <=========> The concrete part containing the physical protocols and addresses for communication.
Protocols: SOPA, HRRP, MIE, and so on.
Address: concrete network address and HTTP ports of the endpoints or Web services

A WSDL documents defines services as a group of network ports. 


### WSDL of SAP Web AS ABAP
Target: Integrate an ABAP Web service into an ABAP application using the ABAP workbench.
- Gnerate a proxy using a WSDL document;
- Define a logical port;
- Call a Web service from an ABAP program.



## Lesson 4: SAP NetWeaver AS as a Web Service Client
### Web Service: The Client Side
SAP NetWeaver can support not only creating a web service as a server but also calling a web service as a client.

> Web Service Client Proxies
- A client proxy should be generated to act as a transfer program, used to connect the server of the required service, before a Web service can be implemented in an application. 
- The client proxy is generated in SE80 using a Web service description(WSDL document). Loading the description is optional (from a URL, a UDDI server, the SAP Exchange Infrastructure).

> Logical Port

When a proxy is generated, all objects required to call a Web service are created, including the logical port. Logical port is an SAP-specific concept fro configuring the runtime features for Web service client proxies.
- Runtime features for Web service client proxies:
    - Configured at the time of activation of the Web service client.
    - Example: the URL for calling the Web service, which may need to be customized by a user.
- Design time features
    - Designed by the application user during development and are suppied together with the Web service client proxy.
    - Example: Whether communication between the client ans server should be session-oriented.
- Configuration data (runtime features) is seperated from the implementation (desgin-time features) in the Web service framework.
    - So that when moving from the test system to the live system, we can customize the URL and other important parameters in the logical port to make the client proxy call the Web service on the live system.

### Steps of implementing a Web service in the client side
Step 1: Call the web service description
Step 2: Generate a web service client proxy
Step 3: create a logical port
Step 4: Implement the client application


### Tips on Generating Proxies
1. Name Confilct: The prefix can't start with 'X', etc.
2. Translation and package assignment: Ensure proxy objects are separated at package level.
3. User access: ... 

Externla WSDL/Schema:
- Local file: no authorization to create a change reques
- URL: No authorization to access the url...



## Lesson 5: Web Service Error Analysis


## Lesson 6: UDDI Introduction



# Unit 4: Preview
## Lesson 1: SAP XI and Web Services
## Lesson 2: E-Business Standards




# Coach Session
cj20: Purchase order, wbs 

qj6 - drf: check its configuration guide
it is for cloud development.


SAP has developed its own BSP, similar to JS but toally written in ABAP. (Reference: Microsoft ASP)
And it evolves to another ... But now we use Fiori.

Different systems represent different development phases.
Once save, others will see my changes to the code/table; Once activate, user/developer runs the new version.

Pull the request to push my change to next system to make them be tested/production, etc.

CDS view is used to: 1. to generate OData structure; 2. convert to JS file and generate Fiori UI.
