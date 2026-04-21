# FIT4012 Lab 2 – Classical Ciphers Project Documentation

## Overview

This is a **C++ project** that implements two classical encryption algorithms:

1. **Caesar Cipher** - character shifting with lowercase, spaces, and decryption
2. **Rail Fence Cipher** - zigzag pattern encryption with decryption and file I/O

---

## Configuration Files Analysis

### 1. **check_lab2.py** (.github/scripts/)

**Purpose**: Automated validation script that checks if the lab submission meets all requirements.

**Required Files Validation**:

- ✅ `README.md` must exist
- ✅ `report-1page.md` must exist
- ✅ `src/caesar.cpp` must exist
- ✅ `src/rail_fence.cpp` must exist
- ✅ `data/input.txt` must exist
- ✅ `tests/test_cases.md` must exist
- ✅ `logs/run_log.md` must exist

**Content Validations**:

- ✅ README must contain keywords: `caesar`, `rail fence`, `github` (case-insensitive)
- ✅ No `TODO(student)` placeholders in `src/caesar.cpp`
- ✅ No `TODO(student)` placeholders in `src/rail_fence.cpp`
- ✅ `src/caesar.cpp` must include `caesar_decrypt()` function
- ✅ `src/rail_fence.cpp` must include `rail_fence_decrypt()` function
- ✅ `src/rail_fence.cpp` must include `read_message_from_file()` function (for Q8)
- ✅ `report-1page.md` results table must be filled (not placeholder: `| I LOVE YOU | 3 |  |  |`)
- ✅ Minimum 6 test cases must be checked in `tests/test_cases.md`
- ✅ Minimum 6 log entries must be checked in `logs/run_log.md`
- ✅ Log placeholder text must be replaced with actual learning summary

**Compilation Checks**:

- ✅ `src/caesar.cpp` compiles with: `g++ -std=c++17 -O2 -Wall -Wextra`
- ✅ `src/rail_fence.cpp` compiles with: `g++ -std=c++17 -O2 -Wall -Wextra`

**Warnings** (non-blocking):

- ⚠️ Report table may have placeholder entries
- ⚠️ Learning summary in run log should replace template text

---

### 2. **lab2-check.yml** (.github/workflows/)

**Purpose**: GitHub Actions CI/CD workflow for automated validation on push/PR.

**Workflow Details**:

- **Trigger**:
  - Runs on push to `main` or `master` branches
  - Runs on pull requests to `main` or `master`
  - Can be manually triggered via `workflow_dispatch`
- **Runner**: Latest Ubuntu environment
- **Steps**:
  - Checks out repository with full history
  - Runs the Python validation script
- **Command**: `python3 .github/scripts/check_lab2.py`
- **Status**: Primary CI/CD validation mechanism for automated grading

---

## Project Structure & File Requirements

### Required Files Overview

```
lab2-classical-ciphers-NgXuanQuang-1/
├── src/
│   ├── caesar.cpp          # Caesar Cipher implementation
│   └── rail_fence.cpp      # Rail Fence Cipher implementation
├── data/
│   └── input.txt           # Sample input file for Q8
├── tests/
│   └── test_cases.md       # Test case descriptions (min 6 items checked)
├── logs/
│   └── run_log.md          # Execution logs (min 6 items checked)
├── README.md               # Project overview
├── report-1page.md         # Lab report with results
└── .github/
    ├── scripts/
    │   └── check_lab2.py   # Validation script
    └── workflows/
        └── lab2-check.yml  # CI/CD workflow
```

---

## File Descriptions

### **src/caesar.cpp**

**Status**: Partially complete with TODO markers

**Implemented Functions**:

- `is_valid_message()` - checks if text contains only letters and spaces
- `shift_char()` - shifts a single character by given amount, handles upper/lowercase
- `caesar_encrypt()` - encryption (Q1+Q2)

**TODO Items**:

- `caesar_encrypt()` implementation for Q1 + Q2 (lowercase support, spaces)
- `caesar_decrypt()` implementation for Q3 (reverse shift)

**Key Features**:

- Handles both uppercase and lowercase letters
- Preserves spaces
- Uses modular arithmetic for wrapping (26 letters)
- Input validation before processing

**Sample Usage**:

```
Input:  "I LOVE YOU", key: 3
Output: "L ORYH BRX"  (each letter shifted by 3)

Decrypt:
Input:  "L ORYH BRX", key: 3
Output: "I LOVE YOU"  (shift back by -3)
```

---

### **src/rail_fence.cpp**

**Status**: Partially complete with TODO markers

**Implemented Functions**:

- `is_valid_message()` - validates input (letters and spaces only)
- `rail_fence_encrypt()` - zigzag pattern encryption (Q6 todo for space handling)
- `read_message_from_file()` - reads first line from file (Q8)

**TODO Items**:

- `rail_fence_encrypt()` modification for Q6 (preserve spaces in zigzag pattern)
- `rail_fence_decrypt()` implementation for Q5 (reconstruct plaintext)
- Validation for invalid rails (Q7)

**Algorithm Concept - Rail Fence (2 rails example)**:

```
Plaintext: "HELLO"
Rails = 2:

H   L
 E L O

Reading left-to-right: H L + E L O = "HLELO"

Plaintext: "I LOVE YOU"
Rails = 2:
I   O E  O
  L V   U
Result: "IOEOLV YU"
```

**Key Features**:

- Supports configurable number of rails
- Handles input validation
- Can read from external file
- Must preserve spaces in zigzag pattern

---

### **data/input.txt**

**Content**: Sample message for Q8 file input testing

```
I LOVE YOU
```

**Purpose**: Used for file-reading Q8 demonstration

---

### **tests/test_cases.md**

**Current Status**: Template with unchecked items

**Required Test Coverage**:

- [ ] Caesar encrypt: `I LOVE YOU` with key `3`
- [ ] Caesar encrypt: `hello world` with key `5`
- [ ] Caesar decrypt: `LORYH BRX` with key `3`
- [ ] Rail Fence encrypt: `I LOVE YOU` with `2` rails
- [ ] Rail Fence encrypt: `I LOVE YOU` with `4` rails
- [ ] Rail Fence decrypt with valid ciphertext
- [ ] Input validation (invalid characters)
- [ ] File input from `data/input.txt`

**Minimum Requirement**: At least 6 items must be marked with `[x]`

---

### **logs/run_log.md**

**Current Status**: Template with placeholder text

**Required Log Entries**:

- [ ] Caesar encrypt test with `I LOVE YOU`, key `3`
- [ ] Caesar encrypt test with `hello world`, key `5`
- [ ] Caesar decrypt test with `LORYH BRX`, key `3`
- [ ] Rail Fence encrypt with `2` rails
- [ ] Rail Fence encrypt with `4` rails
- [ ] Rail Fence decrypt test
- [ ] Input validation test
- [ ] File input test with `data/input.txt`

**Learning Summary Section**: Must replace template text with 3-5 lines describing lessons learned

**Minimum Requirement**: At least 6 items must be marked with `[x]`

---

### **report-1page.md**

**Status**: Template with placeholder text

**Required Sections**:

**Section 1: Objectives**

- Lab goals and skills developed

**Section 2: Methodology**

- Approach to implementing both ciphers
- How decryption was implemented
- File I/O approach

**Section 3: Results (Must be filled)**

**Section 3.1 - Caesar Cipher Results Table**:
| Input | Key | Output | Notes |
|---|---:|---|---|
| I LOVE YOU | 3 | [FILL IN] | Encrypt |
| hello world | 5 | [FILL IN] | Encrypt |
| LORYH BRX | 3 | [FILL IN] | Decrypt |

**Section 3.2 - Rail Fence Cipher Results Table**:
| Input | Rails | Output | Notes |
|---|---:|---|---|
| I LOVE YOU | 2 | [FILL IN] | Encrypt |
| I LOVE YOU | 4 | [FILL IN] | Encrypt |
| [CIPHERTEXT] | 2 | [FILL IN] | Decrypt |

**Section 3.3 - Validation & File Input**:

- Document invalid input handling results
- Document file reading results from `data/input.txt`

**Section 4: Conclusion**

- Summary of what was learned
- Challenges faced and how they were resolved
- Key insights about encryption algorithms

---

### **README.md**

**Status**: Complete

**Contains**:

- ✅ Lab objectives
- ✅ Project structure explanation
- ✅ Build instructions for both programs
- ✅ Required keywords: Caesar, Rail Fence, GitHub
- ✅ 8 question breakdown
- ✅ Submission process
- ✅ Notes about file handling

---

## Build & Verification Commands

### Compile Caesar Cipher

```bash
g++ -std=c++17 -O2 -Wall -Wextra -o caesar_bin src/caesar.cpp
./caesar_bin
```

### Compile Rail Fence Cipher

```bash
g++ -std=c++17 -O2 -Wall -Wextra -o rail_bin src/rail_fence.cpp
./rail_bin
```

### Run Validation Script

```bash
python3 .github/scripts/check_lab2.py
```

---

## Question Breakdown (Q1-Q8)

### Caesar Cipher (Q1-Q3)

- **Q1**: Handle lowercase letters in encryption
- **Q2**: Preserve spaces in Caesar cipher
- **Q3**: Implement Caesar decryption

### Rail Fence Cipher (Q4-Q8)

- **Q4**: Encrypt with different rail counts and observe results
- **Q5**: Implement Rail Fence decryption
- **Q6**: Preserve spaces in Rail Fence encryption
- **Q7**: Validate input (only letters and spaces allowed)
- **Q8**: Read message from file `data/input.txt` and encrypt

---

## Submission Checklist

- [ ] All required files exist in correct locations
- [ ] No TODO(student) placeholders remain in source files
- [ ] Both .cpp files compile without errors
- [ ] `caesar_encrypt()` handles lowercase and spaces (Q1+Q2)
- [ ] `caesar_decrypt()` correctly reverses encryption (Q3)
- [ ] `rail_fence_encrypt()` preserves spaces in pattern (Q6)
- [ ] `rail_fence_decrypt()` correctly reconstructs plaintext (Q5)
- [ ] `read_message_from_file()` reads from file (Q8)
- [ ] At least 6 test cases are marked as completed
- [ ] At least 6 log entries are marked as completed
- [ ] Learning summary replaces template text in logs
- [ ] Report results tables are completely filled
- [ ] README contains: Caesar, Rail Fence, GitHub keywords
- [ ] Minimum 3 meaningful commits in git history
- [ ] All files pushed to GitHub repository

---

## Validation Success Criteria

**Errors** (blocking submission):

- Missing required files
- TODO markers still present
- Missing functions (caesar_decrypt, rail_fence_decrypt, read_message_from_file)
- Fewer than 6 test cases checked
- Fewer than 6 log entries checked
- Compilation errors in either .cpp file

**Warnings** (non-blocking but recommended to fix):

- Report table has placeholder entries
- Learning summary still contains template text

**Pass Condition**: All errors resolved, code compiles, all validations pass.

---

## Expected Test Results Examples

### Caesar Cipher

```
Q1+Q2: "I LOVE YOU" + key 3 → "L ORYH BRX"
Q3:    "L ORYH BRX" + key 3 → "I LOVE YOU" (decrypt)
```

### Rail Fence Cipher

```
Q4+Q5: "HELLO" + 2 rails → "HLOELL" (encrypt) → "HELLO" (decrypt)
Q6: "I LOVE YOU" + 2 rails → preserve spaces in pattern
Q8: Read "I LOVE YOU" from file, encrypt with rails
```

---

## Project Status Summary

| Component       | Status         | Notes                              |
| --------------- | -------------- | ---------------------------------- |
| README.md       | ✅ Complete    | All keywords present               |
| caesar.cpp      | ⏳ In Progress | Has TODO markers for Q1-Q3         |
| rail_fence.cpp  | ⏳ In Progress | Has TODO markers for Q5-Q6         |
| test_cases.md   | ⏳ In Progress | Needs 6+ items checked             |
| run_log.md      | ⏳ In Progress | Needs 6+ logs + summary            |
| report-1page.md | ⏳ In Progress | Needs filled result tables         |
| data/input.txt  | ✅ Complete    | Sample data provided               |
| Compilation     | ⏳ Needs Work  | Has TODO markers preventing checks |

---

## How Automated Grading Works

1. **Push to GitHub** triggers lab2-check.yml workflow
2. **Workflow runs** check_lab2.py validation script
3. **Script checks**:
   - All required files exist
   - No TODO markers remain
   - Required functions implemented
   - Minimum test cases and logs completed
   - Code compiles successfully
4. **Results reported** as pass/fail with detailed errors
5. **Score assigned** based on validation results

**Success**: All validations pass → Lab accepted for grading
