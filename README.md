# ⚙️ SWARA-SAW Implementation: Elective Course Selection DSS

This project implements a **Multi-Criteria Decision Making (MCDM)** solution using a hybrid **SWARA (Step-wise Weight Assessment Ratio Analysis)** and **SAW (Simple Additive Weighting)** method to determine the optimal elective course among several alternatives.

The specific case study is the selection of an elective course for the 5th semester in the Faculty of Computer Science/Informatics.

## 🎯 Project Goal

To objectively rank 6 alternative elective courses based on 5 decision criteria, where the criteria weights are calculated using the SWARA method, and the final ranking is determined by the SAW method.

## 🧠 Methodology: Hybrid SWARA-SAW

1.  **SWARA (Weight Determination):**
    - Criteria are ranked based on their perceived importance (using the 'tj' average value) and assigned a comparative weight ($S_j$).
    - This method generates objective final weights ($W_j$) that reflect the hierarchical importance of the criteria.
2.  **SAW (Ranking):**
    - The initial decision matrix ($X$) is normalized ($R$) by comparing the criteria values against the maximum/minimum ideal values (depending on whether the criterion is Benefit or Cost).
    - The final preference value ($V_i$) for each alternative is calculated by summing the product of the normalized value and the SWARA weight ($V_i = \sum W_j \times r_{ij}$).

## 📊 Data & Criteria

### Alternatives (Courses)

There are 6 elective course alternatives evaluated:

- Machine Learning (Pembelajaran Mesin)
- Data Science
- Pattern Recognition (Pengenalan Pola)
- Database Management (Manajemen Basis Data)
- Computer Network Security (Keamanan Jaringan Komputer)
- Animation and Multimedia (Animasi dan Multimedia)

### Decision Criteria

The 5 criteria are sorted and weighted based on the SWARA calculation:

| Code | Criterion (English Translation)   | Type     | SWARA Weight ($W_j$) |
| :--- | :-------------------------------- | :------- | :------------------- |
| C4   | Relevance to Industry/Job Market  | Benefit  | 0.2879               |
| C2   | Area of Interest / Specialization | Benefit  | 0.2399               |
| C1   | Academic Prerequisites            | **Cost** | 0.1846               |
| C3   | Curriculum Continuity             | Benefit  | 0.1678               |
| C5   | Material Difficulty Level         | **Cost** | 0.1198               |

## 🏆 Final Ranking Results

The final ranked list based on the calculated preference values ($V_i$) is:

| Rank | Alternative                                            | Preference Value ($V_i$) |
| :--- | :----------------------------------------------------- | :----------------------- |
| 1    | **Machine Learning** (Pembelajaran Mesin)              | 0.7897                   |
| 2    | Database Management (Manajemen Basis Data)             | 0.7542                   |
| 3    | Computer Network Security (Keamanan Jaringan Komputer) | 0.7459                   |
| 4    | Data Science                                           | 0.7355                   |
| 5    | Animation and Multimedia (Animasi dan Multimedia)      | 0.7218                   |
| 6    | Pattern Recognition (Pengenalan Pola)                  | 0.6490                   |

**Conclusion:** The recommended elective course is **Machine Learning**.

## 📁 Project Structure

```bash
Swara-Implementation/
└── swara.ipynb             # Jupyter Notebook containing all steps: Data Initialization, SWARA calculation for weights, SAW normalization, and final ranking.
```
