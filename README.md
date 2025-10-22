# 🚀 Backend Developer Roadmap

## What is this?

This document contains a roadmap of skills frequently required for backend developers of web applications. The document is divided into stages (topics). Each stage is divided into items. Each item in the document assumes that:

- The backend developer knows what it is and what problem it solves
- The backend developer knows why and when it should be applied
- The backend developer knows how to work with it or knows where to look it up
- During development or design, the backend developer remembers them and takes them into account in the application

Understanding the principle of operation of each item will be an additional bonus in understanding the entire topic, but this can take a lot of time. Study as you wish and as needed.

## How to work with the document?

Stages and items are arranged in the recommended order for study. Simply follow from top to bottom.

## How to work with document items?

Each item is easily googled and has a Wikipedia page. Links are provided if there is alternative documentation - clearer and/or more detailed. Some links may require VPN. Wikipedia links are provided for clarification if the article title is not obvious or articles could be confused.

Quotes indicate explanations for why you should know this and/or where you might encounter it. If there is no explanation, either it hasn't been added yet, or it's already clear.

## Is there a skill division?

Each item is divided into gradations: **junior** 🌱, **middle** 🌿, **middle+** 🌳 (also known as high middle). Gradations are used to help prioritize different topics - what should be studied first. This uses the generally accepted gradation of skills and areas of responsibility, where senior is middle+ with soft skills. In this document, the maximum gradation level will be middle+, since this document focuses on hard skills.

The **guru** ⚡ label means that this item is for deeper and more advanced study of the topic (if you have time).

## What is the document status?

The document is still in the process of additions and corrections. Ideally, each item should have a gradation, an explanation, and a link to good documentation. We're far from ideal, but it's a start!

If you want to change something (item, link, typo) - create an issue or make a PR. If you want to discuss the document - create a discussion in discussions.

---

## Contents


1. [Stage 1. General Knowledge](#stage-1-general-knowledge)
2. [Stage 2. Networking](#stage-2-networking)
3. [Stage 3. Databases](#stage-3-databases)
4. [Stage 4. HTTP Protocol](#stage-4-http-protocol)
5. [Stage 5. Security](#stage-5-security)
6. [Stage 6. Programming Language](#stage-6-your-programming-language)
7. [Stage 7. Email](#stage-7-email)
8. [Stage 8. Full-Text Search](#stage-8-full-text-search)
9. [Stage 9. Logs and Metrics](#stage-9-logs-and-metrics)
10. [Stage 10. Design and Development](#stage-10-design-and-development)
11. [Stage 11. Docker Virtualization](#stage-11-docker-virtualization)
12. [Stage 12. Linux](#stage-12-linux)

---


## Stage 1. General Knowledge

Some items are difficult to categorize in this document. But they are indispensable. These are basic things that are used everywhere in code, in systems, "under the hood" of your programming language.

- **Regular expressions**. You can play with regular expressions here. Although each language may have its own vision of regular expressions, in general sense (and syntax) they are similar 🌿
  > Sooner or later you will have to parse data from text or check data, and this is where regular expressions will be needed.

### Cryptography

- **Cryptography** 🌱
  > Don't be scared. The item implies practical application of cryptographic functions (what various functions are needed for), not studying cryptography itself.

- **Hashes and hash functions**, including crc32, md5, sha1, sha256 🌱
- **Digital signatures** 🌱
  > To protect data from forgery, digital signatures of the same data are used.

- **Salt for signatures** 🌿
  > In theory (and in practice) a hash function can be determined and to further protect from "hacking" your hash, using so-called salt.

- **Hash collisions** 🌿
  > Hash functions can return the same result (hash) on different data, which can lead to problems and bugs. It's better to know what the probability of collisions for a hash function is and how to avoid them.

- **Symmetric and asymmetric encryption** 🌳
  > Sometimes you have to encrypt data and it's important to choose an encryption strategy.

- **TLS operation principle** 🌳
  > Meaning how CA root and intermediate work, what's behind the certificate.

### Git

- **Basic git work** 🌱
  > In fact, this is the default version control system in the IT world.

- **Committing changes (commit)** 🌱
- **Sending changes (push/pull)** 🌱
- **Creating branches and tags (branch/tag)** 🌱
- **Merging branches (merge)** 🌱
- **Master git completely** ⚡

### Data Structures

- **Data structures** 🌱
- **Hash tables** 🌿
  > Tables are often used in programming languages themselves (associative arrays, objects, etc.)

- **Queue and stack** 🌱
  > The simplest data structures that will often have to be used daily in code.

- **Linked list and doubly linked list** 🌿
  > These data structures are often used in development as they are the simplest way to connect elements with themselves. They are also actively used inside your language ("under the hood") everywhere.

### Data Storage and Transfer Formats

**Text** 🌱
> Text formats are also used for storing application configuration

- JSON
- YAML
- XML

**Binary** 🌿
> Binary formats are used solely for storing and transferring data.

- MessagePack
- BSON (binary analogue of JSON)
- ProtoBuf

---

## Stage 2. Networking

Networking in development is the most important and, often, least noticeable part.

- **Basic understanding of how networking works** 🌱
- **TCP protocol** 🌿
  > You are unlikely to read TCP packets. But it's useful to know HOW TCP works, this will allow you to understand why even with perfect "internet" the application can still lag on the network.

- **TCP packet** ⚡
  > You're unlikely to have to work with TCP packet directly, however from its structure you can glean some useful information about the TCP protocol in general.

- **Flags** ACK, SYN, FIN and others 🌳
  > Flags are responsible for organizing, confirming transmission and closing TCP connections.

- **Buffers (window size)** 🌿
- **TCP problems** 🌳
  > TCP is a very old protocol that no longer meets modern realities.

- **UDP protocol** 🌿
  > The simplest network protocol of the family. Understanding its operation is required. HTTP/3.0, DNS work on UDP protocol, and understanding UDP will give some understanding of HTTP/3.0 operation.

- **UDP packet** ⚡
  > You'll only have to study if you need to create your own data transfer protocol to replace the outdated TCP.

### Network Problems

- **Network problems** 🌱
  > There are always many. But it's worth highlighting those that clearly affect network speed. For the most part, these problems are inherent to TCP, but can also appear where TCP is emulated - on another protocol (for example UDP)

- **Packet loss** 🌱
- **Reordering** 🌿
- **Jitter** 🌿
- **Round-Trip Time (RTT aka lag)** 🌱
- **Network latency (delay)** 🌿

### IP

- **IPv4, IPv6**
  > Basic difference between protocols should be known, at least to correctly create an IP column in the database and processing in code.

### DNS

- **DNS** 🌱
  > Your code will work with domains 24/7 as nobody uses pure IP to connect to anything. Knowing how DNS works and managing domain resolution in the system can simplify debugging in some cases.

- **How domain resolution works** 🌱
- **DNS records** 🌿
- **Main** MX, CNAME, NS, A, AAAA, TXT 🌿
- **Other records** 🌳
- **File** /etc/hosts 🌱
  > The simplest and most accessible way to change the IP of any domain, locally, of course.

- **File** /etc/resolv.conf 🌳
  > Configuration for the system on how and where domains should be resolved.

- **Console commands for working with domains**: whois, dig, host 🌱
  > To identify a problem with a domain you need to learn to work with these commands. Analyze domains both through the default DNS and through public ones, such as 1.1.1.1 or 8.8.8.8.

- **Route tracing** 🌿
- **Traffic analysis** via tcpdump + wireshark ⚡
  > Not simple, but very effective way to "see" and analyze traffic in a convenient UI.

- **Master networking completely** ⚡

---

## Stage 3. Databases

Without databases - nowhere. The most common type of database is relational databases. Therefore, even junior should be able to work with them, but NoSQL databases can be familiarized with a little later.

### Relational Databases

- **Relational databases** MySQL/Postgres/etc. 🌱
  > MySQL implies both Oracle's MySQL and various variants like MariaDB, Percona XTraDB, etc. In general understanding of the family: MySQL/Postgres/MSSQL/etc. have similar SQL APIs, differing only in internal implementation, performance and scalability.

- **Basic query syntax** SELECT/INSERT/UPDATE/DELETE 🌱
- **Creating and modifying tables** 🌱
- **Table column types**, their purpose and differences 🌱
  - Integer types (int)
  - Text types (text)
  - Sets, enumerations (enum)
  - String types (char, varchar)
  - Decimal types (decimal)
  - Floating point numbers (double)
  - others

- **Creating and applying ALTER queries** 🌱
- **Query execution analysis** via EXPLAIN, understanding EXPLAIN results 🌱
  > The most effective way to understand why a query is slow.

### Performance Diagnostics

**Performance diagnostics**
> Slow queries will always appear, and the more there are, the slower your application will work. And as a rule, different databases always have analytics for finding "bottlenecks".

- **Maintaining slow query logs** - slow_log 🌿
  > You can't sit all the time monitoring all queries. It's easier to set up aggregation of slow queries.

- **Reading analytics and statistics** 🌳
  > In MySQL family this is performance_schema, in postgres this is Statistics Collector. Will help fully understand which queries work poorly, where indexes are lacking, where there are too many, and so on.

### Indexes

- **Indexes** 🌱
  > Indexes are a very important part of databases. Your queries should always work "by indexes". A query without an index or with a "bad" index, on loaded projects, can guaranteed lead to application crash.

- **Clustered index** 🌿
  > This doesn't relate to computing clusters. This is a data index, by which rows are laid out in the table.

- **PRIMARY index (aka primary index)** 🌱
  > Index uniquely identifying each row in the table. As a rule, PRIMARY index is the clustered index.

- **UNIQUE/regular indexes** 🌱
- **Composite indexes** 🌱
  > Conditions and/or sorting are rarely on one field, usually there are more. This is where composite indexes come in. Here you need to understand that in a composite index, the sequence of fields is important.

- **Understanding which fields in what sequence** to add to the index for filtering and/or sorting 🌿
- **Understanding how index trees** are built for composite indexes 🌳
- **Understanding index operation** 🌿
- **BTREE index building algorithm** ⚡
  > This understanding won't make your queries faster, but will give an idea of how certain data behaves in indexes.

### Joins and Grouping

- **Joining tables** LEFT JOIN, RIGHT JOIN, INNER JOIN, OUTER JOIN, JOIN 🌱
  > Data is always "smeared" across tables. To collect it, these operators will be needed.

- **Data grouping** via GROUP BY 🌱
  > Data grouping is not rare queries, as a rule, used for collecting statistics.

- **Filtering after grouping** 🌱
- **Functions for working with groups** MAX/MIN/AVG/etc. 🌱
- **Understanding and purpose of foreign keys** 🌿
  > Foreign keys are often used to maintain data consistency in the database.

### Transactions

- **Transactions** 🌿
  > To perform several operations atomically (as one operation), transactions are used.

- **Transaction isolation levels** 🌿
- **Deadlock** and how not to allow it 🌳
- **Triggers** on INSERT/UPDATE/DELETE 🌿
  > You shouldn't actively use triggers. Nevertheless, they can be useful in some debugging or maintenance cases.

### Tree Storage

- **Tree storage** 🌱
  > It's not easy to save a tree structure in a relational database. There are several algorithms with their pros and cons. Actually relevant for other types of databases too.

- **Parent-child algorithm** 🌱
  > Classic variant "with parent_id" in child elements. Simple and "cheap" for inserting elements into trees. But such trees are expensive "to assemble".

- **Nested sets algorithm** 🌿
  > Algorithm allows quite cheaply to collect trees with various modifications and segments. But expensive for inserting elements into trees.

### NoSQL Databases

- **Document-oriented database** (part of NoSQL databases) - MongoDB 🌿
  > Among all NoSQL, MongoDB is the most popular.

- **Data types in collections**, their purpose and differences 🌿
- **Query execution analysis** via explain(), understanding its results 🌿
- **Understanding index operation** (similar to SQL indexes with small differences) 🌿
  - Sparse index property
  - Partial index property
  - TTL index property
  - Geospatial index
  - Text index

- **Nested objects, arrays** 🌿
- **Aggregations** 🌳
- **Working with replication** 🌳
- **Working with MongoDB cluster** 🌳

### Redis

- **Redis** 🌱
  > Universal data storage tool with a focus on performance. Can be both a fast permanent storage and a reactive caching, temporary storage.

- **Basic work with keys** 🌱
- **Working with lists** 🌱
- **Working with hashes** 🌱
- **Working with sets** 🌱
- **Sorted sets** 🌿
- **Transactions**, but in another, its own, understanding
- **Working with Lua** 🌿
  > Gives the ability to run any set of commands atomically, additionally equipped with logic.

### Database Problems

- **Problems in databases** 🌱
- **Deadlock** 🌿
- **Numeric field overflow** (including autoincrement) 🌱
- **Full scan** 🌿
- **Split-brain** 🌳

---

## Stage 4. HTTP Protocol

Every WEB developer should understand the HTTP protocol. A developer who doesn't know the HTTP protocol is like a shoemaker without shoes. Therefore, even junior should know a lot about the HTTP protocol.

- **Understanding the general protocol format**: where are headers and where is the body 🌱
- **Get comfortable with the Network tab** in browser inspector 🌱
  > In the console you can observe all HTTP requests from the page and even make them yourself through the fetch function.

### HTTP Methods

- **HTTP request methods. Their purpose and limitations** 🌱
  > Each method has its purpose (just translate the method names) and, as a consequence, has its conventions and limitations.

- **Main** GET, POST, HEAD 🌱
- **Additional** PUT, DELETE, PATCH 🌿
  > Used in REST API together with main methods

- **Others** 🌳
  > These are already narrowly focused methods, rarely will you have to work with them directly. Nevertheless, they are actively used by applications.

### HTTP Response Codes

- **HTTP response codes** 🌱
- **Principle of dividing codes into groups**: 100-199, 200-299, 300-399, 400-499, 500-599 🌱
  > Codes were created and described not in chaotic order. There is a clear division of their "spheres of influence". Even if some server comes up with its own response code, by group you can better understand the reason for such a response.

- **Main (frequent)**: 200, 206, 301, 302, 304, 400, 401, 403, 404, 500, 502, 503, 504 🌱
  > These are the most frequent response codes that you are guaranteed to encounter.

- **Others** 🌿

### HTTP Headers

- **HTTP headers** 🌱
- **MIME type (document type)** and Content-Type header 🌱
- **Transfer format** application/x-www-form-urlencoded 🌱
- **Transfer format** multipart/form-data 🌿
- **System headers** Host, Content-Length, Content-Encoding, Transfer-Encoding 🌱
- **HTTP caching**, cache control headers: Cache-Control, Expires, Vary, ETag, Last-Modified

### Cookies

- **Cookies** 🌱
  > Currently this is the only accurate way to identify a user.

### CORS and CSP

- **Cross-Origin Resource Sharing (CORS)** 🌿
  > For cross-domain XHR/WebSocket requests you need to learn to work with CORS, otherwise requests won't work.

- **Content-Security-Policy (CSP)** 🌿
  > To improve security you can restrict and specify what and from where can be loaded and run on the page.

### HTTP Versions

- **Differences in HTTP protocol versions**: HTTP/1.0, HTTP/1.1 🌿
  > Despite the appearance of new versions of the HTTP protocol, HTTP/1.0 and HTTP/1.1 versions are still frequent in internal cluster networks.

- **Console commands for HTTP requests** curl, wget 🌱
  > On servers (hosts) there are no browsers whose convenient console can be used. There is shell and many utilities that can work with HTTP.

- **Differences between protocols** HTTP/1.1, HTTP/2.0 and HTTP/3.0 🌳
  > Each protocol has its own capabilities and improvements that can be used to speed up the application.

### WebSocket

- **WebSocket protocol** 🌿
  > This is an extension of HTTP/1.1 and higher for a mechanism of data exchange over one connection. Often used for chats and/or for event-driven models.

- **WebRTC** ⚡
  > If you need to organize P2P (peer-to-peer) chats or P2P streaming, then WebRTC is just for that.

### HTTP API Formats

- **HTTP API formats** 🌱
- **REST API** 🌱
- **RPC** 🌱
- **GraphQL** 🌿

### Web Servers

- **Web servers** 🌱
- **Nginx** 🌱
  > The most common Web server. The probability of encountering it during web application development is high.

- **Familiarization with basic capabilities** 🌱
- **Scalable nginx configuration** 🌿
- **Writing simple locations** in /etc/nginx/nginx.conf for file distribution 🌱
- **HTTP, FastCGI proxying** 🌱

- **Apache httpd** 🌱
  > One of the old but actively used broad-profile Web servers. Although it already yields to nginx in popularity, encountering it in projects is still just as easy.

---

## Stage 5. Security

Your application is always under threat, even if it's some home-page application. Botnets always lack computational resources. Hackers - data. And users - brains (no offense).

### Access Control

- **Types of access control** 🌿
- **Access Control List (ACL)** 🌿
- **Role-based access control (RBAC)** 🌿
- **Attribute-based access control (ABAC)** 🌿

### Authentication

- **Authentication** 🌱
- **Basic** 🌱
  > The simplest type of authorization, not requiring additional computational power (servers).

- **SSO (Single Sign On)** 🌱
  > General name for authorization approach: authorization on multiple applications through one point. OAuth and OpenID are special cases of SSO.

- **OAuth2** 🌿
  > Common type of authorization through an intermediary who guarantees that you are you and can provide some user data, with their consent. Often encounter OAuth2 when you need to connect authorization through social networks. They all have OAuth2 (but each with their own modifications).

- **OpenID** 🌿
  > One of the first popular SSO. Yields to Oauth2 in popularity, but is also used somewhere.

- **Ldap** 🌿
  > This type of authorization is most often used for authorizing own employees in internal services.

- **JSON Web Token (JWT)** 🌿
  > This is not an authorization type, but a tool for transmitting identifying data. However, such a token can have very wide application, not only in authorization.

### Types of Attacks

- **Types of attacks and vulnerabilities** 🌱
- **Phishing site** 🌱
- **Insecure redirect, Open Redirect** 🌱
- **Injections (for example SQL injections)** 🌱
- **XSS attack** 🌱
- **IDOR vulnerability** 🌿
- **CRLF attack** 🌱
- **LFI/RFI attack** 🌱
- **DoS/DDoS** 🌿
- **HTTP-flood** 🌿
- **SYN flood** (TCP knowledge required) 🌳
- **UDP flood** (UDP amplification) 🌳
- **Slow request** 🌿
- **Bombs** 🌿
- **Logic Bomb** 🌿
- **Zip Bomb** 🌱
- **Man In The Middle attack (MITM)** 🌿
- **Brute force** (for example password brute force) 🌱
- **Spoofing** 🌿

---

## Stage 6. Programming Language

There are many programming languages. However, they have a lot in common, some more, some less. This stage will only touch on frequently encountered items in most popular programming languages. The stage will not be clearly divided into gradations, as much depends on the language itself, its capabilities and its extensions.

**Principle of working with this section**: search %your_programming_language% %item_from_stage%. Note that some items may not exist in your language.

- **What is interpreter, compiler, JIT, op-code, byte-code. What of this does your language use?** 🌱
- **Your programming language** 🌱
- **Primitive data types**
  > Basic scalar types - integers, strings, boolean values, floating point numbers, null/nil and so on.

- **Functions, macros**
  - Definition and their call
  > Ability to define a simple function and call it. There are languages where functions without objects cannot exist.

  - Main function or program entry point
  > In a language, a program may only start through a startup function, for example main(). But some languages allow launching a file with code.

- **Set, array, hash table (associative array), tuple**
  > Represents various combinations of primitive types. For example, a numeric data array can be made in almost any language.

- **Objects/classes/structures, prototypes/interfaces/mixins**
  > All modern languages have objects and can operate them.

- **Operator overloading**
  > Allows objects themselves to define how to perform mathematical, logical and other actions (operations) on them.

- **Method overloading**
  > Allows defining multiple methods with one name but different signature. As a rule, this is achieved through a different set of parameters (number or types of accepted values) for each method.

- **Generics (aka templates aka generalizations)**
  > Specific capability of some strongly typed programming languages. Allows defining a single signature for processing different types.

### Object-Oriented Programming (OOP)

- **Object-Oriented Programming (OOP)**
- **References, weak references**
- **Variable scope**
  > It's important to understand when your variables are accessible in code and where they are not yet/already not. This is especially important to understand when working with references.

### Garbage Collector

- **Garbage Collector (GC)**
  > Many high-level (and not only) languages have GC. GC is responsible for freeing memory from garbage (forgotten data, data that code no longer needs) during code execution. This is a very important part of your language, as while GC is working - your code is not working. And if GC works often and/or a lot, your application will start to lag and "hang".

- When and how GC is launched
- Study GC settings
- Enabling/disabling GC, forced GC launch
- Profiling leaks or memory consumption

### Type System

- **Type conversion**
- **Weak/strong typing in code. What it affects and how to live with it**
  > Strong typing requires explicit indication in code of the data type that will be used in a variable, argument, etc. And dynamic, on the contrary, allows not to specify the type. Calculation of value type will occur dynamically, at the moment of program/program code execution (runtime). Some languages can support both strong and weak typing simultaneously.

- **Bit operations**: not, and, or, xor, shift left, shift right 🌱
  > Often instead of or and and symbols |/|| and &/&& are used. You can encounter bit operations more often than it seems, many functions/methods accept options in the form of bit flags like READ|WRITE|CREATE. You need to be able to combine bit flags, delete, determine which flags are set.

### Error Handling

- **Error handling. Exceptions, panics, error and other error manifestations**
  > You always need to handle errors. It's important to know which errors you can catch (handle) and which you can't. There are errors that can be caught and handled, and there are errors that will crash the application. Note that some languages can catch any error, but will still have to restart the application.

- Understanding error stack trace

### Types and Concepts

- **Value vs Reference**
  > Copying by value or copying by reference and where. It's important to understand when you're passing a copy of data and when you're passing a link to data. It's easy to shoot yourself in the foot here, changing values not where you intended.

- **Mutable and immutable**
  > Some types or values can be changed and some cannot. Knowing where your data can change and where it can't will help prevent some bugs.

- **Static and dynamic types**
  > Static - types defined at compilation (if language has compilation). Dynamic - types determined at execution.

- **Lazy and eager evaluation**
  > Lazy - calculated when needed. Eager - calculated immediately. For example, generators in many languages are lazy.

### Concurrency

- **Coroutines, goroutines, green threads**
  > Different languages call lightweight threads differently. It's important to understand how they work in your language.

- **Async/await, promises, futures**
  > Asynchronous programming patterns. Important to understand how they work in your language.

- **Locks, mutexes, semaphores**
  > Synchronization primitives. Important for working with shared state.

- **Race conditions, deadlocks**
  > Common concurrency problems. Important to know how to avoid them.

### Standard Library

- **Working with strings**
  > Most of the code works with strings. It's important to know the standard string processing capabilities.

- **Working with dates and time**
  > Dates and time are everywhere. It's important to know how to work with them.

- **Working with files**
  > Reading, writing, deleting files. Working with paths.

- **Working with network**
  > HTTP clients, TCP/UDP sockets.

### Package Management

- **Package manager of your language**
  > npm, pip, composer, cargo, maven, etc.

- **Dependency management**
  > How to add, update, delete dependencies.

- **Versioning**
  > Semantic versioning, version constraints.

### Testing

- **Unit testing**
  > Testing individual functions/methods.

- **Test framework of your language**
  > pytest, jest, junit, etc.

- **Mocking**
  > Mocking dependencies for testing.

- **Test coverage**
  > Measuring how much code is covered by tests.

### Popular Frameworks

- **Web framework**
  > Django, Express, Spring, etc.

- **ORM**
  > Working with databases through objects.

- **Logging**
  > Logging libraries and best practices.

### Code Quality

- **Linter**
  > Static code analysis tool.

- **Formatter**
  > Code formatting tool.

- **Type checker**
  > For dynamically typed languages.

### Debugging

- **Debugger**
  > How to use debugger in your language.

- **Profiler**
  > Performance profiling tools.

---

## Stage 7. Email

*(Continue from the original document...)*

**Email protocols** 🌿
- SMTP (Simple Mail Transfer Protocol)
  > Protocol for sending emails
- IMAP (Internet Message Access Protocol)
  > Protocol for receiving emails
- POP3
  > Another protocol for receiving emails

**Email structure** 🌿
- Headers
- Body
- Attachments
- MIME types

**Sending email** 🌿
- Email libraries in your language
- Email templates
- Transactional emails

**Email services** 🌿
- SendGrid
- Mailgun
- Amazon SES

---

## Stage 8. Full-Text Search

**Search engines** 🌿
- Elasticsearch
  > Most popular search engine
- Apache Solr
- Meilisearch

**Search concepts** 🌿
- Indexing
- Tokenization
- Stemming
- Analyzers
- Relevance scoring

**Search queries** 🌿
- Basic queries
- Boolean queries
- Phrase queries
- Fuzzy search
- Wildcards

---

## Stage 9. Logs and Metrics

**Logging** 🌱
- Log levels
  > DEBUG, INFO, WARN, ERROR, FATAL
- Structured logging
  > JSON logs
- Log rotation
- Centralized logging

**Log management** 🌿
- ELK Stack
  > Elasticsearch, Logstash, Kibana
- Grafana Loki
  > Log database based on Prometheus-like storage

**Metrics** 🌿
- Prometheus
  > Popular metrics collection system
- Metric types
  > count, gauge, histogram, summary
- Metric delivery
  > push and pull
- Queries
  > Syntax, labels, vectors, intervals, operators
- Key functions
  > rate, irate

**Visualization** 🌳
- Grafana
  > Excellent UI for displaying metrics
  - Creating dashboards
  - Creating graphs
  - Setting up alerts

---

## Stage 10. Design and Development

Patterns, concepts and approaches to designing various web applications.

### Development Principles

- **Development principles** 🌱
- **GRASP** (General Responsibility Assignment Software Patterns) 🌿
- **SOLID** (Single Responsibility, Open–Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) 🌿
- **KISS** (Keep It Simple, Stupid) 🌱
- **YAGNI** (You Aren't Gonna Need It) 🌱
- **DRY** (Don't Repeat Yourself) 🌱
- **IoC** (Inversion Of Control), and as a consequence - DI (Dependency Injection) 🌿
- **DDD** (Domain-Driven Design) 🌿

### Architectural Patterns

- **Architectural patterns** 🌱
  > One project can have one or several architectural patterns, or even half. Architectural patterns are an approach to solving the task assigned to the project.

- **Hexagonal Architecture** 🌳
- **Event-Driven Architecture** (aka Broker pattern) 🌳
- **Onion Architecture** (aka Layered pattern) 🌳
- **CQRS** (The Command and Query Responsibility Segregation) 🌳
- **SoA** (Service-Oriented Architecture) 🌳
- **Event Sourcing** 🌳

### Application Patterns

- **MVC pattern** 🌱
  > The oldest and quite widespread application design pattern, separating UI from application logic.

- **ADR pattern** (Action-Domain-Responder)
  > MVC refinement for web tasks

- **MVP pattern** 🌱
  > MVP is an iteration of MVC development due to application and UI complications. Often used in front-end - in browser.

- **MVVM pattern**
  > Actually this pattern is suitable for desktop or mobile applications. Practically not used in web applications.

### Design Patterns

**Design patterns**
> Patterns simplify development, as they are, essentially, community experience in solving various problems. Main thing is don't forget about KISS and YAGNI, so as not to fall into abstraction hell and complexity abyss.

- Creational design patterns
- Structural design patterns
- Behavioral design patterns

### Development Methodologies

**Development methodologies**
> This is not about scrum, agile, waterfall, planning, design and so on. This is about code writing methodologies.

- **TDD** (Test Driven Development)
  > Development through testing, the most famous development method, requiring developer first - writing test for code, then the code itself.

- **BDD** (Behavior Driven Development)
  > Extended version of TDD, in that first not a test is written, but a description of what needs to be done, in domain language, for example Gherkin.

### Application Types

**Application types**
> There is a division of applications by UI generation method.

- **MPA** (Multi-Page Application)
  > Classic application type, with multiple pages generated on back-end for UI creation.

- **SPA** (Single Page Application)
  > General name for application type when application lives in browser and goes to server for data. Can be both SSG, SSR, CSR or any combination thereof.

- **SSG** (Static Site Generation)
  > All application pages are pre-generated into static files. Dynamics completely on JS. Can be both MPA and SPA.

- **SSR** (Server Side Rendering)
  > Approach to application page generation. Each request is processed on server, where UI is generated, then server returns response to client on front-end.

- **CSR** (Client Side Rendering)
  > Approach to application page generation. All UI is generated in browser using JS. JS makes requests to servers for data, for building or changing UI. SPA is a special case of CSR.

- **PWA** (Progressive Web Application)
  > Literally your site as a mobile application.

### Testing

- **Testing** 🌱
- **Unit testing** 🌱
  > Testing individual (including separate from each other) product parts, usually individual functions/methods. Unit tests also carry another goal - checking your implementation architecture. As a rule, if you can't write a unit test for a function/method without involving other application components, then perhaps you should reconsider the architecture. Good Unit testing leads to good inversion of control (IoC, see above).

- **Integration tests** 🌿
  > Complex type of tests. Checking functionality of application, module, components with another application, module, component.

- **End-to-End (aka E2E aka Through testing)** 🌿
  > Example of E2E test - testing finished API application. Not application components are tested, but ready functionality.

- **Smoke test** 🌿
  > Smoke tests allow testing the very possibility of your application working. Sometimes used for testing infrastructure for the possibility of your application working in it.

### Application and Design Problems

- **Application and design problems** 🌱
- **Technical debt** 🌱
  > Technical debt will start accumulating in project from the first lines of code. It should always be taken into account in development and plan its elimination.

- **Over engineering** 🌱
  > When implementation is much larger or more complex than required. Will require a heap of resources for project support.

- **Premature Optimization** 🌱
  > Resorting to optimization where it's not required at the moment. Will take away a heap of resources at the project development stage.

### Other Concepts

- **Refactoring techniques**
  > To get rid of technical debt will have to refactor often and a lot.

- **Anti-patterns**
  > It's useful to know how to do things, but no less useful to know how NOT to do things.

- **Semver**
  > The most common principle of application version naming. In some languages and package managers is mandatory to comply with.

### Distributed Systems

**Distributed systems**
> When application hits server ceiling then you have only one way out - force application to work on multiple servers. This greatly complicates application and many resources go to preserving data integrity and consistency.

- **CAP and PACELC theorems**
  > In distributed systems will have to sacrifice something. PACELC is extended CAP theorem. These theorems just describe what parameters system will have to sacrifice.

- **Microservices architecture**

---
## Stage 11. Docker Virtualization

To begin, you need to set up a virtual machine for experiments and research. If something goes wrong, the virtual machine can always be recreated.

There are many virtualization systems, but Docker stands out among them. Docker is a popular tool for desktop virtualization. On production servers, it is used to a lesser extent, as Kubernetes (aka k8s) is more popular there. Docker is not the only virtualization system, the closest analogues are Lima, Podman (something between Docker and k8s).

- Install docker 🌱
- Run a container with Linux Ubuntu, the latest LTS version. Launch bash (console) of the container 🌱
- Install a convenient application for managing images and containers Kitematic, Portainer, etc. Or get comfortable with Docker console commands. Docker-desktop already has its own dashboard for managing images and containers 🌱
- **docker compose** for spinning up a cluster of containers 🌿
  > For a working application, as a rule, several different services are required (database, cache, http-server, etc.) and packing all this into one Docker container will be problematic, simply due to the specifics of virtualization itself. This is where compose will help to launch a bunch of containers and connect them together.

---

## Stage 12. Linux

Study Linux installed in the container. Linux, de facto, is the server OS for most web applications. This section will discuss Linux, although (almost) everything is also relevant for other POSIX-compatible systems. For example, for the BSD family, including MacOS. However, there may be differences. As a starting Linux distribution, Ubuntu is usually chosen, but you can take the most compact - Alpine, which is often used in virtualization.

- **Installing packages and updating the system** via apt/apt-get in Ubuntu/Debian and apk in Alpine 🌱
  > During research and various trials, you will have to install, update, and reinstall many Linux packages many times. It's better to immediately learn how these commands work. Basic operations needed: find, install, update, delete.

- **Basic bash skills** (improved sh aka shell) 🌱
  > In Linux-like systems, bash permeates everything. You are guaranteed to encounter it and there will be cases when you need to write bash/shell scripts.

- **Basic bash syntax** 🌿
  > In fact, this is the only scripting language that is guaranteed to be installed in the system.
  - Control operators if, for and while
  - Logical operators ;, &&, ||
  - Executing expressions \`cmd\` and $(cmd)

- **Basic commands for working with the file system** cd, ls, find, cat, cp, mv, mkdir, rmdir, rm 🌱
- **Calling manuals** via man command 🌱
  > Through this command you can get help on any command, operation, files and even source code.

- **Command pipelines** via operator | (cmd1 | cmd2 | cmd3) 🌱
  > Linux has a large number of commands for data processing and for solving various tasks that you may need to combine through pipelines.

- **Data processing commands** cat, tail, head, grep, awk, sed 🌿
  > This set will be needed for scanning and analyzing logs or large volumes of text data.

- **Archive commands** zcat, gzip, gunzip, tar, zgrep 🌿
  > As a rule, nobody stores logs or large volumes of text data "as is", usually it's a gz or tar.gz (tgz) archive.

- **Console editors** vim, nano. Open file, make changes, save 🌱
  > Editing a file from the console is not that rare. By the way, to exit vim: esc, type :q!, enter.

- **Console viewers** less, zless. Open, find word, close 🌱
  > Editors are redundant to just view file contents. Viewers also handle non-"standard" files for editors.

- **Console file manager** mc 🌱
  > Console file managers, like Midnight Commander, provide a UI that makes working with typical file operations more convenient and visual.

- **Background tasks**, operator &, commands jobs, fg, bg 🌿
  > The operator will allow you to run multiple commands in one shell session.

- **Signal ignoring command** nohup 🌿
  > The command will allow, when the shell session ends, to keep alive launched background tasks until their logical completion.

- **Streams, stream redirection**, operators >, >>, < 🌱
  > Where to write output and where errors will help these operations indicate.

- **Master the console completely** ⚡

### Processes

- **Process concept** 🌱
  > As in all other OSs, running applications in Linux are represented by processes.

- **Process analysis commands** top, htop, ps (ps aux) 🌱
  > This is like a "task manager" in the Linux world, allowing you to monitor system processes.

- **Parent process, child process** 🌿
  > Processes don't appear out of nowhere, something launches them. Understanding the process hierarchy will facilitate working with them and make understanding multiprocess applications easier.

- **Master-worker processes, daemon** 🌿
  > This is one of the common types of computation parallelization in applications. Many programs use exactly this parallelization approach.

- **Zombie processes**. Where they come from and how to deal with them 🌳
  > This is a type of problem with parallelizing computations through child processes. Occurs when the master process has problems or bugs.

- **Sending signals to processes** 🌱
  > This is the main lever of influence on processes by third-party applications (system or yours).

- **Study commands** kill, pkill, killall 🌱
- **Purpose of signals** SIGKILL, SIGTERM, SIGINT, SIGHUP, SIGSEGV 🌿
- **System call (syscall)** 🌳
  > System call (Linux kernel API call) is not a free operation and it's better to keep them under control in high-load applications.

- **Command for analyzing system calls** of a process via strace 🌳
  > The simplest and most accessible way to see what system calls a process makes in real time.

### File Descriptors

- **Study the descriptor concept** 🌿
  > Any data stream (incoming and/or outgoing) is represented as descriptors. You will (most likely) read or write something through a descriptor.

- **Standard descriptors** STDIN, STDOUT, STDERR and their numbering 🌿
  > Every stream in a process is numbered and there are "reserved" numbers for certain streams.

- **Streams, sockets and unix-sockets** 🌿
  > These are all varieties of descriptors that you will have to work with. Descriptor rules apply to all of them, well, since they are descriptors.

- **Descriptor limitations** 🌳
  > Not an uncommon problem for applications when it hits the limit of open descriptors.

- **Command for analyzing open descriptors** of a process via lsof 🌳
  > For debugging an application, you always need to know what the application is communicating with (works great paired with strace, matching descriptor numbers).

### Users

- **Users** 🌱
- **Root user** 🌱
  > Essentially this is the system admin. Avoid using root (even in containers) as access to root gives access to the entire system, which all malware dreams of.

- **Super user, commands** su and sudo 🌱
  > Nobody will give you root in production, but you may well have a "privileged" user who can use sudo.

### File System

- **File system** 🌱
- **Command** stat 🌱
- **File system rights and access** 🌱
  > Excessive access leads to security holes, lack of access leads to bugs in the application. Consciously set where x (especially for directories), where r, and where w.

- **Understanding access descriptions** like --xr-xrwx and 0137 (octal) for files and directories 🌱
  > Usually this is how you will see access levels in consoles.

- **Executable files, shebang** 🌱
- **Changing access rights** via chmod, chown commands 🌿
- **Working with disks** 🌳
  > Need to know where, how and where various disks or media are mounted. It happens that an application can work with several disks at once, some may be network disks.

### Links

- **Links on the file system** 🌱
- **Symlink (aka symbolic link)** 🌱
  > The most common type of link. Widely used in Linux and in package managers of different languages. You will use this too.

- **Hardlink (aka hard link)** 🌿
  > Rare use case for links. Needed if you need to "deduplicate" a large volume of files. Essentially allows you to create several names for one file.

### Services

- **Starting and stopping systemd services** 🌿
  > Linux is essentially just a bunch of running applications as services.

### SSH

- **SSH** 🌱
  > The most accessible way to launch a shell on a remote machine is to use SSH. Used everywhere.

- **Generating your own ssh-rsa key** via ssh-keygen 🌱
  > Without it you won't get on hosts via SSH.

- **Using public ssh-rsa key** to log into a remote machine (use a second container with Linux) 🌱

### Content Transfer

- **Content transfer** 🌱
  > There is a need to transfer logs, database dumps and other files between machines or to yourself.

- **scp** 🌱
  > The simplest tool for transferring files between hosts via ssh.

- **rsync** 🌿
  > Perhaps the most powerful tool for transferring files between hosts with lots of settings, rules and protocols.

- **rclone** 🌿
  > "rsync" for cloud storage. Universal tool for working with content that is stored in clouds or somewhere on the network.

### Task Schedulers

- **Crontab command** and crond launch
  > The most common and simple task scheduler, with very flexible schedule settings

- **Command** at 🌿
  > When you want to run a task once, at a certain time. In crontab this will require separately creating a schedule, which greatly complicates automation and clutters the entire schedule.

### Memory

- **RAM** 🌿
- **Command** free, meta information /proc/meminfo 🌿
  > Always estimate how much memory the application or scripts will need so as not to be killed by the system.

- **Out Of Memory (OOM) error** and cause of occurrence. OOM-killer 🌳
  > This is exactly what happens when you exceed all acceptable limits of memory consumption in the system.

### System Logs

- **System logs. Why and how to view** 🌿
  > When problems occur, logs are the only thing that can lead to the essence of the problem. In addition to application logs, it's worth looking at system logs, sometimes its problem can lead to problems in applications. Some logs worth highlighting:

- **dmesg** (driver messages) - important messages from Linux components, including from OOM-killer 🌿
- **syslog** - system log 🌿
  > There may be messages from the Linux kernel, various services, network interfaces and much more.

### Problems in Linux

- **Problems in Linux and consequences** 🌱
  > There are many, but let's highlight only a few.

- **Kernel panic** 🌱
  > BSoD analogue for Linux. The most unpleasant system error, clearly hinting that the system is not stable.

- **Segmentation fault (aka segfault)** 🌿
  > Not as rare an application error as one would like. The application tried to work with memory it doesn't have access to.

- **Core dump (aka coredump)** 🌳
  > Result of segmentation fault processing by the system. Coredump may be needed by the developer of the crashed application to analyze the program's state at the moment of crash.

---


## Contributing

If you want to change something (item, link, typo) - create an issue or make a PR. If you want to discuss the document - create a discussion in discussions.

---

**Good luck on your backend development journey! 🚀**
