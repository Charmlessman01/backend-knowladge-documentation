# Backend Knowledge Documentation

## 1. Programming Language

### **Golang**

**Konsep yang Dipahami:**
- Struct dan methods
- Goroutines untuk concurrent processing
- Error handling
- Pointer basics
- Interface
- Package management dengan go mod

## 2. Framework

### **Fiber (Web Framework)**

**Fitur yang Dikuasai:**
- Basic routing (GET, POST, PUT, DELETE)
- Middleware basics (logger, CORS, Auth)
- Request parsing (JSON body, query params, path params)
- Response JSON
- Error handling middleware
- Route grouping untuk API versioning

## 3. Database

### **PostgreSQL**

**Pemahaman SQL:**
- CRUD operations (SELECT, INSERT, UPDATE, DELETE)
- CREATE TABLE dengan constraints
- WHERE clause untuk filtering
- ORDER BY dan LIMIT untuk sorting & pagination
- JOIN tables (INNER JOIN, LEFT JOIN)
- GROUP BY untuk grouping data

**Pemahaman Database:**
- Primary Key & Foreign Key
- Constraints (NOT NULL, UNIQUE, CHECK)
- Basic indexing untuk optimasi
- Transaction basics (BEGIN, COMMIT, ROLLBACK)
- Relasi antar table (One-to-Many, Many-to-Many)

### **Redis (Caching)**

**Operasi Dasar:**
- GET & SET data
- DELETE keys
- SET expiration (EXPIRE)
- Check TTL

**Use Cases:**
- Caching query results
- Store user sessions
- Temporary data storage
- Rate limiting sederhana

### **RabbitMQ (Message Queue)**

**Konsep Dasar:**
- Producer-Consumer pattern
- Queue untuk menyimpan message
- Publish message
- Consume message

## 4. ORM

### **Ent ORM**

**Kemampuan:**
- Schema definition dengan Go code
- Code generation dari schema
- CRUD operations type-safe
- Query dengan Where conditions
- Relasi entities (One-to-Many, Many-to-One)
- Transaction handling

## 5. Architecture

**Struktur Folder:**
```
internal/
├── domain/
│   ├── entities/     → Domain models
│   └── errors/       → Custom errors
├── ports/
│   ├── input/        → Use case interfaces
│   └── output/       → Repository interfaces
├── adapters/
│   ├── http/         → HTTP handlers (Fiber)
│   ├── postgres/     → Database implementation (Ent)
│   ├── redis/        → Cache implementation
│   └── rabbitmq/     → Queue implementation
└── infrastructure/
    ├── database/     → DB connection setup
    ├── cache/        → Redis connection
    └── queue/        → RabbitMQ connection
```

### **5.2. Clean Architecture**

**Struktur Folder:**
```
internal/
├── entities/        → Domain models
├── usecases/        → Business logic
│   └── user/
│       ├── create.go
│       ├── get.go
│       └── update.go
├── controllers/     → HTTP handlers
│   └── user/
│       └── handler.go
├── repositories/    → Repository interfaces
│   └── user_repo.go
└── infrastructure/
    ├── database/    → DB implementation
    └── http/        → HTTP server setup
```
