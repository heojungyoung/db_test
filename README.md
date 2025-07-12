# db_test

# 🚀 My Awesome Project

This is a brief README showing how to include **code** in Markdown.

## Features

- ✅ Easy to read
- 🛠️ Syntax highlighting
- 🔗 Links and images

## Usage

1. Clone the repo:
   ```bash
   git clone https://github.com/username/my-awesome-project.git
   cd my-awesome-project



# 📊 Database Schema & Queries

This document shows how to include SQL in Markdown with proper syntax highlighting.

## 1. Create Tables

```sql
-- Create a users table
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    created_at TIMESTAMP    DEFAULT CURRENT_TIMESTAMP
);

-- Create a posts table
CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    user_id INTEGER NOT NULL REFERENCES users(id),
    title   VARCHAR(200) NOT NULL,
    body    TEXT,
    posted_at TIMESTAMP    DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO users (username, email)
VALUES
  ('alice', 'alice@example.com'),
  ('bob',   'bob@example.com');

INSERT INTO posts (user_id, title, body)
VALUES
  (1, 'Hello World', 'This is my first post!'),
  (2, 'Markdown & SQL', 'How to mix SQL in Markdown.');


SELECT
  u.username,
  p.title,
  p.posted_at
FROM users u
JOIN posts p ON p.user_id = u.id
ORDER BY p.posted_at DESC;
