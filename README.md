## SET 1 - MAKEMORE (PART 1) 🔗

[![Documentation](https://img.shields.io/badge/Documentation-Available-blue)](https://muzzammilshah.github.io/Road-to-GPT/Makemore-part1/)
![Number of Commits](https://img.shields.io/github/commit-activity/m/MuzzammilShah/NeuralNetworks-LanguageModels-1?label=Commits)
[![Last Commit](https://img.shields.io/github/last-commit/MuzzammilShah/NeuralNetworks-LanguageModels-1.svg?style=flat)](https://github.com/MuzzammilShah/NeuralNetworks-LanguageModels-1/commits/main)  
![Project Status](https://img.shields.io/badge/Status-Done-success)

&nbsp;

### **Overview**
Introduced to the concept of a bigram character-level language model, this repository explores its **training**, **sampling**, and **evaluation** processes. The model evaluation was conducted using the **Negative Log Likelihood (NLL)** loss to assess its quality.

The model was trained in two distinct ways, both yielding identical results:

1. **Frequency-Based Approach**: Directly counting and normalizing bigram frequencies.
2. **Gradient-Based Optimization**: Optimizing the counts matrix using a gradient-based framework guided by minimizing the NLL loss.

This demonstrated that **both methods converge to the same result**, showcasing their equivalence in achieving the desired outcome.

&nbsp;

### **🗂️Repository Structure**

```plaintext
├── .gitignore
├── A-Main-Notebook.ipynb
├── B-Main-Notebook.ipynb
├── C-Main-Notebook.ipynb
├── README.md
├── notes/
│   ├── A-main-makemore-part1.md
│   ├── B-main-makemore-part1.md
│   ├── C-main-makemore-part1.md
│   └── README.md
└── names.txt
```

- **Notes Directory**: Contains detailed notes corresponding to each notebook section.
- **Jupyter Notebooks**: Step-by-step implementation and exploration of the bigram model.
- **README.md**: Overview and guide for this repository.
- **names.txt**: Supplementary data file used in training the model.

&nbsp;

### **📄Instructions**

To get the best understanding:

1. Start by reading the notes in the `notes/` directory. Each section corresponds to a notebook for step-by-step explanations.
2. Open the corresponding Jupyter Notebook (e.g., `A-Main-Notebook.ipynb` for `A-main-makemore-part1.md`).
3. Follow the code and comments for a deeper dive into the implementation details.

&nbsp;

### **⭐Documentation**

For a better reading experience and detailed notes, visit my **[Road to GPT Documentation Site](https://muzzammilshah.github.io/Road-to-GPT/)**. 

> **💡Pro Tip**: This site provides an interactive and visually rich explanation of the notes and code. It is highly recommended you view this project from there.

&nbsp;


### **✍🏻Acknowledgments**
Notes and implementations inspired by the **Makemore - Part 1** video by [Andrej Karpathy](https://karpathy.ai/).  

For more of my projects, visit my [Portfolio Site](https://muhammedshah.com).
