
# 🎓 Making Volcano Plots Speak: Custom Gene Labeling in Python

**Author:** Kelly Hamisi  
**Learning Platform:** Stanford Data Ocean – Precision Medicine Program  
**Tool:** Python + Bioinfokit  
**Project Theme:** Visualizing differential gene expression with precision and clarity

---

## 🔍 Why Customize Volcano Plots?

In bioinformatics, volcano plots are powerful tools for visualizing thousands of gene expression changes between two conditions — often **treatment vs. control**.

By plotting:
- 📈 **log₂ Fold Change (x-axis)** → how much a gene increases or decreases
- 📉 **−log₁₀(p-value) (y-axis)** → how confident we are that the change is real

We can quickly spot which genes are significantly **upregulated** or **downregulated**.

But one challenge remains:  
> 🧬 “How do I make this data **readable and meaningful** to others?”

---

## 🛠️ What I Built

I didn’t stop at setting statistical thresholds — I went further by labeling **specific genes** with **short, clear names** instead of long IDs.

### 🧬 Gene Name Mapping:

| Raw Gene ID             | Custom Label |
|-------------------------|--------------|
| LOC_Os09g01000.1        | EP           |
| LOC_Os01g50030.1        | CPuORF25     |
| LOC_Os06g40940.3        | GDH          |
| LOC_Os03g03720.1        | G3PD         |

---

## 🧠 Why This Matters

- ✅ Simplifies communication with collaborators  
- ✅ Makes plots clean for presentations or reports  
- ✅ Helps focus on **biologically meaningful hits**

---

## 💻 Python Code

```python
from bioinfokit import visuz

visuz.GeneExpression.volcano(df=df,
    lfc='log2FC',
    pv='p-value',
    lfc_thr=(2, 1),
    pv_thr=(0.01, 0.05),
    color=("#A31746", "lightgrey", "#FF9595"),
    show=True,
    plotlegend=True,
    legendpos='upper right',
    sign_line=True,
    legendanchor=(1.46,1),
    genenames={
        "LOC_Os09g01000.1": "EP",
        "LOC_Os01g50030.1": "CPuORF25",
        "LOC_Os06g40940.3": "GDH",
        "LOC_Os03g03720.1": "G3PD"
    },
    gstyle=2,
    geneid="GeneNames")
```

---

## 📊 The Result

![Volcano Plot](Add%20G2%20Names.png)

This volcano plot doesn’t just show trends — it tells a story.  
Labeled. Filtered. Personalized.

---

## 🧭 Takeaway

In bioinformatics, **how you visualize results** can be as powerful as the results themselves.

This plot was about more than graphics — it was about **owning the narrative**.

---

## 🚀 What’s Next?

- Labeling **all genes**  
- Exporting publication-ready figures  
- Comparing multiple conditions in one plot

> 🧠 “Every plot is a story. Every badge is a milestone.”  
> — Kelly Hamisi, #TheMaguyaMatrix
