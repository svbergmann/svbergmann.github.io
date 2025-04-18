# svbergmann.github.io

This repository hosts the source code for my personal resume website, available at [https://svbergmann.github.io](https://svbergmann.github.io). 
It utilizes GitHub Pages for hosting and employs a combination of technologies to generate both,
a web version and a PDF version of my resume from a single source of truth.

## How it Works

The core data for the resume is maintained in two primary formats:

1. **LaTeX Files:** Using the [`moderncv` class](https://ctan.org/pkg/moderncv) with the `classic` theme and `blue` color scheme, 
    several `.tex` files (`cv.tex`, `career.tex`, `education.tex`, `skills.tex`, etc.) define the structure and content for a formal CV. 
    This allows for the generation of a high-quality PDF version, including embedded certificates. 
    The LaTeX setup also includes translation logic to support both German and English versions.
2. **JSON Resume:** A `resume.json` file adheres to the [JSON Resume schema](https://jsonresume.org/schema/). 
    This standardized JSON format serves as the data source for generating the web version of the resume.

GitHub Actions are used to automatically:

* Compile the LaTeX files into PDF documents (in German and English).
* Build the web version using the `resume.json` data and the specified theme.
* Deploy the generated website and PDFs to GitHub Pages.

## Technologies Used

* **LaTeX:** For generating the PDF version of the CV.
    * **moderncv:** LaTeX class for modern CVs.
* **JSON Resume:** A community-driven open-source initiative to create a standard JSON-based format for resumes.
    * **Schema:** [JSON Resume Schema v1.0.0](https://raw.githubusercontent.com/jsonresume/resume-schema/v1.0.0/schema.json)
    * **Theme:** [kendall](https://github.com/jsonresume/theme-kendall) (as specified in `resume.json`)
* **GitHub Pages:** For hosting the static website.
* **GitHub Actions:** For automating the build and deployment process.

## TODOs

* Add more clarity to the README.md file
* Update resume.json
* Use a tool (maybe pandoc) to also generate the latex cv based on the data provided inside the resume.json file.
