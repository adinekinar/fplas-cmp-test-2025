# Windows Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Windows** using Docker Desktop.

### 1. Open PowerShell
Please use **Windows PowerShell** or **Command Prompt(cmd)** for all commands.

How to open:
- Press **Windows Key**
- Type **PowerShell** or **cmd**
- Click **Windows PowerShell** or **Command Prompt**

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
> Make sure the unzipped project folder is directly on your Desktop.
> Do not rename the folder.

#### Option B — With Git

```
git clone https://github.com/adinekinar/fplas-cmp-test-2025.git
cd fplas-cmp-test-2025
```

### 4. Configure Output Folder in docker-compose.yml

Open the docker-compose.yml file in the "fplas-cmp-test-2025" project and Modify the following directory to match your PC's Desktop directory. Then, the results directory appears on PC's Desktop.

```
C:/Users/safiraak/Desktop/fplas_results:/app/addon/output

to

C:\\Users\\User\\Desktop\\results:/app/addon/output (or) /C:/Users/User/Desktop/results:/app/addon/output 
```
> Caution
> / or \ \ is depends on your PC setup. Thus, try one of them until you see the results directory on PC's Desktop.

### 5. Run the Docker Command
```
cd fplas-cmp-test-2025
```
Now you can run the system using:
```
docker compose up
```
> This command must be executed inside the project folder.
> If you run it from the wrong location, Docker will not work.

### 6. Open Chrome browser and navigate to http://localhost:4000/

#### 🔍 How to Know If Docker Compose Is Running Correctly
You will know Docker is running properly if:
##### 1. PowerShell starts printing running logs
Example output :

gambar

As long as you see continuous logs → Docker is running.

##### 2. No “ERROR” messages appear

If only warnings appear, it’s usually fine.

### 7. Stop
When you want to shut down the system:
	1.	Go back to the PowerShell window where Docker is running
	2.	Press: ``Ctrl+C``
  3.	Wait until containers stop and logs finish
	4.	Close PowerShell



