# 💼 Mathematical Modeling in Banking – List 3 Project (Summer Semester 2024/25)

This repository contains a project for the *Mathematical Modeling in Banking* course, focused on credit risk analytics and default modeling. The objective is to identify non-performing loans (NPLs) and calculate default rates (PD) using historical loan-level data.

## 🗓️ Project Information

- **Course**: Mathematical Modeling in Banking  
- **Semester**: Summer 2024/25  

---

## 🎯 Objective

Build a credit risk classification and estimation framework by:
- Identifying **defaults** and **cures** based on provided business rules.
- Calculating **observed default rates** (DRₜ).
- Modeling expected **PD** for different customer risk groups.

---

## 📁 Dataset Overview

### 🧾 Credit File
| Column | Description |
|--------|-------------|
| `Id_kredytu` | Unique loan identifier |
| `Period_dte` | Reporting date |
| `Start_bal_amt` | Initial loan amount |
| `Start_dte` | Loan start date |
| `Bal_amt` | Current balance |
| `Kwota_przeterm` | Overdue amount |
| `Dpd` | Days past due |
| `Fl_windykacji` | Flag for collections |
| `Fl_smierc` | Flag for borrower death |
| `TTM` | Time to maturity (in years) |

### 📊 DMA File
- Contains: `Id_kredytu`, `Period_dte`, and `DMA` – Days with overdue > PLN 400 and > 1% of exposure.

### 💸 Write-offs File
- Contains: `Id_kredytu`, `Period_id` (in format 12 × year + month), and `Kwota umorzona` (amount written off).

---

## 🔍 Key Definitions

### 🟥 Default Conditions
A loan is classified as **non-performing (default)** if any of the following apply:
- The account is under **collections**
- There are **>90 days with DMA condition met**
- All borrowers are **deceased**

### 🟩 Cure Conditions
A loan returns to performing status (**cure**) if:
- The account **no longer meets default conditions**
- There are **no DMA > 30 days for 92 consecutive days**

---

## 📈 Tasks Completed

1. **Default Identification**  
   Classification of loans as defaulted or performing according to business rules.

2. **Default Rate Calculation**  
   Computation of observed default rate (DRₜ):
   \[
   DR_t = \frac{\text{Number of exposures that default within 12 months}}{\text{All exposures active at time } t}
   \]

3. **PD Modeling**  
   Segmentation of exposures into **risk groups** with assigned default probabilities over a 12-month horizon.


---

## 🧪 Technologies Used

- Python 3.x
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn`
- `xgboost` (optional for advanced modeling)
- `DecisionTreeRegressor`

---

## 📂 Project Structure

- `raport_3 (1).ipynb` – Data loading, default/cure logic, DR calculation, PDgroup modeling and visualizations



