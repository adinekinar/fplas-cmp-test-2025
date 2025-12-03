# Windows Installation Guide – FPLAS 2025

This document explains how to run **FPLAS** on **Windows** using Docker Desktop.

### 0. Stop Existing FPLAS Containers (Important Before Installation)

Before installing the new FPLAS 2025 system, please stop any old FPLAS containers that may still be running on your PC.

This is important because:
- The previous version you installed last week uses the same ports (4000, 8080, 5000)
- If old containers are still running, the new system cannot start

Stop all running Docker containers:
```
docker stop $(docker ps -aq)
```
(Optional) Remove old stopped containers:
```
docker rm $(docker ps -aq)
```

> [!CAUTION]
> These commands only stop/remove containers, not your images or project files.
> Safe to use before installing the new FPLAS version.

Now you can continue with the installation steps below.

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
> [!CAUTION]
> / or \ \ is depends on your PC setup. Thus, try one of them until you see the results directory on PC's Desktop.

<img width="841" height="240" alt="Screenshot docker compose" src="https://github.com/user-attachments/assets/40c2c4f1-1fba-49b4-8976-d077e662afe4" />

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
##### A. PowerShell starts printing running logs
Example output :

<img width="1105" height="548" alt="Screenshot 2025-12-03 162648" src="https://github.com/user-attachments/assets/31424b1b-06d8-4613-b75e-db12333d5cd0" />

As long as you see continuous logs → Docker is running.

##### B. No “ERROR” messages appear

If only warnings appear, it’s usually fine.

### 7. Stop
When you want to shut down the system:

a.	Go back to the PowerShell window where Docker is running
	
b.	Press: `Ctrl+C`
	
c.	Wait until containers stop and logs finish
	
d.	Close PowerShell









