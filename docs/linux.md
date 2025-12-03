# Linux Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Linux** using Docker.

### 1. Open Terminal

You may use:

•	Terminal (default Ubuntu)
  
•	Any terminal emulator (GNOME Terminal, Konsole, etc.)

### 2. Get 3 docker images on the command prompt(cmd).

```
docker pull adinekinar16/fplas-backend:latest
docker pull adinekinar16/fplas-frontend:latest
docker pull 24091997/fplas-nginx-2024:v1
```

### 3. Change the desktop directory on the command prompt(cmd)

```
cd Desktop
```

### 4. Download the Project

#### Option A — Without Git

1. Open the GitHub repository.
2. Click **Code → Download ZIP**.
3. Extract it.
4. Move to Desktop.
5. Rename to:

```
fplas-cmp-test-2025
```

> [!CAUTION]
> Ensure the project folder is placed directly inside your Desktop and named exactly `fplas-cmp-test-2025`.

#### Option B — With Git

```
git clone https://github.com/adinekinar/fplas-cmp-test-2025.git
cd fplas-cmp-test-2025
```

### 5. Configure Output Folder in docker-compose.yml

Open the docker-compose.yml file in the "fplas-cmp-test-2025" project and Modify the following directory to match your PC's Desktop directory. Then, the results directory appears on PC's Desktop.

```
C:/Users/safiraak/Desktop/fplas_results:/app/addon/output

to

/home/.../Desktop/results:/app/addon/output
```

<img width="579" height="216" alt="Screenshot docker compose linux" src="https://github.com/user-attachments/assets/34a34a39-8b30-4d17-a5b6-cab4b3fa1f2e" />

### 6. Run Docker Compose

Move into the project folder:

```
cd ~/Desktop/fplas-cmp-test-2025
```
Run the system:
```
docker compose up
```
> This command must be executed from inside the project folder.

### 7. Open Chrome browser and navigate to http://localhost:4000/

#### 🔍 How to Know If Docker Compose Is Running Correctly

##### A. Terminal shows continuous logs

Example:

gambar

If logs continue → the system is running.

##### B. No “ERROR” appears

Warnings are okay.

### 8. Stop

When you want to shut down the system:

a. Go back to the Terminal window where Docker is running

b. Press: `Ctrl+C`

c. Wait until containers stop and logs finish

d. Close Terminal






