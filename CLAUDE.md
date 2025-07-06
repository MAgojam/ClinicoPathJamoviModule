# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Package Overview

ClinicoPath is a comprehensive jamovi module for clinicopathological research analysis. It provides statistical analysis tools specifically designed for pathology and clinical research, including survival analysis, decision analysis, descriptive statistics, and specialized plots. The project serves as an umbrella package that coordinates multiple sub-modules distributed across separate repositories.

## Core Architecture

### Jamovi Module Structure

This is a jamovi R module with a specific 4-file architecture pattern that must be followed for all analyses:

- **`.b.R` files**: Backend implementation classes (e.g., `crosstable.b.R`, `survival.b.R`, `decisiongraph.b.R`)
- **`.a.yaml` files**: Analysis definitions with options/parameters (e.g., `crosstable.a.yaml`)
- **`.u.yaml` files**: User interface definitions (e.g., `crosstable.u.yaml`)
- **`.r.yaml` files**: Results/output definitions (e.g., `crosstable.r.yaml`)
- **`.h.R` files**: Auto-generated header files (compiled from .yaml files)

### Key Backend Pattern

All analysis classes inherit from auto-generated base classes and use R6 class system:

```r
crosstableClass <- R6::R6Class(
    "crosstableClass", 
    inherit = crosstableBase,  # Auto-generated from .yaml files
    private = list(
        .init = function() { ... },
        .run = function() { ... }
    )
)
```

### Main Functional Areas

1. **ClinicoPath Descriptives**: Summary statistics, Table One, cross tables, data checking
2. **ClinicoPath Survival**: Survival analysis, Cox regression, Kaplan-Meier, competing risks
3. **meddecide**: Medical decision analysis, ROC curves, sensitivity/specificity, diagnostic tests, decision trees with Markov chain modeling
4. **JJStatsPlot**: Statistical plots using ggstatsplot wrappers
5. **Patient Follow-Up Plots**: Swimmer plots, waterfall plots, treatment response visualization

### Advanced Decision Analysis Architecture

The `decisiongraph` module supports both traditional decision trees and advanced Markov chain models:

**Decision Trees**: One-time decisions with immediate outcomes

- Acute medical conditions (surgery vs. conservative treatment)
- Emergency decisions with clear cost/utility trade-offs
- Point-in-time cost-effectiveness analysis

**Markov Chain Models**: Long-term disease progression modeling

- Chronic disease management with multiple health states
- Transition probability matrices for state changes over time
- Cohort trace analysis with discounted cost-effectiveness calculations
- Multi-cycle analysis for lifetime economic evaluations

The module automatically handles different analysis types based on `treeType` option (`simple`, `costeffectiveness`, `markov`).

## Namespace and Package Configuration

### Package Namespace Analysis

Current Situation: ✅ The configuration is actually CORRECT

Your package namespace is properly configured as ClinicoPath. Here's the evidence:

✅ Correct Configuration:

1. DESCRIPTION file (line 2): Package: ClinicoPath
2. jamovi 0000.yaml (line 3): name: ClinicoPath
3. jamovi 0000.yaml (line 18): ns: ClinicoPath (namespace)
4. NAMESPACE file: Contains proper exports with ClinicoPath functions
5. All function exports: Use ClinicoPath namespace consistently

📁 Repository vs Package Name:

- Repository/Folder: ClinicoPathJamoviModule
- Package Name: ClinicoPath ✅

This is completely normal and acceptable. Many R packages have descriptive repository names that differ from the package name.

🔍 Why "ClinicoPathJamoviModule" Sometimes Appears:

Installation scenarios where this occurs:

1. Local Development Installation:
devtools::install()  # Uses folder name if in root directory
2. GitHub Installation with Full Repo Name:
devtools::install_github("user/ClinicoPathJamoviModule")
3. Manual Installation from Source: Using folder name

✅ Correct Installation Methods:

To ensure "ClinicoPath" namespace is used:

1. From CRAN (future):
install.packages("ClinicoPath")
2. From GitHub with Package Name:
devtools::install_github("user/ClinicoPathJamoviModule",
                         subdir = ".",
                         build_vignettes = FALSE)
3. Development Installation:
# From package root directory
devtools::install(pkg = ".", quick = TRUE)

🚀 Recommendations:

Your current setup is correct! However, to avoid confusion:

1. Documentation: Always refer to the package as "ClinicoPath" in:
  - README files
  - Documentation
  - Installation instructions
  - User guides
2. Installation Instructions: Provide clear installation commands:
# Correct installation
devtools::install_github("sbalci/ClinicoPathJamoviModule")
library(ClinicoPath)  # Always loads as ClinicoPath
3. Repository Description: Update GitHub repository description to clarify:
"ClinicoPath R Package - Analysis for Clinicopathological Research"

📋 Summary:

- ✅ Package namespace is correctly configured as "ClinicoPath"
- ✅ All jamovi analyses use ns: ClinicoPath
- ✅ DESCRIPTION and NAMESPACE files are correct
- 📁 Repository name ClinicoPathJamoviModule is just the container name
- 🎯 Users should always library(ClinicoPath) regardless of installation method

The confusion comes from folder/repository naming vs package naming, which is a common and acceptable practice in R package development.

[... rest of the existing file content remains unchanged ...]