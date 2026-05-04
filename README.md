# GOFIVE Assignment - ASP.NET Web API

## 📌 Overview

This project is a RESTful Web API built using ASP.NET Core and Entity Framework Core.
It uses SQLite as the database and includes Swagger for API testing.

---

## 🛠 Tech Stack

* ASP.NET Core Web API
* Entity Framework Core
* SQLite
* Swagger (Swashbuckle)
* API Versioning

---

## 📦 Prerequisites

Install the following before running the project:

* .NET 8 SDK
  https://dotnet.microsoft.com/download

Check installation:

```bash
dotnet --version
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Kitpoom101/GOFIVE-assignmentBE.git
cd GOFIVE-assignmentBE
```

---

### 2. Restore dependencies

```bash
dotnet restore
```

---

### 3. Apply database migrations

```bash
dotnet ef database update
```

> This will create/update the SQLite database using existing migrations.

---

### 4. Run the API

```bash
dotnet run
```

---

### 5. Access the API

* Base URL:
  http://localhost:5214

* Swagger UI:
  http://localhost:5214/swagger

---

## 🗄 Database (SQLite)

* Database file: `mydb.db` (located in the root of the API folder)
* Uses Entity Framework Core migrations
* Schema is managed in the `Migrations/` folder

If you run into database issues:

```bash
# delete database file
rm mydb.db

# reapply migrations
dotnet ef database update
```

---

## 📁 Project Structure

```
.
├── Controllers/
│   └── UsersController.cs
├── Data/
│   └── AppDBContext.cs
├── Models/
│   └── User.cs
├── Migrations/
├── Properties/
│   └── launchSettings.json
├── appsettings.json
├── appsettings.Development.json
├── Program.cs
├── API.csproj
├── mydb.db
└── README.md
```


---

## ⚙️ Configuration

Connection string is defined in:

```
appsettings.json
```

Example:

```json
"ConnectionStrings": {
  "DefaultConnection": "Data Source=mydb.db"
}
```

---

## ⚠️ Common Issues

### 1. Port already in use

Edit port in:

```
Properties/launchSettings.json
```

---

### 2. EF Core commands not working

Install EF CLI tools:

```bash
dotnet tool install --global dotnet-ef
```

---

### 3. Database errors

Delete `mydb.db` and run:

```bash
dotnet ef database update
```

---

## 👨‍💻 Notes

* Project currently targets `.NET 10`, but `.NET 8` is recommended for better compatibility
* SQLite is used for simplicity and portability
* Swagger is enabled for easy API testing

---

## 🔧 Recommended Improvements

### Ignore build files

Add to `.gitignore`:

```
bin/
obj/
```

Then remove them from Git:

```bash
git rm -r --cached bin obj
git commit -m "Remove build files"
git push
```

---

### Optional: Ignore database file

```
*.db
```

---

### Recommended .NET version

Update your `.csproj`:

```xml
<TargetFramework>net8.0</TargetFramework>
```
