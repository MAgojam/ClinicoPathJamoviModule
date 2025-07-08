# ClinicoPath 0.0.3.46

## Major Infrastructure Improvements

### Enhanced Module Update System
- **Completely rewritten _updateModules.R** with enterprise-grade features
- **Smart asset copying**: Configuration-based vs legacy mode selection via `use_legacy_copying` option
- **Enhanced error handling**: Graceful degradation with comprehensive validation and recovery
- **Better logging**: Visual progress indicators with emojis and structured reporting
- **Module validation**: Pre-flight checks for all module directories and dependencies
- **Improved Git integration**: Enhanced commit handling with dry-run support and better error messages

### New Configuration Options
- **File copying control**: Granular control via `copy_vignettes`, `copy_data_files`, `copy_test_files`, `copy_r_files`
- **Smart path resolution**: Automatic fallback for missing dependencies and utility files
- **Enhanced backup system**: Automatic cleanup of old backups with configurable retention
- **Performance optimization**: Incremental updates and parallel processing support

### Function Enhancements

#### kappasizeci Function - Complete Overhaul
- **Enhanced implementation**: Added comprehensive parameter validation and error handling
- **Performance optimization**: Implemented caching system for repeated calculations
- **Comprehensive test suite**: 40+ test cases covering functionality, validation, edge cases, and real-world scenarios
- **Complete documentation**: 1,297-line comprehensive vignette with clinical examples and best practices
- **Test data generation**: 776-line script creating realistic datasets for 7 research domains (medical, radiological, psychological, etc.)

#### eurostatmap Function - Turkey Data Integration
- **Moved test files**: Relocated Turkey eurostatmap tests to proper testing infrastructure
- **Enhanced test structure**: Converted to proper testthat framework with comprehensive validation
- **Improved coverage**: Added data structure validation and statistical bounds checking

### Testing Infrastructure
- **Comprehensive test coverage**: Enhanced test suites for multiple functions
- **Proper test organization**: Moved standalone test files to appropriate testing directories
- **Better test structure**: Converted legacy tests to modern testthat framework
- **Real-world scenarios**: Added tests for clinical, medical, and research applications

### Developer Experience
- **Enhanced error messages**: Clear, actionable error messages with context
- **Better progress reporting**: Real-time feedback with completion summaries
- **Improved documentation**: Updated configuration files with comprehensive comments
- **Module status awareness**: Only processes enabled modules, skips disabled ones

### Code Quality
- **Consistent error handling**: Unified error handling patterns throughout
- **Enhanced validation**: Comprehensive input validation with helpful error messages
- **Better logging**: Structured logging with visual indicators and progress tracking
- **Robust operations**: Graceful handling of missing files and directories


# ClinicoPath 0.0.2.0072


calculated cut-off groups in continuous survival can be added to data


# ClinicoPath 0.0.2.0069

optional padjustement to pairwise survival fixes: https://github.com/sbalci/ClinicoPathJamoviModule/issues/38

saving calculated variables to Data


# ClinicoPath 0.0.2.0064

- added ggvenn function
fixed https://github.com/yanlinlin82/ggvenn/issues/16

- deleted some functions, will add as updated

# ClinicoPath 0.0.2.0048

- started adding arguments of ggstatsplot
fixed: https://github.com/sbalci/jjstatsplot/issues/3


# ClinicoPath 0.0.2.0046

-  use `x` and `y` instead of `main` and `condition` arguments for `ggpiestats` and `ggbarstats`  
partially fixed: https://github.com/sbalci/jjstatsplot/issues/1

-  add point.path argument in grouped_ggwithinstats
partially fixed: https://github.com/sbalci/jjstatsplot/issues/2

- waiting for update in jamovi mran version. current ggstatsplot dependencies are not up to date in jamovi's library



# ClinicoPath 0.0.2.0044

- fixed multivariate survival to work without continuous explanatory 


# ClinicoPath 0.0.2.0043

- added jsurvival to linux
- added some functions of descriptives to linux


# ClinicoPath 0.0.2.0041

- updated jsurvival
- added more controls under collapse boxes
- advanced outcome: users can select more than one outcome level depending on their analysis (event free or overall survival). Competing risk survival will also be added in the future.
- advanced survival: users can use dates to calculate survival time. the date type should be defined. many variations for date types are given.
- Cumulative events, cumulative survival and KMunicate style Kaplan-Meier curves are added.
- A separate function for continuous explanatory variable is added. The optimal cut-off based on survival outcome is defined and after cut-off definition other univariate survival analysis are performed.
- under multivariate analysis users can now generate Kaplan-Meier curves upto two explanatory variables.
- an adjusted survival curve is also added, though it requires further management.


# ClinicoPath 0.0.2.0040

- separating univariate continuous survival from categorical


# ClinicoPath 0.0.2.0039

- added options to vartree

fixes: https://github.com/sbalci/ClinicoPathJamoviModule/issues/28


# ClinicoPath 0.0.2.0038

- fixes https://github.com/sbalci/ClinicoPathJamoviModule/issues/20

# ClinicoPath 0.0.2.0037

- added Survival Analysis for Continuous Explanatory

- added vtree package functions to vartree function

- fixes https://github.com/sbalci/ClinicoPathJamoviModule/issues/9


# ClinicoPath 0.0.2.0036

- added Benford Analysis

- added interactive size to jjbarstats


```
.init = function() {
            deplen <- length(self$options$dep)
            self$results$plot$setSize(400, deplen*300)
        }
```


# ClinicoPath 0.0.2.0035

- meddecide has been added to jamovi library

https://github.com/sbalci/meddecide/

https://github.com/sbalci/meddecide/releases/

https://library.jamovi.org/win64/R3.6.3/meddecide-0.0.1.0005.jmo

https://library.jamovi.org/linux/R3.6.3/meddecide-0.0.1.0005.jmo

https://library.jamovi.org/macos/R3.6.3/meddecide-0.0.1.0005.jmo

# ClinicoPath 0.0.2.0034

- added metrics to survival functions
- updating survival options (continuous explanatory, cut-off, two categorical explanatory, multiple outcome options, elapsed time calculation from dates)
- added KMunicate type survival curve
- added Fagan's nomogram

# ClinicoPath 0.0.2.0027

- temporarily added many functions from various packages to update functions and arguments


# ClinicoPath 0.0.2.0026

- jsurvival has been added to jamovi library

https://github.com/sbalci/jsurvival

https://github.com/sbalci/jsurvival/releases/

https://library.jamovi.org/macos/R3.6.3/jsurvival-0.0.2.0026.jmo

https://library.jamovi.org/win64/R3.6.3/jsurvival-0.0.2.0026.jmo


# ClinicoPath 0.0.2.0025

- ClinicoPath as a combined module has been taken down from jamovi library.
- Users are adviced to install submodules.

- ClinicoPathDescriptives, jsurvival, and meddecide tables have been updated to look more jamovian :)





# ClinicoPath 0.0.2.0024

- ClinicoPathDescriptives functions are separately added to jamovi library under Exploration menu

ClinicoPathDescriptives module can be downloaded inside jamovi (click Modules and jamovi library)

https://library.jamovi.org/win64/R3.6.3/ClinicoPathDescriptives-0.0.2.0019.jmo

https://library.jamovi.org/linux/R3.6.3/ClinicoPathDescriptives-0.0.2.0019.jmo

https://library.jamovi.org/macos/R3.6.3/ClinicoPathDescriptives-0.0.2.0019.jmo



# ClinicoPath 0.0.2.0023

- added Age Pyramid

- survival status can be selected from levels

- WIP decisioncalculator



# ClinicoPath 0.0.2.0022

- GGStatsPlot functions are separately added to jamovi library under jjstatsplot menu

JJStastPlot module can be downloaded inside jamovi (click Modules and jamovi library)

https://library.jamovi.org/macos/R3.6.3/jjstatsplot-0.0.1.0001.jmo

https://library.jamovi.org/win64/R3.6.3/jjstatsplot-0.0.1.0001.jmo

https://library.jamovi.org/linux/R3.6.3/jjstatsplot-0.0.1.0001.jmo



# ClinicoPath 0.0.2.0021

- updating jjstatsplot for release



# ClinicoPath 0.0.2.0020

- made submodules:


- ClinicoPathDescriptives


https://github.com/sbalci/ClinicoPathDescriptives/

https://github.com/sbalci/ClinicoPathDescriptives/releases/


- JJStatsPlot: 


https://github.com/sbalci/jjstatsplot

https://github.com/sbalci/jjstatsplot/releases/


- jsurvival:

https://github.com/sbalci/jsurvival

https://github.com/sbalci/jsurvival/releases/


- meddecide

https://github.com/sbalci/meddecide/


https://github.com/sbalci/meddecide/releases/



# ClinicoPath 0.0.2.0019

- rewrote summary of categorical values to decrease dependencies




# ClinicoPath 0.0.2.0018

-   added cumulative events and cumulative hazard plots to survival

<https://rpkgs.datanovia.com/survminer/survminer_cheatsheet.pdf>

-   added cox adjusted survival to multivariate survival


# ClinicoPath 0.0.2.0017

-   added alluvial diagrams using easyalluvial package to Descriptives (under
    Explore menu)\
    <https://github.com/sbalci/ClinicoPathJamoviModule/issues/19>\
    <https://github.com/erblast/easyalluvial/issues/19>

-   added easyalluvial as an option to Graphs and Plots (under JJStatsPlot menu)
    for repeated categorical measurements.

# ClinicoPath 0.0.2.0016

-   See: <https://github.com/sbalci/jjstatsplot/releases/>

-   See: <https://github.com/sbalci/ClinicoPath/releases/>

-   crosstable function partially resolves
    <https://github.com/jamovi/jamovi/issues/443>

-   survival function resolves
    <https://github.com/jonathon-love/deathwatch/issues/2>

-   added export html to crosstables to bypass
    <https://github.com/jamovi/jamovi/issues/892>

# ClinicoPath 0.0.2.0015

-   Added tangram statistical results

-   Added options to finalfit crosstables fixes:
    <https://github.com/sbalci/ClinicoPathJamoviModule/issues/24> Partially
    fixes: <https://github.com/jamovi/jamovi/issues/901> fixes:
    <https://github.com/ewenharrison/finalfit/issues/52>

-   Added experimental biblometrics functions

-   includes experimental changes

# ClinicoPath 0.0.2.0014

-   Added footnote to arsenal crosstable

# ClinicoPath 0.0.2.0012

-   jjstatsplot is the wrapper functions for using ggstatsplot in jamovi.
-   I thought it might be a nice separate module too. I have prepared it to ask
    opinions.
-   Use attached `.jmo`files to install via side load in jamovi.
-   Requires latest jamovi \>=1.2.22 <https://www.jamovi.org/download.html>
-   tangram error is fixed, but it does not reveal statistical test results.
-   arsenal's footnote is not visible in Html output

# ClinicoPath 0.0.2.0004

Using `spgarbet/tangram@0.3.2` until the bug is fixed.

# ClinicoPath 0.0.2.0003

Added arsenal, finalfit, and gtsummary to crosstable function. gtsummary gives
different results, due to nonparametric tests. Should add options and
documentation. tangram still not functioning.

# ClinicoPath 0.0.2

-   version 0.0.2 is released
-   works with jamovi latest release (\>=1.2.18)
    <https://www.jamovi.org/download.html>

![](man/figures/jamovi-ClinicoPath-0.0.2-released.gif){align="center"
width="75%"}

-   The new version of \#ClinicoPath [@jamovistats] module is on the jamovi
    library. Requires \#jamovi 1.2.18 \#rstats \#biostatistics \#pathology
    \#pathologists

<https://twitter.com/serdarbalci/status/1261256107919642629>

-   \#ClinicoPath \#jamovi module comes with example datasets as with other
    \#jamovi modules. Use them as example to prepare your data.

<https://twitter.com/serdarbalci/status/1261639212664840192>

-   You can easily make 'Table One' for reports/manuscripts via \#ClinicoPath
    [@jamovistats] module. Uses \#tableone, \#arsenal, \#gtsummary, and
    \#janitor packages. \#rstats \#biostatistics \#pathology \#pathologists

<https://twitter.com/serdarbalci/status/1262083972328230912>

-   \#jamovi has very nice tables. Sometimes I prefer to read the tables
    automatically via \#ClinicoPath [@jamovistats] module. Using \#easystats
    \#report package. \#naturallanguage \#data \#summary \#rstats
    \#biostatistics \#pathology \#pathologists

<https://twitter.com/serdarbalci/status/1262354990787694599>

-   With \#ClinicoPath [@jamovistats] module it is easy to make crosstables.
    uses \#tangram package \#rstats \#biostatistics \#pathology \#pathologists

<https://twitter.com/serdarbalci/status/1262691784574017536>

-   You can make different plots based on variable type via \#jamovi
    \#ClinicoPath module. Using \#rstats [@jamovistats] \#ggstatsplot
    \#ggalluvial \#easyalluvial packages \#pathology \#pathologists
    \#datavisualisation

<https://www.youtube.com/watch?v=m3uInetiC8w>

<https://twitter.com/serdarbalci/status/1263191858454413312>

-   Some examples of survival analysis via [@jamovistats] \#ClinicoPath module.
    Using \#rstats \#finalfit by [@ewenharrison] \#survival \#survminer
    \#ggstatsplot in \#jamovi \#biostatistics \#pathology \#pathologists
    <https://www.youtube.com/watch?v=gIPf4xIKAOU>

<https://www.linkedin.com/pulse/survival-analysis-via-jamovi-clinicopath-module-serdar-balc%25C4%25B1>
\#datavisualisation \#datascience \#patoloji \#analysis \#datascientist \#data
\#clinicaltrials \#clinicalstudies \#clinicaltrial \#clinicalresearch

<https://twitter.com/serdarbalci/status/1264153665386004480>

It is generating natural language summaries to make easy to read the tables:
"Median Survival: When LVI is Absent, median survival is 26 [20.1 - 32.3,"95%
CI] months. When LVI is Present, median survival is 9.3 [8.8 - 10.6, 95% CI]
months."

<https://twitter.com/serdarbalci/status/1264153686508478465>

"Hazard: When LVI is Present, there is 2.55 (1.85-3.51, p\<0.001) times risk
than when LVI is Absent."

<https://twitter.com/serdarbalci/status/1264153695715053568>

"1, 3, 5-yr Survival: When LVI Absent, 12 month survival is 70.9% [63.36%-79.3%,
95% CI]. When LVI Absent, 24 month survival is 54.2% [45.85%-64.1%, When LVI
Present, 12 month survival is 28.4% [20.03%-40.3%, 95% CI]. When LVI Present, 24
month survival is 14.4% ..."

<https://twitter.com/serdarbalci/status/1264153698764312577>

"pairwise comparison of Grade: The comparison between Grade 2 and Grade 1 has a
p-value of 0.87." Note for myself: The wording should be better.

<https://twitter.com/serdarbalci/status/1264153700114862080>

You can do multivariate survival analysis

<https://twitter.com/serdarbalci/status/1264153711087140864>

And also make Odds Ratio Tables and Plots. When you change the order of
variables in jamovi data, the analysis also changes.

<https://twitter.com/serdarbalci/status/1264153752015122432>

<https://github.com/sbalci/ClinicoPathJamoviModule>

<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLxRBOaoEoP4JfAMi7aIbkRXPXGUEwzTNv" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>

</iframe>

# ClinicoPath 0.0.1.0001

Added multivariate survival, and comparison plots.

# ClinicoPath v0.0.1

A jamovi module that contains main analysis used in clinicopathological
research. ClinicoPath help researchers to generate natural language summaries of
their dataset, generate cross tables with statistical tests, and survival
analysis with survival tables, survival curves, and natural language summaries.

You may install using side load: windows:
<https://library.jamovi.org/win64/R3.6.1/ClinicoPath-0.0.1.jmo> macOS:
<https://library.jamovi.org/macos/R3.6.1/ClinicoPath-0.0.1.jmo>

<https://github.com/sbalci/ClinicoPathJamoviModule>

<https://github.com/sbalci/ClinicoPathJamoviModule/releases/tag/v0.0.1>

# ClinicoPath 0.0.1.1001

-   removed 'frequencies'
-   Documentations are being added.
-   CI are being added.
-   Badges, README are updated.

# ClinicoPath 0.0.1.1000

## Functions work as defaults

-   Divided module into 2 windows: ClinicoPath1 and ClinicoPath2
-   Removed unnecessary outputs.
-   Added ToDo section and a warning that still in development
-   Updated Readme file
-   Currently functions are working. But only in defaults.

### For descriptive analysis:

-   TableOne
-   WriteSummary
-   Report General Features
-   Frequencies

### For comparing variables:

-   CrossTable
-   GGStatsPlot2

### For survival analysis

-   FinalFit
-   FinalFit Multivariate Survival

### For medical decision tests:

-   Medical Decision
-   Decision Calculator

### For correlation analysis:

-   Correlation

### For inter and intra observer agreement

-   Interrater Intrarater Reliability

### Decision tree and cluster analysis sections.

-   Not active yet.

# ClinicoPath 0.0.1-beta

-   First Pre-release

-   <https://github.com/sbalci/ClinicoPathJamoviModule/releases/tag/0.0.1-beta>
