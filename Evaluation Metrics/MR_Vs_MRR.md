# Mean Rank (MR) vs. Mean Reciprocal Rank (MRR)

**Mean Rank (MR)** and **Mean Reciprocal Rank (MRR)** are metrics used to evaluate ranking systems, focusing on different aspects of search performance. MR measures the average position of the first relevant result (lower is better), while MRR averages the inverse of that position (higher is better). MRR highlights top-1 accuracy, while MR treats rank differences equally.

---

### Key Differences and Characteristics

#### Mean Rank (MR)
*   **Definition:** The arithmetic mean of the positions of the first relevant item across all queries:  
    $$MR = \frac{1}{Q} \sum_{i=1}^{Q} rank_i$$
*   **Lower is Better:** A lower rank means the first relevant item appears higher.
*   **Sensitivity:** It treats improvements at the top of the list (e.g., from rank 5 to 1) the same as improvements further down (e.g., from rank 50 to 46).
*   **Range:** $[1, \infty)$

#### Mean Reciprocal Rank (MRR)
*   **Definition:** The mean of the reciprocals of the ranks of the first relevant item:  
    $$MRR = \frac{1}{Q} \sum_{i=1}^{Q} \frac{1}{rank_i}$$
*   **Higher is Better:** A higher score (closer to 1) means the first relevant item appears near the top.
*   **Sensitivity:** It heavily favors results where the first relevant item is ranked very high (e.g., rank 1, 2, or 3).
*   **Range:** $(0, 1]$

---

### Comparison Table


| Feature | Mean Rank (MR) | Mean Reciprocal Rank (MRR) |
| :--- | :--- | :--- |
| **Focus** | Average position | Inverse position |
| **Best Value** | 1 | 1 |
| **Sensitivity** | Linear sensitivity to rank | High sensitivity to top positions |
| **Range** | $[1, \infty)$ | $(0, 1]$ |
| **Use Case** | General ranking quality | Lookups, QA, chatbots |

---

### When to Use Which
*   **Use MRR:** When user satisfaction depends heavily on the very first result (e.g., voice assistants, Q&A systems, or "known-item" searches).
*   **Use MR:** When looking for a general indicator of how far down the list the user needs to go to find the first result, often used in knowledge graph embedding evaluation.
*   **Limitations:** Both metrics only consider the **first** relevant result and ignore other relevant items in the list.
