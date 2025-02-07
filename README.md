# SQL-Queries

# Apply Filters to SQL Queries

## **Project Description**

My organization is working to **enhance system security**. My role is to ensure **data security**, investigate potential security issues, and update **employee computers** as necessary.

The following **SQL queries** use **filters** to retrieve **specific security-related data**.

---

## **1. Retrieve After-Hours Failed Login Attempts**

A potential security incident occurred **after business hours** (**after 18:00**).  
I need to **identify all failed login attempts** that occurred **after 18:00**.

### **SQL Query:**
```sql
SELECT * 
FROM log_in_attempts 
WHERE login_time > '18:00' 
AND success = FALSE;
```

### **Explanation:**
- `login_time > '18:00'` → Filters for logins **after 6:00 PM**.
- `success = FALSE` → Filters for **failed** login attempts.

---

## **2. Retrieve Login Attempts on Specific Dates**

A **suspicious event** occurred on **2022-05-09**.  
All login attempts on **2022-05-09** and **2022-05-08** must be investigated.

### **SQL Query:**
```sql
SELECT * 
FROM log_in_attempts 
WHERE login_date = '2022-05-09' 
OR login_date = '2022-05-08';
```

### **Explanation:**
- `login_date = '2022-05-09'` → Filters for logins on **May 9, 2022**.
- `login_date = '2022-05-08'` → Filters for logins on **May 8, 2022**.

---

## **3. Retrieve Login Attempts Outside of Mexico**

Some login attempts **originated outside of Mexico** and require investigation.

### **SQL Query:**
```sql
SELECT * 
FROM log_in_attempts 
WHERE country NOT LIKE 'MEX%';
```

### **Explanation:**
- `NOT LIKE 'MEX%'` → Excludes entries where `country` starts with **MEX** (matching both **MEX** and **MEXICO**).

---

## **4. Retrieve Employees in the Marketing Department**

The **Marketing department** in the **East building** requires **computer updates**.

### **SQL Query:**
```sql
SELECT * 
FROM employees 
WHERE department = 'Marketing' 
AND office LIKE 'East%';
```

### **Explanation:**
- `department = 'Marketing'` → Filters for **Marketing employees**.
- `office LIKE 'East%'` → Filters for **employees in the East building**.

---

## **5. Retrieve Employees in Finance or Sales**

Employees in the **Finance** and **Sales** departments require a **different security update**.

### **SQL Query:**
```sql
SELECT * 
FROM employees 
WHERE department = 'Finance' 
OR department = 'Sales';
```

### **Explanation:**
- `department = 'Finance'` → Filters for **Finance employees**.
- `department = 'Sales'` → Filters for **Sales employees**.

---

## **6. Retrieve All Employees NOT in IT**

A final security update must be applied to **employees not in the IT department**.

### **SQL Query:**
```sql
SELECT * 
FROM employees 
WHERE department NOT LIKE 'Information Technology';
```

### **Explanation:**
- `NOT LIKE 'Information Technology'` → Excludes employees in **IT**.

---

## **Summary**

I successfully **applied filters** to SQL queries to retrieve **critical security data** from **two tables**:  
- **`log_in_attempts`** → To investigate **suspicious login activities**.
- **`employees`** → To identify **employees needing security updates**.

### **SQL Techniques Used:**
✅ `AND` / `OR` → For **specific conditional filters**.  
✅ `NOT` → To **exclude** unwanted data.  
✅ `LIKE` / `%` Wildcard → To **match text patterns**.  

By implementing these **SQL filters**, I was able to **isolate security risks** and **enhance system protection**.
