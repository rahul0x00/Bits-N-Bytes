# SSRF
Server Side Request Forgery attacks

## Introduction
Server-side request forgery is a web security vulnerability that allows an attacker to induce the server-side application to make requests to an unintended location.

In a typical SSRF attack, the attacker might cause the server to make a connection to internal-only services within the organization's infrastructure. In other cases, they may be able to force the server to connect to arbitrary external systems, potentially leaking sensitive data such as authorization credentials.

## Typical attack steps
1. Scan internal network to determine internal infrastructure which you may access
2. Collect opened ports at localhost and other internal hosts which you want (basically by time-based determination)
3. Determine services/daemons on ports using [wiki](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#bookmark=id.c26g9qyp2i8t) or [daemons banners](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#bookmark=id.bpk4tpy1tk6o) (if you may watch output)
4. Determine type of you SSRF combination:
    - Direct socket access (such as this [example](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#bookmark=id.g75p1qafgyar))
    - Sockets client (such as java URI, cURL, LWP, others)
5. In case of direct socket access determine CRLF and other injections for smuggling
6. In case of sockets client, determine available [URI schemas](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#bookmark=id.osggnj3pn7l6)
7. Compare available schemas and services/daemons protocols to find [smuggling possibilities](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit#bookmark=id.s5sdux8jzzp8)
8. Determine host-based auth daemons and try to exploit it

## Vulnerabilities
There are number of vulnerabilities which can provide SSRF attacks. Basically they can be determined by this groups:
- Format processing
    - XML
        - XXE
        - DTD remote access
        - XML design
    - OpenOffice
        - DDE formulas
        - Dynamic data linking
        - External resource embedding
    - PDF (TCPDF)
- Direct sockets access
    - CRLF injection
- Net library URL processing (unsafe server-side redirect and others)
    - cURL
    - LWP
    - ASP.NET URI
    - Java URI
- External data linking
    - Databases
        - Postgres
        - MySQL
        - MondoDB
        - Redis
        - Oracle

### Further Resources
- [SSRF Bible Cheatsheet](https://docs.google.com/document/d/1v1TkWZtrhzRLy0bYXBcdLUedXGb9njTNIJXa3u9akHM/edit)
- [PayloadsAllTheThings - Server-Side Request Forgery](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Request%20Forgery)