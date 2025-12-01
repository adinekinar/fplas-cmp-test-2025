# Linux Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Linux** using Docker.

## 1. Requirements

```
docker --version
docker compose version
```

## 2. Pull Docker Images

```
docker pull adinekinar16/fplas-backend:latest
docker pull adinekinar16/fplas-frontend:latest
docker pull 24091997/fplas-nginx-2024:v1
```

## 3. Download the Project

### With Git

```
cd ~/Desktop
git clone https://github.com/your-user/fplas-2025.git
cd fplas-2025
```

### Without Git

1. Download ZIP
2. Extract
3. Move to Desktop
4. Rename to fplas-2025

```
cd ~/Desktop/fplas-2025
```

## 4. Create Output Directory

```
mkdir -p ~/Desktop/fplas_results
```

## 5. Configure docker-compose.yml

```yaml
nplas-app:
  image: adinekinar16/fplas-frontend:latest
  volumes:
    - /home/<user>/Desktop/fplas_results:/app/addon/output
```

## 6. Run

```
cd ~/Desktop/fplas-2025
docker compose up
```

## 7. Access

```
http://localhost:4000/
```

## 8. Output

```
/home/<user>/Desktop/fplas_results
```

## 9. Stop

```
docker compose down
```
