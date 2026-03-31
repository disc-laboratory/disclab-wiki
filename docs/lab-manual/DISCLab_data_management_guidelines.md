# DISC Laboratory --- Data and Project Management Guidelines

This document defines the standard structure and rules for organizing research-related materials within the **Digital Intelligence for Structures and Construction (DISC) Laboratory**. The goal is to ensure consistency, reproducibility, traceability, and efficient collaboration across all projects and among all team members, including PhD students, postdoctoral researchers, undergraduate students, research staff, and collaborators.

## Purpose of this Document

This document provides the lab-wide guidelines for storing, managing, and documenting project information. It is intended to help all members of the group understand where files should be placed, how project materials should be organized, and what minimum documentation standards are expected.

These guidelines are meant to support good research practice. They do not replace university, sponsor, data protection, safety, ethics, or other institutional requirements. Where relevant, official NTU rules and project-specific conditions remain controlling.

## General Principles

### Project-centric organization

All research materials must be organized by **project**, not by individual person. Projects often continue even when students or staff leave the group, and multiple members may contribute to the same project over time. For this reason, all project data, code, reports, and outputs must remain within the corresponding project folder.

### Data integrity

Raw data is considered the original record of acquisition and must never be modified, overwritten, or deleted casually. Any cleaning, transformation, annotation, or reformatting must be carried out on copies of the data stored in the appropriate processed-data folders.

### Version control

All core code must be managed through the official GitHub organization of the laboratory. Local folders may contain clones of repositories, temporary scripts, or exploratory notebooks, but important code must not exist only on a local machine.

### Reproducibility

Experiments must be documented well enough that another group member can understand what was done, what data was used, what configuration was run, and how the outputs were generated.

### Controlled access

Where relevant, folder permissions should be used to protect sensitive or critical content. In particular, raw data folders should be treated as read-only after validation, and only authorized members should modify official project material.

## Global Lab Folder Structure

The overall lab storage should follow a structure similar to the one below:

```text
DISC_Lab/
|
|-- 00_Admin/
|-- 01_Lab_Manual/
|-- 02_Projects/
|-- 03_Publications/
|-- 04_Templates/
```

### Description of the top-level folders

#### `00_Admin/`

This folder contains administrative and operational documents related to the management of the lab.

Typical content includes:

- budgets and financial tracking;
- hiring and recruitment documents;
- meeting notes for lab or PI meetings;
- internal reports;
- grant tracking and administrative records.

This folder is intended for operational purposes only. Research data and project-specific technical materials should not be stored here.

#### `01_Lab_Manual/`

This folder contains the guidelines, standards, and procedures that define how research should be conducted and documented in the lab.

Typical content includes:

- data management guidelines;
- coding standards;
- experiment tracking guidelines;
- GitHub and version control workflows;
- onboarding instructions.

These documents define how work should be done in the lab. All lab members are expected to follow them. Project-specific files should not be stored here.

#### `02_Projects/`

This folder contains all active research projects in the lab. It is the core working area of the lab, and all research activities must be organized here by project rather than by person.

Each project must follow the standard structure:

```text
PROJ_XXX_ProjectName/
|-- 00_Admin/
|-- 01_Data/
|-- 02_Code/
|-- 03_Models/
|-- 04_Experiments/
|-- 05_Results/
|-- 06_Reports/
|-- 07_Presentations/
|-- 08_Documents/
|-- 09_Archive/
```

All work must be organized by project, not by individual. Members should follow the structure strictly and refer to the lab manual for more detailed procedural guidance.

#### `03_Publications/`

This folder contains all materials related to publications.

Typical content includes:

- journal papers;
- conference papers;
- submitted manuscripts;
- supplementary materials;
- figures and tables prepared for publications.

A suggested structure is:

```text
Paper_Name/
|-- manuscript/
|-- figures/
|-- tables/
|-- supplementary/
|-- submission/
```

Final versions should be clearly identified, and publication materials should remain consistent with the corresponding project results.

#### `04_Templates/`

This folder contains reusable templates for the lab.

Typical content includes:

- LaTeX templates for papers, reports, and CVs;
- presentation templates;
- report templates;
- code templates and utility scripts;
- experiment logging templates.

These files should be used as starting points. Members should create copies when needed rather than modifying the master templates directly.

## Mandatory Project Folder Structure

Every project must follow the same internal structure. A standard project folder should look like this:

```text
PROJ_XXX_ProjectName/
|
|-- 00_Admin/
|-- 01_Data/
|-- 02_Code/
|-- 03_Models/
|-- 04_Experiments/
|-- 05_Results/
|-- 06_Reports/
|-- 07_Presentations/
|-- 08_Documents/
|-- 09_Archive/
```

### Project naming convention

Each project folder should be named using the format:

`PROJ_XXX_ProjectName`

where `XXX` is a three-digit identifier and `ProjectName` is a short descriptive name written with underscores instead of spaces when needed.

Examples:

- `PROJ_001_XR_Bridge_Inspection`
- `PROJ_002_Heritage_Digitalization`
- `PROJ_003_Robotic_Assembly`

## Detailed Description of Each Project Folder

### `00_Admin/`

This folder stores project-specific administrative and management material.

Typical content includes:

- meeting notes;
- project timelines and milestone tracking;
- internal task assignments;
- communication summaries relevant to the project;
- staffing or role definitions specific to the project.

This folder should not be used to store research outputs, datasets, or technical code.

### `01_Data/`

This is one of the most important folders in the project. It contains all project-related datasets and associated metadata.

The recommended internal structure is:

```text
01_Data/
|-- 00_Raw/
|-- 01_Processed/
|-- 02_Annotations/
|-- 03_External/
|-- 04_Splits/
|-- README.md
```

#### `00_Raw/`

This folder contains original acquired data, such as images, videos, point clouds, LiDAR scans, sensor readings, or any other primary data source. Once uploaded and verified, this folder should be treated as read-only.

Rules:

- never modify raw files directly;
- never overwrite raw files with processed versions;
- never store edited files in the raw-data folder.

#### `01_Processed/`

This folder contains cleaned, transformed, converted, or otherwise processed versions of the raw data. Any scripts or notes that explain the processing pipeline should be linked clearly to these files.

#### `02_Annotations/`

This folder stores labels, masks, segmentation maps, bounding boxes, metadata tables, and exports from annotation tools. Annotation guidelines, class names, labeling conventions, and format definitions should also be documented here or in a dedicated README file.

#### `03_External/`

This folder contains public or externally sourced datasets used in the project. It should be clear what dataset was used, from where it was obtained, and under what version or release.

#### `04_Splits/`

This folder stores train, validation, and test splits, or other project-specific partitions of the data. These files are important for reproducibility and should be versioned where necessary.

#### README requirements for the data folder

The `README.md` within the data folder should describe, at minimum:

- the origin of the data;
- acquisition date or campaign;
- sensors or devices used;
- preprocessing steps;
- data format;
- naming conventions;
- known limitations or exclusions.

### `02_Code/`

This folder stores the coding material associated with the project. The recommended structure is:

```text
02_Code/
|-- main_repo/
|-- experiments/
|-- notebooks/
|-- README.md
```

#### `main_repo/`

This should contain a clone of the official project repository hosted in the DISC Lab GitHub organization. This is the main location for the active codebase.

#### `experiments/`

This folder may contain temporary scripts, local tests, or quick development material that is not yet mature enough to become part of the main repository. Useful scripts should eventually be cleaned and migrated into the main repository if they become part of the project workflow.

#### `notebooks/`

This folder is intended for Jupyter notebooks or other exploratory computational documents used for analysis, visualization, or quick prototyping.

#### Rules for the code folder

- important code must not be stored only locally;
- use meaningful commit messages in GitHub;
- document dependencies and environment setup;
- remove or archive obsolete scripts when they are no longer relevant.

### `03_Models/`

This folder is intended for machine learning or computational model artifacts. A recommended structure is:

```text
03_Models/
|-- checkpoints/
|-- final_models/
|-- configs/
|-- logs/
```

#### `checkpoints/`

Intermediate training states or periodic saved model states.

#### `final_models/`

Final selected models used for analysis, deployment, reporting, or publication.

#### `configs/`

Configuration files used for training, inference, evaluation, or deployment.

#### `logs/`

Training logs, run summaries, metric outputs, and related records.

#### Rules for the models folder

Every stored model should be traceable to:

- the dataset version used;
- the code version or commit;
- the configuration file used;
- the corresponding experiment folder if applicable.

### `04_Experiments/`

This folder is central to the scientific quality and traceability of the project. Every experiment should have its own folder.

Example:

```text
04_Experiments/
|-- EXP_001_initial_training/
    |-- config.yaml
    |-- notes.md
    |-- outputs/
```

Each experiment folder should include at least:

- a configuration file or parameter record;
- a short notes file explaining the objective of the experiment;
- a description of what changed with respect to previous runs;
- references to the dataset version and model version used;
- the outputs generated by that run.

Experiments should be named systematically, for example:

`EXP_001_initial_training`

### `05_Results/`

This folder stores the outputs that are used in papers, reports, presentations, or discussions.

A suggested structure is:

```text
05_Results/
|-- figures/
|-- tables/
|-- videos/
|-- qualitative/
```

Typical content includes:

- publication-ready figures;
- performance tables;
- visualization videos;
- qualitative comparisons and inspection outputs.

This folder should contain organized outputs, not temporary scratch files.

### `06_Reports/`

This folder stores written project outputs and internal reporting documents.

A suggested structure is:

```text
06_Reports/
|-- internal/
|-- milestones/
|-- thesis/
```

It may include:

- internal progress reports;
- sponsor deliverables;
- milestone summaries;
- thesis reports, drafts, or appendices when relevant.

### `07_Presentations/`

This folder stores all slides and presentation files associated with the project.

Examples include:

- group meeting presentations;
- progress review slides;
- conference presentations;
- defense presentations.

Files should be named clearly, for example `20260415_group_update.pdf`.

### `08_Documents/`

This folder stores formal non-report documentation associated with the project.

A suggested structure is:

```text
08_Documents/
|-- proposals/
|-- agreements/
|-- ethics/
```

Typical content includes:

- submitted proposals and proposal drafts;
- collaboration agreements or memoranda;
- ethics approvals or ethics-related submissions;
- formal documentation required by the institution or sponsor.

### `09_Archive/`

This folder stores deprecated, inactive, or superseded materials that should be retained for record purposes but should no longer be used as active working files.

Examples include:

- old report versions;
- outdated figures or tables;
- scripts replaced by newer workflows;
- unused supporting files from earlier phases of the project.

## Naming Conventions

Consistent naming is required to avoid confusion and improve searchability.

### Projects

Use:

`PROJ_XXX_ProjectName`

### Experiments

Use:

`EXP_XXX_Description`

### Dataset versions

Use clear version labels, for example:

- `dataset_v1`
- `dataset_v2`

### Files

Whenever appropriate, use date-first naming in the form:

`YYYYMMDD_description.ext`

This convention is recommended especially for reports, presentation files, and meeting-related documents.

## Responsibilities

### Principal Investigator

The PI is responsible for overseeing compliance with the general structure, defining permissions where needed, and ensuring that the overall project organization supports continuity, integrity, and accessibility.

### Researchers and students

All members of the lab are responsible for:

- following the folder structure consistently;
- documenting experiments and datasets properly;
- storing work in the appropriate project location;
- using version control for code;
- avoiding private or isolated storage of important project materials.

## GitHub Usage

All core code developed in the lab should be stored in the [DISC Lab GitHub organization](https://github.com/disc-laboratory).

Recommended practice includes:

- one repository per project, tool, or sufficiently independent codebase;
- no large raw datasets in GitHub;
- no unnecessary storage of large trained models in GitHub unless specifically justified;
- use of GitHub for version control, collaboration, issue tracking, and documentation.

## Final Notes

The quality of research outputs depends not only on the scientific ideas and technical work, but also on the clarity and discipline with which information is managed. A well-organized project structure reduces errors, facilitates continuity when group members change, and makes it much easier to reproduce results, prepare publications, and respond to sponsor or institutional requirements.

When in doubt, the default rule is simple: place files in the project folder, document what was done, avoid modifying raw data, and keep important code and experimental records traceable.

**Maintained by:** DISC Laboratory  
**Last updated:** March 27, 2026
