---

title: Common message header bearing method and apparatu for converting soap API into rest API
abstract: A common message header bearer method for converting a SOAP API into a REST API includes: determining a REST API common message bearing field, where the common message bearing field is a field in a REST API message header and complies with a following format: one header field name+one header field value+multiple attribute-value pairs (); and bearing a relevant content of a SOAP message header in the common message bearing field in a format of the attribute-value pairs (). Embodiments of the present disclosure further provide an apparatus for converting a SOAP API into a REST API.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08776085&OS=08776085&RS=08776085
owner: Huawei Technologies Co., Ltd.
number: 08776085
owner_city: Shenzhen
owner_country: CN
publication_date: 20130314
---
This application is a continuation of International Application No. PCT CN2011 074949 filed on May 31 2011 which claims priority to Chinese Patent Application No. 201010516295.X filed on Oct. 20 2010 both of which are hereby incorporated by reference in their entireties.

The present disclosure relates to the field of communication technologies and in particular to a common message header bearer method and apparatus for converting a SOAP API into a REST API.

A Simple Object Access Protocol Application Programming Interface SOAP API Simple Object Access Protocol Application Programming Interface is an interface for implementing interconnection and interworking between application software systems based on a Web service mechanism. The SOAP API allows application software developed by using different operating systems and different languages to easily implement interworking. A complete SOAP API message includes a message header header bearer and a message body body bearer . The message header is used to bear common information for common processing such as authorization. The message body is used to bear service related information for service related processing.

A Representational State Transfer Application Programming Interface REST API Representational State Transfer Application Programming Interface is a common interoperable interface between Internet based WEB application capabilities that is an API complying with the REST style. A system corresponding to the API complying with the REST style is a REST style system. Features of the REST style system include the followings externally open information is a resource where the resource is identified by a Uniform Resource Identifier URI Uniform Resource Identifier of conventional WEB technologies only four operations are allowed for the externally open resource including add modify delete and get which respectively correspond to Post add Put modify Delete delete and Get get in the Hyper text Transfer Protocol HTTP Hyper Text Transfer Protocol of conventional WEB technologies.

With the fast development of the Internet it is expected that all capabilities may be open to the Internet. For example a conventional application system using Web services starts to open to the Internet. Therefore it is necessary to open the SOAP API as a corresponding REST API that is convert the SOAP API into the REST API . When the SOAP API is opened as the corresponding REST API contents of the service part will be abstracted into resources and the SOAP common message header part requires a common bearer point in the new REST API interface. Because WEB technologies use the HTTP protocol HTTP message headers of the HTTP protocol of WEB applications mainly bear fields related to negotiation between HTTP protocol clients and servers and HTTP message bodies mainly bear service messages. As a result when the SOAP API is converted into the REST API it is necessary to find an appropriate position in HTTP to carry the relevant content of a SOAP message header.

A prior art 1 provides a solution for converting the SOAP API into the REST API which is extending HTTP message header fields by adding contents which are to be carried by SOAP header and prefixed with X as follows 

This extension results in too many header field names in HTTP protocol fields which is confusing. In addition the extension of HTTP protocol fields is normally related to a bottom layer negotiation mechanism between HTTP protocol clients and servers and this extension reduces the processing speed of bottom layer negotiation between the clients and the servers.

A prior art 2 provides a solution for converting the SOAP API into the REST API which is carrying a SOAP message header in an HTTP message body.

However because an HTTP message body mainly bears service messages the inclusion of message header contents in an XML file of every service message results in strong association between service messages and message headers and weak independence in file and program processing. In addition during program processing the whole service message body must be parsed to complete authorization required by the message header which results in a low processing speed.

As a result the prior arts for converting the SOAP API into the REST API have the problem of redundancy and slow message processing.

Embodiments of the present disclosure provide a common message header bearer method and apparatus for converting a SOAP API into a REST API.

Embodiments of the present disclosure provide a common message header bearer method for converting a Simple Object Access Protocol Application Programming Interface SOAP API into a Representational State Transfer Application Programming Interface REST API including 

determining a REST API common message bearing field where the common message bearing field is a field in a REST API message header and complies with a following format one header field name one header field value multiple attribute value pairs and

bearing a relevant content of a SOAP message header in the common message bearing field in a format of the attribute value pairs.

Embodiments of the present disclosure provide an apparatus for converting a Simple Object Access Protocol Application Programming Interface SOAP API into a Representational State Transfer Application Programming Interface REST API including 

a determining unit configured to determine a REST API common message bearing field where the common message bearing field is a field complying with a following format one header field name one header field value multiple attribute value pairs and

a converting unit configured to bear a relevant content of a SOAP message header in the common message bearing field in a format of the attribute value pairs.

According to the solutions provided by embodiments of the present disclosure the relevant content of a SOAP message header is borne in a REST API common message bearing field and the common message bearing field is located in a REST API message header. Thereby the embodiments of the present disclosure prevent problems such as strong association between a service message and a message header and the necessity of parsing the whole service message body to complete authorization required by the message header during program processing which results in a low processing speed. In addition because the common message bearing field is a field complying with a format of one header field name one header field value multiple attribute value pairs a problem of slow bottom layer negotiation between a client and a server due to too many header field names may be effectively prevented.

Therefore the common message header bearer solutions provided by the embodiments of the present disclosure for converting a SOAP API into a REST API ensure system simplicity and good protocol parsing performance.

The solutions in the embodiments of the present disclosure are hereinafter described clearly and completely with reference to the accompanying drawings in the embodiments of the present disclosure. It may be understood that the described embodiments are only a part rather than all of the embodiments of the present disclosure. Based on the embodiments of the present disclosure all other embodiments obtained by persons of ordinary skill in the art without creative efforts shall fall within the protection scope of the present disclosure.

An embodiment of the present disclosure provides a common message header bearer method for converting a SOAP API into a REST API. As shown in the method includes the following steps.

Step Determine a REST API common message bearing field where the common message bearing field is a field in a REST API message header and complies with a following format one header field name one header field value multiple attribute value pairs.

The common message bearing field may be an existing field in the HTTP protocol such as an authorization Authorization field or a newly created field in the REST API. Either the existing field or the newly created field meets a format of one header field name one header field value multiple attribute value pairs thereby effectively preventing a problem of slow bottom layer negotiation between a client and a server resulting from too many header field names.

Embodiments of the present disclosure set no limit on the number of the attribute value pairs which may be two or more.

Step Bear a relevant content of a SOAP message header in the common message bearing field in a format of the attribute value pairs.

The content of the SOAP message header to be borne in the common message bearing field varies depending on application systems for interworking and the embodiment of the present disclosure sets no limit thereto.

Embodiments of the present disclosure provide a simple and convenient common message header bearer solution for converting a SOAP API into a REST API. Because the relevant content of a SOAP message header is borne in a REST API common message bearing field and the common message bearing field is located in a REST API message header the following problems are prevented problems such as strong association between a service message and a message header and the necessity of parsing the whole service message body to complete authorization required by the message header during program processing which results in a low processing speed. In addition because the common message bearing field is a field complying with a format of one header field name one header field value multiple attribute value pairs a problem of slow bottom layer negotiation between a client and a server due to too many header field names may be effectively prevented.

Therefore the method provided by embodiments of the present disclosure for converting a SOAP API into a REST API ensures system simplicity and good protocol parsing performance.

An example provided by an embodiment of the present disclosure for converting a SOAP API into a REST API is as follows.

The Authorization field of the HTTP protocol message header is extended as an example. By studying the Authorization field it is found that Authorization in the HTTP protocol is allowed to be extended to different authorization modes. For different authorization modes message attribute values that are carried may be randomly extended. In the example of converting a SOAP API into a REST API an extended protocol is as follows where the underlined part is the extended content. The extended field is the Authorization field in the HTTP protocol message header bearing negotiation related fields. The extended Authorization field contains a header field name Authorization a header field value EXAMPLEAUTH realm EXAMPLE and multiple attribute value pairs made up of attributes names attribute values such as devId 3500001 

In order to make the present disclosure more comprehensible the present disclosure is described by using a specific application scenario as follows 

An application scenario of the method provided by an embodiment of the present disclosure for converting a SOAP API into a REST API is that telecommunication capabilities are open to Internet applications for example a telecommunication carrier opens a short message capability to Internet applications.

An open REST API common message header carries information such as an Internet application provider and an application identifier to a telecommunication capability opening gateway and the telecommunication capability opening gateway needs to authorize the application provider and application identifier. In the example the relevant content of the SOAP message header is stored in the Authorization field of HTTP. The telecommunication capability opening gateway may obtain HTTP bottom layer Authorization information to perform authorization and does not need to parse a service message thereby improving the processing speed. The specific REST API message is as follows Authorization is the header field name EXAMPLEAUTH realm EXAMPLE is the header field value and the underlined part is the extended field which contains the relevant content of the SOAP message header added to the Authorization field in a format of multiple attribute value pairs.

Another application scenario of the method provided by an embodiment of the present disclosure for converting a SOAP API into a REST API is that telecommunication capabilities are open to terminal applications for example the telecommunication location capability is open to terminal applications.

When obtaining its own location or the locations of other users a terminal application needs to carry a common message header to a capability opening gateway for authorization. The common message header may be carried in the Authorization field of the REST API. An example of a message to be delivered is as follows in which Authorization is the header field name EXAMPLEAUTH realm EXAMPLE is the header field value and the underlined part is the extended field containing the relevant content of the common message header added to the Authorization field in a format of multiple attribute value pairs 

An embodiment of the present disclosure provides an apparatus for converting a SOAP API into a REST API as shown in including 

a determining unit configured to determine a REST API common message bearing field where the common message bearing field is a field in a REST API message header and complies with a following format one header field name one header field value multiple attribute value pairs and each attribute value pair includes an attribute name an attribute value and

a converting unit configured to bear a relevant content of a SOAP message header in the common message bearing field in a format of the attribute value pairs.

a selecting subunit configured to select the common message bearing field from existing fields of a REST API message header where the selected field includes an authentication field.

a creating subunit configured to create the common message bearing field in a REST API message header.

Embodiments of the present disclosure provide an apparatus for converting a SOAP API into a REST API. Because the relevant content of a SOAP message header is borne in a REST API common message bearing field and the common message bearing field is located in a REST API message header the following problems are prevented problems such as strong association between a service message and a message header and the necessity of parsing the whole service message body to complete authorization required by the message header during program processing which results in a low processing speed. In addition because the common message bearing field is a field complying with a format of one header field name one header field value multiple attribute value pairs a problem of slow bottom layer negotiation between a client and a server due to too many header field names may be effectively prevented.

Therefore the apparatus provided by embodiments of the present disclosure for converting a SOAP API into a REST API ensures system simplicity and good protocol parsing performance.

To sum up according to embodiments of the present disclosure the relevant content of a SOAP message header is borne in a REST API common message bearing field and the common message bearing field is located in a REST API message header. Thereby the following problems are prevented problems such as strong association between a service message and a message header the necessity of parsing the whole service message body to complete authorization required by the message header during program processing which results in a low processing speed. In addition because the common message bearing field is a field complying with a format of one header field name one header field value multiple attribute value pairs a problem of slow bottom layer negotiation between a client and a server due to too many header field names may be effectively prevented.

Therefore the common message header bearer solution provided by embodiments of the present disclosure for converting a SOAP API into a REST API ensures system simplicity and good protocol parsing performance.

Persons of ordinary skill in the art may understand that all or a part of the steps of the method according to embodiments may be implemented by a program instructing relevant hardware. The program may be stored in a computer readable storage medium and the storage medium may be a read only memory ROM for short a random access memory RAM for short a magnetic disk a CD ROM and so on.

The above are only preferred embodiments of the present disclosure. The protection scope of the present disclosure however is not limited thereto. Any variation or substitution that is within the scope disclosed by the present disclosure and can be easily conceived for those skilled in the art should be covered in the protection scope of the present disclosure. Hence the protection scope of the present disclosure should be determined by the claims.

