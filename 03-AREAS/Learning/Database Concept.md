


# Data, Databases & DBMS

## Data
- Raw facts and statistics (IP addresses, cookies, personal info)
- Becomes **information** when processed meaningfully

## Database
- Organized collection of related data
- Stored electronically for easy access and management

## DBMS
**Database Management System** — software to create, manage, and manipulate databases.

### Key Features
- **Tables**: Data stored in related tables
- **Less Redundancy**: Avoids duplicate data (normalization)
- **Consistency**: Real-time updates across users
- **Multi-user**: Concurrent access with security
- **Query Language**: Easy data retrieval (SQL)
- **Security**: Access control and permissions
- **Transactions**: Maintains integrity during operations

### Pros
- Reduces data duplication
- Fast data retrieval
- Easy maintenance
- Supports massive datasets
- Integrates with applications

### Cons
- Complex to set up
- Expensive licensed versions (use MySQL/PostgreSQL for free)
- Requires significant storage

# Components of a Database Management System (DBMS)

A Database Management System (DBMS) consists of five major components:

1. **Hardware**
   - Refers to the physical components necessary for data storage and access, such as computers, hard drives, and input/output channels.

2. **Software**
   - The program that controls the DBMS. It acts as a wrapper around the database, providing an interface to store, access, and update data.

3. **Data**
   - The primary resource of a DBMS. It includes actual data and metadata, which is data about the data, essential for understanding stored information.

4. **Procedures**
   - General instructions for using the DBMS, including setup, database management, backups, and report generation.

5. **Database Access Language**
   - A specialized language for writing commands to interact with the database, enabling operations like data access, insertion, updating, and deletion.

## User Roles

- **Database Administrator (DBA)**: Manages the DBMS, focusing on security, availability, licensing, and user access.
- **Application Programmer/Software Developer**: Develops and designs DBMS components.
- **End User**: Interacts with the DBMS through applications to store, retrieve, update, and delete data.

# DBMS Architecture Overview

## Types of DBMS Architecture
- **Centralized**: All data stored at one location.
- **Decentralized**: Multiple copies of the database at different locations.
- **Hierarchical**: Data structured in a tree-like format.

## DBMS Architectures

### 1-Tier Architecture
- Direct access to the database.
- Used in local application development.
- Programmers communicate directly with the database for quick responses.

### 2-Tier Architecture
- **Structure**: User ↔ Application Layer ↔ DBMS
- Application layer acts as a mediator between the user and the DBMS.
- **Advantages**:
  - Additional security as DBMS is not exposed directly to the user.
  - Security and authentication checks can be implemented in the application layer.
- **Example**: ODBC (Open Database Connectivity) provides APIs for client-side programs to access the DBMS.

### 3-Tier Architecture
- **Structure**: User ↔ GUI Layer ↔ Application Layer ↔ DBMS
- Adds a Presentation or GUI Layer for user interaction.
- End users interact with the GUI without knowledge of the underlying application or DBMS.
- **Example**: PHPMyAdmin (for MySQL) is a classic example of 3-tier architecture.
