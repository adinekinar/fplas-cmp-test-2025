# Windows Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Windows** using Docker Desktop.

## 1. Download Required Docker Images

```
docker pull adinekinar16/fplas-backend:latest
docker pull adinekinar16/fplas-frontend:latest
docker pull 24091997/fplas-nginx-2024:v1
```

## 2. Move to Desktop Directory

```
cd %USERPROFILE%\Desktop
```

If your project folder already exists:

```
cd %USERPROFILE%\Desktop\fplas-2025
```

## 3. Download the Project

### Option A — Without Git

1. Open the GitHub repository.
2. Click **Code → Download ZIP**.
3. Extract it.
4. Move to Desktop.
5. Rename to:

```
fplas-2025
```

### Option B — With Git

```
cd %USERPROFILE%\Desktop
git clone https://github.com/your-user/fplas-2025.git
cd fplas-2025
```

## 4. Configure Output Folder in docker-compose.yml

Edit:

```yaml
nplas-app:
  image: adinekinar16/fplas-frontend:latest
  volumes:
    - C:/Users/<YourName>/Desktop/fplas_results:/app/addon/output
```

Create folder:

```
mkdir %USERPROFILE%\Desktop\fplas_results
```

## 5. Run FPLAS

```
cd %USERPROFILE%\Desktop\fplas-2025
docker compose up
```

## 6. Access

```
http://localhost:4000/
```

## 7. Output Location

```
C:\Users\<YourName>\Desktop\fplas_results
```

## 8. Stop

```
docker compose down
```
