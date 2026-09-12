# Blog Management System (Wikipedia Database)

A MySQL-based relational database project designed to model the core functionality of a Wikipedia-like collaborative content management system.

## Project Overview

The Blog Management System (Wikipedia Database) manages users, roles, permissions, pages, revisions, text content, categories, watchlists, talk pages, comments, logs, blocks, page links, and page restrictions.

The project demonstrates practical implementation of relational database concepts using MySQL and SQL.

## Features

- User registration and user management
- Role and permission management
- Page creation and management
- Page revision and version history
- Text content management
- Page categorisation
- User watchlists
- Page-to-page internal links
- Talk pages and comments
- Threaded comment replies
- User blocking
- Page restrictions
- Activity and administrative logging
- SQL joins and combined queries
- Page and content search
- Administrative statistics

## Database Schema

The database contains the following main tables:

- `User`
- `Roles`
- `Permission`
- `User_role`
- `role_permission`
- `Page`
- `Revision`
- `Text`
- `Watchlist`
- `Category`
- `Page_category_link`
- `Page_Link`
- `Talk_page`
- `Talk_Comment`
- `Log`
- `Block`
- `Page_restriction`

## Entity Relationships

The database implements several types of relationships:

### User and Roles
Users are assigned roles through the `User_role` bridge table.

**Relationship:** Many-to-Many

### Roles and Permissions
Roles are associated with permissions through the `role_permission` bridge table.

**Relationship:** Many-to-Many

### User and Revision
A user can create multiple revisions.

**Relationship:** One-to-Many

### Page and Revision
A page can have multiple revisions, while each revision belongs to one page.

**Relationship:** One-to-Many

### Revision and Text
Each revision is associated with the text content of that version.

**Relationship:** One-to-One

### User and Page through Watchlist
Users can watch multiple pages, and a page can be watched by multiple users.

**Relationship:** Many-to-Many

### Page and Category
Pages can belong to multiple categories through `Page_category_link`.

**Relationship:** Many-to-Many

### Page and Talk Page
A page can have an associated talk page for discussions.

**Relationship:** One-to-One

### Talk Page and Comments
A talk page can contain multiple comments.

**Relationship:** One-to-Many

### Comments and Replies
Comments can reference other comments to support threaded discussions.

**Relationship:** Self-Referencing

## Main Functional Workflows

### 1. Page Edit and Revision Flow

When a user edits a page:

1. New text content is inserted into the `Text` table.
2. A new revision is created in the `Revision` table.
3. The revision stores the page, text, user, description, and timestamp.
4. The page's latest revision ID is updated.
5. Previous revisions remain available for revision history.

Example:

```sql
INSERT INTO revision 
(page_id, text_id, user_id, description)
VALUES 
(2, 13, 2, 'Change the topic of physics');

UPDATE page
SET page_latest_id = 15
WHERE page_id = 2;
