# 🚀 Backend Developer Roadmap

## 📖 About This Document

This document contains a comprehensive roadmap of skills frequently required for backend developers of web applications. The roadmap is divided into **stages** (topics), with each stage broken down into individual items.

### What You Should Know

For each item in this document, a backend developer should:

- ✅ Know what it is and what problem it solves
- ✅ Understand when and why to apply it
- ✅ Know how to work with it or where to find references
- ✅ Keep it in mind during development and design

Understanding the underlying principles of each item is a bonus for comprehensive knowledge, though it may be time-consuming. Study these at your own pace and as needed.

---

## 📚 How to Use This Document

Stages and items are arranged in the **recommended learning order**. Simply follow from top to bottom.

Each item is easily searchable and typically has a Wikipedia page. Links are provided when alternative documentation exists that is clearer or more detailed. Some links may require VPN access.

> 💡 **Note:** Quoted text provides explanations about why you should know something and where you might encounter it.

---

## 🎯 Skill Levels

Each item is categorized by skill level to help you prioritize your learning:

| Level | Icon | Description |
|-------|------|-------------|
| **Junior** | 🌱 | Fundamental skills - start here |
| **Middle** | 🌿 | Intermediate skills - build on fundamentals |
| **Middle+** | 🌳 | Advanced skills - master level |
| **Guru** | ⚡ | Deep dive topics - for those who want to go further |

> 📌 The maximum skill level in this document is **middle+** (🌳), as the focus is on hard skills. Senior level typically includes middle+ skills combined with soft skills.

---

## 📝 Document Status

This document is continuously being updated and refined. Ideally, each item should have a skill level, explanation, and link to quality documentation.

**Want to contribute?** 
- 🐛 Found a bug or typo? Create an issue or submit a PR
- 💬 Want to discuss? Use the discussions section

---

## 📑 Table of Contents

1. [🐳 Docker Virtualization](#stage-1-docker-virtualization)
2. [🐧 Linux](#stage-2-linux)
3. [💡 General Knowledge](#stage-3-general-knowledge)
4. [🌐 Networking](#stage-4-networking)
5. [💾 Databases](#stage-5-databases)
6. [📡 HTTP Protocol](#stage-6-http-protocol)
7. [🔒 Security](#stage-7-security)
8. [⚙️ Your Programming Language](#stage-8-your-programming-language)
9. [📧 Email](#stage-9-email)
10. [🔍 Full-Text Search](#stage-10-full-text-search)
11. [📊 Logs and Metrics](#stage-11-logs-and-metrics)
12. [🏗️ Design and Development](#stage-12-design-and-development)

---

## Stage 1. 🐳 Docker Virtualization

First, set up a virtual machine for experimentation and research. If something goes wrong, you can always recreate the virtual machine.

There are many virtualization systems, but Docker stands out. Docker is a popular tool for desktop virtualization. On production servers, it's less common, as **Kubernetes (k8s)** is more popular there. Docker isn't the only virtualization system—close alternatives include **Lima** and **Podman** (something between Docker and k8s).

### Learning Path

- 🌱 **Install Docker**
- 🌱 **Run a container with Linux Ubuntu** (latest LTS version) and launch bash console
- 🌱 **Install a convenient application** for managing images and containers (Kitematic, Portainer, etc.) or get comfortable with Docker console commands. Docker Desktop already has a dashboard for managing images and containers
- 🌿 **docker-compose** for spinning up container clusters
  > 💡 For production applications, multiple services are typically required (database, cache, HTTP server, etc.), and packing everything into one Docker container is problematic due to virtualization specifics. Compose helps launch multiple containers and connect them together.

---

## Stage 2. 🐧 Linux

Study the Linux installed in your container. Linux is de facto the server OS for most web applications. This section discusses Linux, though (almost) everything is also relevant for other POSIX-compatible systems (e.g., BSD family, including macOS). However, there may be differences. Ubuntu is typically chosen as a starting Linux distribution, but you can use the most compact one—**Alpine**—which is often used in virtualization.

### 📦 Package Management

- 🌱 **Installing packages and updating the system** via `apt`/`apt-get` in Ubuntu/Debian and `apk` in Alpine
  > 💡 During research and experimentation, you'll need to install, update, and reinstall many Linux packages. Learn these commands early. Basic operations needed: find, install, update, remove.

### 💻 Bash Basics

- 🌱 **Basic bash skills** (improved sh, aka shell)
  > 💡 In Linux-like systems, bash permeates everything. You're guaranteed to encounter it and will need to write bash/shell scripts.

- 🌿 **Basic bash syntax**
  > 💡 This is essentially the only scripting language guaranteed to be installed on the system.
  - Control operators: `if`, `for`, `while`
  - Logical operators: `;`, `&&`, `||`
  - Execution expressions: `` `cmd` `` and `$(cmd)`

### 📁 File System Commands

- 🌱 **Basic commands for working with the file system**: `cd`, `ls`, `find`, `cat`, `cp`, `mv`, `mkdir`, `rmdir`, `rm`

- 🌱 **Calling manuals** via `man` command
  > 💡 This command provides help for any command, operation, files, and even source code.

- 🌱 **Command pipelines** via `|` operator (`cmd1 | cmd2 | cmd3`)
  > 💡 Linux has many data processing commands that you can combine through pipelines to solve various tasks.

### 🔧 Data Processing

- 🌿 **Data processing commands**: `cat`, `tail`, `head`, `grep`, `awk`, `sed`
  > 💡 This set is needed for scanning and analyzing logs or large volumes of text data.

- 🌿 **Archive commands**: `zcat`, `gzip`, `gunzip`, `tar`, `zgrep`
  > 💡 Typically, logs or large text volumes aren't stored as-is but in gz or tar.gz (tgz) archives.

### ✏️ Editors and Viewers

- 🌱 **Console editors**: `vim`, `nano` (open file, make changes, save)
  > 💡 Editing files from the console isn't uncommon. BTW, to exit vim: `esc`, type `:q!`, `enter`.

- 🌱 **Console viewers**: `less`, `zless` (open, find word, close)
  > 💡 Editors are overkill just to view file contents. Viewers also handle non-standard files.

- 🌱 **Console file manager**: `mc`
  > 💡 Console file managers like Midnight Commander provide a UI that makes typical file operations more convenient and visual.

### ⚙️ Background Tasks

- 🌿 **Background tasks**: `&` operator, `jobs`, `fg`, `bg` commands
  > 💡 The operator allows running multiple commands in one shell session.

- 🌿 **Signal ignoring command**: `nohup`
  > 💡 Allows background tasks to continue running after shell session termination until logical completion.

- 🌱 **Streams and stream redirection**: `>`, `>>`, `<` operators
  > 💡 These operations help direct output and errors to the right places.

- ⚡ **Master the console completely** - *guru level*

### 🔄 Processes

- 🌱 **Process concept**
  > 💡 Like all other OSs, running applications in Linux are represented as processes.

- 🌱 **Process analysis commands**: `top`, `htop`, `ps` (`ps aux`)
  > 💡 Linux's "task manager" for monitoring system processes.

- 🌿 **Parent process, child process**
  > 💡 Processes don't appear from nowhere—something launches them. Understanding process hierarchy makes working with them easier and simplifies understanding multiprocess applications.

- 🌿 **Master-worker processes, daemon**
  > 💡 One of the common types of computation parallelization in applications. Many programs use exactly this parallelization approach.

- 🌳 **Zombie processes**: where they come from and how to deal with them
  > 💡 A problem type in parallelization through child processes. Occurs when the master process has issues or bugs.

- 🌱 **Sending signals to processes**
  > 💡 The main lever for external applications (system or yours) to affect processes.

- 🌱 **Commands**: `kill`, `pkill`, `killall`

- 🌿 **Signal purposes**: `SIGKILL`, `SIGTERM`, `SIGINT`, `SIGHUP`, `SIGSEGV`

### 🔧 System Calls

- 🌳 **System call (syscall)**
  > 💡 System calls (Linux kernel API calls) aren't free operations and should be controlled in high-load applications.

- 🌳 **Analyzing system calls**: `strace`
  > 💡 The simplest and most accessible way to see what system calls a process makes in real-time.

### 📋 File Descriptors

- 🌿 **File descriptor concept**
  > 💡 Any data stream (incoming and/or outgoing) is represented as descriptors. Reading or writing will (most likely) be through descriptors.

- 🌿 **Standard descriptors**: `STDIN`, `STDOUT`, `STDERR` and their numbering
  > 💡 Every stream in a process is numbered, and there are "reserved" numbers for specific streams.

- 🌿 **Streams, sockets, and unix-sockets**
  > 💡 All varieties of descriptors you'll work with. Descriptor rules apply to all of them.

- 🌳 **Descriptor limits**
  > 💡 A common application problem is hitting the open descriptor limit.

- 🌳 **Analyzing open descriptors**: `lsof`
  > 💡 For debugging, always know what the application is communicating with (works great with strace, matching descriptor numbers).

### 👥 Users and Permissions

- 🌱 **Users**
- 🌱 **Root user**
- 🌱 **File permissions**: read, write, execute for user, group, others
- 🌱 **Changing permissions**: `chmod`, `chown` commands
- 🌱 **`sudo` command** for elevated privileges

### 🌍 Environment Variables

- 🌱 **Environment variables**
  > 💡 A simple and reliable way to configure applications.

- 🌱 **Viewing and setting variables**: `export`, `env`, `printenv`
- 🌱 **Standard variables**: `PATH`, `HOME`, `USER`

### 🌐 Networking

- 🌱 **Basic networking commands**: `ping`, `curl`, `wget`, `netstat`, `ss`
- 🌿 **Network configuration**: `ifconfig`, `ip`
- 🌿 **Checking connections**: `telnet`, `nc` (netcat)

### 📊 System Information

- 🌱 **System information commands**: `uname`, `hostname`, `uptime`, `df`, `du`
- 🌿 **Resource monitoring**: `free`, `vmstat`, `iostat`

### 📝 Logs

- 🌱 **System logs location**: `/var/log/`
- 🌿 **Log viewing**: `journalctl` (systemd)

---

## Stage 3. 💡 General Knowledge

### Data Formats

- **JSON** - *junior*
- **XML** - *junior*
- **YAML** - *junior*
- **CSV** - *junior*
- **Protocol Buffers (protobuf)** - *middle*
- **MessagePack** - *middle+*

### Encoding

- **Character encoding concept** - *junior*
- **ASCII** - *junior*
- **Unicode** - *junior*
- **UTF-8, UTF-16** - *junior*
- **Base64** - *junior*
- **URL encoding** - *junior*

### Regular Expressions (RegEx)

- **Basic regex syntax** - *junior*
- **Metacharacters**: `.`, `*`, `+`, `?`, `^`, `$`, `[]`, `()`, `|` - *middle*
- **Flags**: `i`, `g`, `m` - *middle*
- **Lookahead and lookbehind** - *middle+*

### Date and Time

- **Timestamps** - *junior*
- **Unix time** - *junior*
- **ISO 8601 format** - *junior*
- **Timezones** - *junior*
- **UTC** - *junior*

### Version Control

- **Git basics** - *junior*
  - Init, clone, add, commit, push, pull
  - Branches, merge, rebase
  - Status, log, diff
- **Git workflows**: feature branch, gitflow - *middle*
- **Pull requests / merge requests** - *junior*
- **Resolving conflicts** - *middle*

### Algorithms and Data Structures

- **Big O notation** - *middle*
- **Arrays, Lists** - *junior*
- **Hash tables, Sets** - *junior*
- **Stacks, Queues** - *middle*
- **Trees, Graphs** - *middle*
- **Sorting algorithms**: quicksort, mergesort, heapsort - *middle*
- **Search algorithms**: binary search, DFS, BFS - *middle*

---

## Stage 4. Networking

### OSI Model

- **7 layers of OSI model** - *middle*
- **Layer responsibilities** - *middle*

### TCP/IP

- **IP address** - *junior*
- **IPv4 vs IPv6** - *middle*
- **Subnets and CIDR** - *middle*
- **TCP protocol** - *middle*
  - Three-way handshake
  - Reliable delivery
  - Flow control
- **UDP protocol** - *middle*
  - Unreliable, connectionless
  - Use cases

### DNS

- **DNS purpose** - *junior*
- **DNS records**: A, AAAA, CNAME, MX, TXT, NS - *middle*
- **DNS resolution process** - *middle*
- **DNS caching** - *middle*
- **DNS tools**: `nslookup`, `dig` - *middle*

### HTTP/HTTPS

See dedicated [Stage 6: HTTP Protocol](#stage-6-http-protocol)

### Network Tools

- **`ping`** - testing connectivity - *junior*
- **`traceroute`** - route analysis - *middle*
- **`nmap`** - port scanning - *middle*
- **`tcpdump`, `wireshark`** - packet capture - *middle+*

### Ports

- **Port concept** - *junior*
- **Well-known ports**: 80, 443, 22, 21, 25, 3306, 5432 - *junior*
- **Port ranges**: well-known (0-1023), registered (1024-49151), dynamic (49152-65535) - *middle*

### Load Balancing

- **Load balancer concept** - *middle*
- **Types**: Layer 4 vs Layer 7 - *middle+*
- **Algorithms**: round-robin, least connections, IP hash - *middle*
- **Health checks** - *middle*

### Reverse Proxy

- **Reverse proxy concept** - *middle*
- **Use cases**: caching, SSL termination, load balancing - *middle*
- **Popular tools**: Nginx, HAProxy, Traefik - *middle*

### CDN

- **Content Delivery Network concept** - *middle*
- **Edge servers** - *middle*
- **CDN benefits**: latency reduction, DDoS protection - *middle*

---

## Stage 5. Databases

### SQL Databases

- **SQL basics** - *junior*
  - SELECT, INSERT, UPDATE, DELETE
  - WHERE, ORDER BY, GROUP BY, HAVING
  - JOINs: INNER, LEFT, RIGHT, FULL
  - Aggregate functions: COUNT, SUM, AVG, MIN, MAX

- **Database design** - *middle*
  - Normalization (1NF, 2NF, 3NF)
  - Primary keys, foreign keys
  - Indexes
  - Constraints: UNIQUE, NOT NULL, CHECK

- **Transactions** - *middle*
  - ACID properties
  - Isolation levels
  - COMMIT, ROLLBACK

- **Performance** - *middle+*
  - Query optimization
  - EXPLAIN plans
  - Index strategies
  - Query caching

- **Popular SQL databases** - *middle*
  - PostgreSQL
  - MySQL / MariaDB
  - SQLite

### NoSQL Databases

- **Document databases** - *middle*
  - MongoDB
  - CouchDB
  - Document structure, collections

- **Key-value stores** - *middle*
  - Redis
  - Memcached
  - Use cases: caching, sessions

- **Column-family stores** - *middle+*
  - Cassandra
  - HBase
  - Wide-column storage

- **Graph databases** - *middle+*
  - Neo4j
  - OrientDB
  - Graph queries, relationships

### Database Concepts

- **Connection pooling** - *middle*
- **Replication** - *middle+*
  - Master-slave
  - Master-master
  - Replication lag

- **Sharding** - *middle+*
  - Horizontal vs vertical partitioning
  - Sharding strategies

- **Backup and recovery** - *middle*
- **Migration tools** - *middle*

---

## Stage 6. HTTP Protocol

### HTTP Basics

- **HTTP versions**: HTTP/1.1, HTTP/2, HTTP/3 - *middle*
- **Request structure**: method, headers, body - *junior*
- **Response structure**: status code, headers, body - *junior*

### HTTP Methods

- **GET** - retrieve resource - *junior*
- **POST** - create resource - *junior*
- **PUT** - update/replace resource - *junior*
- **PATCH** - partial update - *middle*
- **DELETE** - remove resource - *junior*
- **HEAD, OPTIONS** - *middle*

### Status Codes

- **1xx**: Informational - *middle*
- **2xx**: Success (200, 201, 204) - *junior*
- **3xx**: Redirection (301, 302, 304) - *middle*
- **4xx**: Client errors (400, 401, 403, 404, 429) - *junior*
- **5xx**: Server errors (500, 502, 503, 504) - *junior*

### Headers

- **Request headers**: User-Agent, Accept, Authorization, Content-Type - *junior*
- **Response headers**: Content-Type, Content-Length, Set-Cookie, Cache-Control - *junior*
- **CORS headers** - *middle*
- **Custom headers** - *middle*

### Cookies

- **Cookie concept** - *junior*
- **Cookie attributes**: Domain, Path, Expires, Secure, HttpOnly, SameSite - *middle*
- **Session cookies vs persistent cookies** - *junior*

### Sessions

- **Session management** - *junior*
- **Server-side sessions** - *middle*
- **Token-based sessions** - *middle*

### HTTPS and SSL/TLS

- **HTTPS purpose** - *junior*
- **SSL/TLS handshake** - *middle*
- **Certificates** - *middle*
- **Certificate authorities** - *middle*

### Authentication

- **Basic Authentication** - *junior*
- **Bearer tokens** - *middle*
- **OAuth 2.0** - *middle+*
- **JWT (JSON Web Tokens)** - *middle*
  - Structure: header, payload, signature
  - Use cases and limitations

### REST API

- **REST principles** - *middle*
  - Statelessness
  - Resource-based URLs
  - HTTP methods usage
  - HATEOAS

- **API versioning** - *middle*
- **Pagination** - *middle*
- **Filtering and sorting** - *middle*
- **API documentation**: Swagger/OpenAPI - *middle*

### GraphQL

- **GraphQL basics** - *middle+*
- **Queries, mutations, subscriptions** - *middle+*
- **Schema definition** - *middle+*

### WebSockets

- **WebSocket protocol** - *middle*
- **Full-duplex communication** - *middle*
- **Use cases**: real-time apps, chat, gaming - *middle*

### HTTP/2 Features

- **Multiplexing** - *middle+*
- **Server push** - *middle+*
- **Header compression** - *middle+*

---

## Stage 7. Security

### Common Vulnerabilities

- **SQL Injection** - *junior*
  - Prevention: prepared statements, parameterized queries

- **XSS (Cross-Site Scripting)** - *junior*
  - Types: reflected, stored, DOM-based
  - Prevention: input sanitization, output encoding

- **CSRF (Cross-Site Request Forgery)** - *middle*
  - Prevention: CSRF tokens, SameSite cookies

- **XXE (XML External Entity)** - *middle*
- **SSRF (Server-Side Request Forgery)** - *middle+*
- **Command Injection** - *middle*
- **Path Traversal** - *middle*

### Authentication & Authorization

- **Authentication vs Authorization** - *junior*
- **Password hashing** - *junior*
  - Bcrypt, Argon2, PBKDF2
  - Salt, iterations

- **Multi-factor authentication (MFA)** - *middle*
- **Password policies** - *junior*
- **Rate limiting** - *middle*
- **Account lockout** - *middle*

### Encryption

- **Symmetric encryption**: AES - *middle*
- **Asymmetric encryption**: RSA - *middle*
- **Hashing**: SHA-256, SHA-3 - *junior*
- **Encryption at rest and in transit** - *middle*

### Security Headers

- **Content-Security-Policy (CSP)** - *middle*
- **X-Frame-Options** - *middle*
- **X-Content-Type-Options** - *middle*
- **Strict-Transport-Security (HSTS)** - *middle*

### OWASP

- **OWASP Top 10** - *middle*
  > Familiarize yourself with the most critical web application security risks

### Security Best Practices

- **Principle of least privilege** - *middle*
- **Defense in depth** - *middle*
- **Input validation** - *junior*
- **Secure defaults** - *middle*
- **Regular security updates** - *junior*
- **Security audits and penetration testing** - *middle+*

### API Security

- **API keys** - *middle*
- **Rate limiting and throttling** - *middle*
- **API Gateway** - *middle+*

---

## Stage 8. Your Programming Language

*This section depends on your chosen backend language. Here are common topics you should cover:*

### Language Fundamentals

- **Syntax and basic constructs** - *junior*
- **Data types** - *junior*
- **Control flow** - *junior*
- **Functions** - *junior*
- **Error handling** - *junior*

### Object-Oriented Programming

- **Classes and objects** - *junior*
- **Inheritance** - *junior*
- **Polymorphism** - *middle*
- **Encapsulation** - *junior*
- **Interfaces / Traits** - *middle*

### Functional Programming

- **Pure functions** - *middle*
- **Immutability** - *middle*
- **Higher-order functions** - *middle*
- **Map, filter, reduce** - *middle*

### Concurrency

- **Threads** - *middle*
- **Locks and mutexes** - *middle*
- **Async/await** - *middle*
- **Promises / Futures** - *middle*
- **Deadlocks and race conditions** - *middle+*

### Memory Management

- **Stack vs Heap** - *middle*
- **Garbage collection** - *middle*
- **Memory leaks** - *middle*

### Package Management

- **Package managers**: npm, pip, composer, cargo, maven, etc. - *junior*
- **Dependencies management** - *junior*
- **Semantic versioning** - *middle*

### Testing

- **Unit testing** - *junior*
- **Test frameworks** specific to your language - *junior*
- **Mocking** - *middle*
- **Test coverage** - *middle*

### Popular Frameworks

- **Web frameworks** for your language - *middle*
- **ORM (Object-Relational Mapping)** - *middle*
- **Logging libraries** - *junior*

---

## Stage 9. Email

### Email Protocols

- **SMTP (Simple Mail Transfer Protocol)** - *middle*
  - Sending emails
  - SMTP servers

- **IMAP (Internet Message Access Protocol)** - *middle*
  - Reading emails
  - Folder management

- **POP3** - *middle*
  - Downloading emails
  - Differences from IMAP

### Email Structure

- **Email headers**: From, To, Subject, Date, Message-ID - *middle*
- **MIME (Multipurpose Internet Mail Extensions)** - *middle*
- **Multipart messages**: text and HTML - *middle*
- **Attachments** - *middle*

### Sending Email

- **Email libraries** for your language - *middle*
- **Email templates** - *middle*
- **Transactional emails** - *middle*

### Email Services

- **Email service providers**: SendGrid, Mailgun, Amazon SES - *middle*
- **Webhook handling** for email events - *middle*

### Email Security

- **SPF (Sender Policy Framework)** - *middle*
- **DKIM (DomainKeys Identified Mail)** - *middle*
- **DMARC (Domain-based Message Authentication)** - *middle+*

### Email Deliverability

- **Spam filters** - *middle*
- **Email reputation** - *middle*
- **Bounce handling** - *middle*
- **Unsubscribe mechanisms** - *middle*

---

## Stage 10. Full-Text Search

### Search Concepts

- **Indexing** - *middle*
- **Tokenization** - *middle*
- **Stemming and lemmatization** - *middle*
- **Stop words** - *middle*

### Search Engines

- **Elasticsearch** - *middle*
  - Document indexing
  - Query DSL
  - Aggregations
  - Relevance scoring

- **Apache Solr** - *middle+*
- **Meilisearch** - *middle*
- **Typesense** - *middle*

### Search Features

- **Full-text search** - *middle*
- **Fuzzy search** - *middle*
- **Faceted search** - *middle*
- **Autocomplete / suggestions** - *middle*
- **Highlighting** - *middle*

### Performance

- **Query optimization** - *middle+*
- **Index optimization** - *middle+*
- **Caching strategies** - *middle*

---

## Stage 11. Logs and Metrics

### Logging

- **Log levels**: DEBUG, INFO, WARN, ERROR, FATAL - *junior*
- **Structured logging**: JSON logs - *middle*
- **Log rotation** - *middle*
- **Centralized logging** - *middle*

### Log Management Systems

- **ELK Stack** (Elasticsearch, Logstash, Kibana) - *middle*
- **Grafana Loki** - *middle*
  > Log database based on Prometheus-like storage with excellent Grafana integration

### Metrics

- **Prometheus** or similar (e.g., Victoria Metrics) - *middle*
  > Popular metrics collection and storage system

- **Metric types** - *middle*
  - Count
  - Gauge
  - Histogram
  - Summary

- **Metric delivery methods**: push and pull - *middle*

### Prometheus Queries

- **Query syntax** - *middle*
  - Labels
  - Vectors
  - Intervals
  - Operators

- **Key functions** - *middle*
  - `rate`
  - `irate`

### Visualization

- **Grafana** - *middle+*
  > Excellent UI for displaying metrics from various storage systems, including Prometheus-like systems
  - Creating dashboards
  - Creating graphs
  - Setting up alerts

### Monitoring

- **Application monitoring** - *middle*
- **Infrastructure monitoring** - *middle*
- **Alerting** - *middle*
- **SLA, SLO, SLI** - *middle+*

---

## Stage 12. Design and Development

Patterns, concepts, and approaches to designing various web applications.

### Development Principles

- **GRASP (General Responsibility Assignment Software Patterns)** - *middle*
- **SOLID** - *middle*
  - Single Responsibility
  - Open–Closed
  - Liskov Substitution
  - Interface Segregation
  - Dependency Inversion

- **KISS (Keep It Simple, Stupid)** - *junior*
- **YAGNI (You Aren't Gonna Need It)** - *junior*
- **DRY (Don't Repeat Yourself)** - *junior*
- **IoC (Inversion of Control)** and DI (Dependency Injection) - *middle*
- **DDD (Domain-Driven Design)** - *middle*

### Architectural Patterns

*One project may use one or several architectural patterns, or even portions of them. Architectural patterns are approaches to solving the task assigned to the project.*

- **Hexagonal Architecture** - *middle+*
- **Event-Driven Architecture** (aka Broker pattern) - *middle+*
- **Onion Architecture** (aka Layered pattern) - *middle+*
- **CQRS** (Command and Query Responsibility Segregation) - *middle+*
- **SOA** (Service-Oriented Architecture) - *middle+*
- **Event Sourcing** - *middle+*

### Application Patterns

- **MVC (Model-View-Controller)** - *junior*
  > The oldest and quite widespread application design pattern, separating UI from application logic

- **ADR (Action-Domain-Responder)** - *middle*
  > MVC refinement for web tasks

- **MVP (Model-View-Presenter)** - *junior*
  > MVP is an iteration of MVC development due to application and UI complexity. Often used in front-end.

- **MVVM (Model-View-ViewModel)** - *middle*
  > Actually suitable for desktop or mobile applications. Rarely used in web applications.

### Design Patterns

*Patterns simplify development, as they're essentially community experience in solving various problems. Remember KISS and YAGNI to avoid falling into abstraction hell.*

- **Creational patterns** - *middle*
- **Structural patterns** - *middle*
- **Behavioral patterns** - *middle*

### Development Methodologies

*Not about scrum, agile, waterfall, planning, design, etc. This is about code writing methodologies.*

- **TDD (Test Driven Development)** - *middle*
  > Development through testing—the most famous development method requiring developers to first write tests for code, then the code itself.

- **BDD (Behavior Driven Development)** - *middle+*
  > Extended version of TDD where you first write not a test but a description of what needs to be done, in a domain language (e.g., Gherkin).

### Application Types

*Division by UI generation method.*

- **MPA (Multi-Page Application)** - *middle*
  > Classic application type with multiple pages generated on backend to create UI.

- **SPA (Single Page Application)** - *middle*
  > General name for applications that live in the browser and fetch data from the server. Can be SSG, SSR, CSR, or any combination.

- **SSG (Static Site Generation)** - *middle*
  > All application pages are pre-generated as static files. All dynamics are in JS. Can be both MPA and SPA.

- **SSR (Server Side Rendering)** - *middle*
  > Approach to page generation. Each request is processed on the server where UI is generated, then the server returns response to the client/front-end.

- **CSR (Client Side Rendering)** - *middle*
  > Approach to page generation. All UI is generated in the browser using JS. JS makes server requests for data to build or modify UI. SPA is a specific case of CSR.

- **PWA (Progressive Web Application)** - *middle*
  > Literally your website as a mobile application.

### Testing

- **Unit testing** - *junior*
  > Testing separate (and separated from each other) product parts, usually individual functions/methods. Unit tests also serve another purpose—checking your implementation architecture. Generally, if you can't write a unit test for a function/method without involving other application components, you may need to reconsider the architecture. Good unit testing leads to good Inversion of Control (IoC).

- **Integration tests** - *middle*
  > Complex test type. Checking functionality of an application, module, or component with another application, module, or component.

- **End-to-End (E2E) testing** - *middle*
  > E2E test example—testing a finished API application. Tests not application components but ready functionality.

- **Smoke tests** - *middle*
  > Smoke tests allow testing your application's ability to work. Sometimes used for testing whether infrastructure can support your application.

### Application and Design Problems

- **Technical debt** - *junior*
  > Technical debt starts accumulating in a project from the first lines of code. Always consider it in development and plan for its elimination.

- **Over-engineering** - *junior*
  > When implementation is much larger or more complex than required. Will require massive resources for project maintenance.

- **Premature optimization** - *junior*
  > Resorting to optimization where it's not currently needed. Will consume massive resources during project development.

### Other Concepts

- **Refactoring techniques** - *middle*
  > To eliminate technical debt, you'll need to refactor frequently.

- **Anti-patterns** - *middle*
  > Knowing what to do is useful, but knowing what NOT to do is equally useful.

- **Semver (Semantic Versioning)** - *middle*
  > The most widespread principle for application version naming. Required in some languages and package managers.

### Distributed Systems

*When an application hits the server ceiling, you have only one option—make the application work on multiple servers. This greatly complicates the application, and many resources go into maintaining data integrity and consistency.*

- **CAP and PACELC theorems** - *middle+*
  > In distributed systems, you must sacrifice something. PACELC is an extended CAP theorem. These theorems describe which parameters the system must sacrifice.

- **Microservices architecture** - *middle+*

---

## Contributing

If you want to change something (item, link, typo), create an issue or make a PR. To discuss the document, use discussions.

---

**Good luck on your backend development journey! 🚀**
