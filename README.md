# 📱 Flutter Clean Architecture Project

This project is implemented using **Clean Architecture** principles to ensure scalability, maintainability, and a strict separation of concerns.

---

## 🏗️ Architecture Overview

The project is divided into three main layers, following the dependency rule (dependencies point inwards toward the Domain layer).

### 🎨 1. Presentation Layer
Responsible for everything the user sees and interacts with.
- **Screens:** The primary UI pages of the application.
- **Widgets:** Reusable UI components.
- **State Management:** Handles the logic for updating the UI (e.g., **Bloc**, **Provider**, or **Cubit**).

### 🧠 2. Domain Layer
The "Heart" of the application. This layer is completely independent of any external libraries or frameworks.
- **Entities:** Simple business objects.
- **Use Cases:** Specific application logic (e.g., `GetUserData`, `UpdateProfile`).
- **Repositories (Abstract):** Interfaces that define the contracts for data operations.

### 💾 3. Data Layer
Responsible for data retrieval and persistence.
- **Models:** Data transfer objects (DTOs) with JSON serialization logic (`fromJson`, `toJson`).
- **Repositories (Implementation):** The actual implementation of the Domain repository interfaces.
- **Data Sources:** - *Remote:* Handles API calls (e.g., **RESTful API**, **Firebase**, or **Supabase**).
    - *Local:* Handles local caching (e.g., **Hive**, **Sqflite**, or **Shared Preferences**).

---

## 📂 Folder Structure

```text
lib/
 ├── core/              # Shared utilities, constants, and themes
 ├── features/          # Feature-based organization
 │   └── feature_name/
 │       ├── data/
 │       │   ├── datasources/
 │       │   ├── models/
 │       │   └── repositories/
 │       ├── domain/
 │       │   ├── entities/
 │       │   ├── repositories/
 │       │   └── usecases/
 │       └── presentation/
 │           ├── screens/
 │           ├── widgets/
 │           └── manager/ (State Management logic)
 └── main.dart