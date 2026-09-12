# Wikipedia Database Management System

A relational database project developed using MySQL and SQL to model the core functionality of a Wikipedia-like collaborative encyclopedia.

## Overview

The system manages users, pages, revisions, categories, watchlists, talk pages, comments, permissions, administrative logs, and page restrictions.

The project focuses on relational database design, data integrity, SQL querying, and modelling relationships between different entities.

## Key Features

- User, role, and permission management
- Page and category management
- Page revision and text version tracking
- Page edit and revision history
- User watchlists
- Page-to-page internal links
- Talk pages and threaded comments
- User blocking and page restrictions
- Activity and administrative logging
- Keyword-based page search
- Administrative statistics

## Database Concepts

- Relational database design
- Database normalisation
- Primary and foreign keys
- One-to-many and many-to-many relationships
- CRUD operations
- SQL joins
- Indexing
- Stored procedures
- Aggregate queries
- Self-referencing relationships

## Main Entities

- `user`
- `role`
- `permission`
- `page`
- `revision`
- `text`
- `category`
- `watchlist`
- `talk_pages`
- `talk_comment`
- `log`
- `block`
- `page_restriction`

## Example SQL Operations

The project includes queries for:

- Creating and updating page revisions
- Viewing revision history
- Displaying pages with their categories
- Finding internal links between pages
- Retrieving user roles and permissions
- Viewing blocked users and administrators
- Managing talk-page comments and replies
- Searching pages by keywords
- Generating administrative statistics

## Technologies Used

- **MySQL**
- **SQL**
- **Relational Database Design**
