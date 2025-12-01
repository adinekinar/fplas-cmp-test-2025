# Linux Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Linux** using Docker.

### 1. Get 3 docker images on the command prompt(cmd).

```
docker pull adinekinar16/fplas-backend:latest
docker pull adinekinar16/fplas-frontend:latest
docker pull 24091997/fplas-nginx-2024:v1
```

### 2. Change the desktop directory on the command prompt(cmd)

```
cd Desktop
```

### 3. Download the Project

#### Option A — Without Git

1. Open the GitHub repository.
2. Click **Code → Download ZIP**.
3. Extract it.
4. Move to Desktop.
5. Rename to:

```
fplas-cmp-test-2025
```

#### Option B — With Git

```
git clone https://github.com/adinekinar/fplas-cmp-test-2025.git
cd fplas-cmp-test-2025
```

### 4. Configure Output Folder in docker-compose.yml

Open the docker-compose.yml file in the "fplas-cmp-test-2025" project and Modify the following directory to match your PC's Desktop directory. Then, the results directory appears on PC's Desktop.

```
diisi sini

to

/home/.../Desktop/results:/app/addon/output
```
### 5. Run FPLAS

```
fplas-cmp-test-2025
```
```
docker compose up
```

## 6. Open Chrome browser and navigate to http://localhost:4000/

## 7. Stop

```
docker compose down
```


