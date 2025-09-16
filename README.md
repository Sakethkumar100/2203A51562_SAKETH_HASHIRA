# 2203A51562_SAKETH_HASHIRA
# Polynomial Constant Term Finder

This project reconstructs the constant term of a polynomial using **Lagrange interpolation**.  
The input is provided in JSON format where each point `(x, y)` is encoded with a given base.  
The decoded points are used to interpolate the polynomial, and the constant term (the secret) is extracted.

---

## Project Structure

PolynomialConstantTermFinder/
│── index.js # Main program
│── testCase1.json # Sample test case 1
│── testCase2.json # Sample test case 2
│── README.md # Project documentation

markdown
Copy code

---

## How It Works

1. **Input JSON**  
   Each JSON file contains:
   - `keys`:  
     - `n`: number of points available  
     - `k`: threshold number of points required for interpolation  
   - Numbered entries `"1"`, `"2"`, … representing `x` values.  
     Each entry has:
     - `base`: the base of the encoded number (2–36).  
     - `value`: the encoded string for `y`.  

2. **Decoding**  
   Each `y` value is converted to base-10 using a custom decoder that supports digits `0–9` and `A–Z` (case-insensitive).

3. **Lagrange Interpolation**  
   The program uses the points to interpolate the polynomial and compute the constant term (the secret).

4. **Output**  
   The program prints the constant term for each test case.

---

## Usage

1. Make sure you have [Node.js](https://nodejs.org) installed.  
   Check with:
   ```bash
   node -v
Clone or copy the project folder.

Place your test JSON files in the same directory as index.js.

Run the program:

bash
Copy code
node index.js
Example Input
testCase1.json
json
Copy code
{
  "keys": { "n": 4, "k": 3 },
  "1": { "base": "10", "value": "4" },
  "2": { "base": "2", "value": "111" },
  "3": { "base": "10", "value": "12" },
  "6": { "base": "4", "value": "213" }
}
testCase2.json
json
Copy code
{
  "keys": { "n": 10, "k": 7 },
  "1": { "base": "6", "value": "13444211440455345511" },
  "2": { "base": "15", "value": "aed7015a346d635" },
  "3": { "base": "15", "value": "6aeeb69631c227c" },
  "4": { "base": "16", "value": "e1b5e05623d881f" },
  "5": { "base": "8", "value": "316034514573652620673" },
  "6": { "base": "3", "value": "2122212201122002221120200210011020220200" },
  "7": { "base": "3", "value": "20120221122211000100210021102001201112121" },
  "8": { "base": "6", "value": "20220554335330240002224253" },
  "9": { "base": "12", "value": "45153788322a1255483" },
  "10": { "base": "7", "value": "1101613130313526312514143" }
}
Example Output
Run:

bash
Copy code
node index.js
Expected result:

pgsql
Copy code
Processing testCase1.json
Constant term (secret) = 23

Processing testCase2.json
Constant term (secret) = -13478698549472778234
Output Screenshots
Add your run screenshots here:

Test Case 1 Result:
<img width="659" height="166" alt="Screenshot 2025-09-16 114640" src="https://github.com/user-attachments/assets/024d4274-71e4-4c28-b410-66e7b84ed306" />
