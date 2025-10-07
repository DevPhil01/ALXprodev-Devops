# Shell Scripting Practice — Batch Processing and Parallel API Requests

## 📅 Date
**October 6, 2025**

---

## 🧠 Overview
This session focused on enhancing Bash scripting skills by implementing **batch data retrieval**, **error handling**, and **parallel processing** using background jobs and process management commands.  
The exercises were based on fetching Pokémon data from the **PokéAPI** using `curl`, and progressively improving script reliability and performance.

---

## 🧩 Tasks Completed

### **Task 1: Batch Pokémon Data Retrieval**
- **Objective:** Fetch Pokémon data from the [PokéAPI](https://pokeapi.co) in batch.
- **Description:**  
  A Bash script was created to loop through a list of Pokémon names and retrieve their details using `curl`.
- **Key Concepts:**
  - Use of arrays to store multiple Pokémon names.
  - Directory creation with `mkdir -p`.
  - File output redirection.
  - Use of loops for repetitive API calls.

---

### **Task 2: Add Robust Error Handling and Retry Logic**
- **Objective:** Make the script fault-tolerant to network issues and invalid names.
- **Description:**  
  Enhanced the previous batch retrieval script to:
  - Detect failed requests.
  - Retry failed API calls up to **3 times** before logging an error.
  - Skip to the next Pokémon if retries fail.
- **Key Concepts:**
  - Conditional statements (`if` / `$?` exit codes).
  - Loops for retry mechanisms.
  - Logging failures to a dedicated error log file.

---

### **Task 3: Speed Up Retrieval with Parallel Processing**
- **Objective:** Use **background processes** to fetch data faster.
- **Description:**  
  Implemented parallel execution using `&` and managed the background processes effectively.
  The script ensures all background processes complete before proceeding.
- **Key Concepts:**
  - Running multiple processes concurrently using `&`.
  - Collecting process IDs (`$!`) for management.
  - Using `wait` to synchronize.
  - Process monitoring with `kill -0` and termination with `kill`.
  - Timeout mechanism for slow or hanging processes.

---

## ⚙️ Commands and Tools Used
- `curl` — To make HTTP requests to the PokéAPI.
- `mkdir`, `rm`, `echo`, `sleep`, `wait` — For basic file and process operations.
- `kill` — For terminating background processes that exceed time limits.
- `[]` / `$?` — For command success or failure checking.
- Redirection (`>`, `>>`) — For writing to log and output files.

---

## 🗂️ Files Created
| File Name | Description |
|------------|-------------|
| `batchProcessing-0x04` | Final script implementing parallel Pokémon data retrieval with process management (`kill`, `wait`). |
| `pokemon_data_parallel/` | Directory containing fetched Pokémon data in JSON format. |
| `parallel_errors.log` | Log file capturing any failed requests or killed processes. |
| `README.md` | Documentation for today’s shell scripting exercises. |

---

## 🚀 Learning Outcomes
By completing this session, the following skills were reinforced:
1. Writing efficient **Bash scripts** for automation.
2. Implementing **error handling** and **retry mechanisms** for reliability.
3. Using **background processes** and **parallelization** to improve performance.
4. Managing processes safely using `kill` and `wait`.
5. Understanding how to build modular, well-documented scripts.

---

## 🧾 Example Run Output
```
Starting parallel Pokémon data fetch...
Fetching data for bulbasaur...
Fetching data for ivysaur...
Fetching data for venusaur...
Fetching data for charmander...
Fetching data for charmeleon...
Saved data to pokemon_data_parallel/bulbasaur.json ✅
Saved data to pokemon_data_parallel/ivysaur.json ✅
Saved data to pokemon_data_parallel/charmander.json ✅
Saved data to pokemon_data_parallel/venusaur.json ✅
Saved data to pokemon_data_parallel/charmeleon.json ✅
✅ Parallel batch processing complete!
```

---

## ✍️ Author
**PHIL JR**  
*Shell Scripting Practice – API Data Automation & Process Management*
