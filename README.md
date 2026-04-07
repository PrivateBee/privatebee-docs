# Private Bee – GPS 4D Navigation System 🐝

## Project Description

GPS 4D is an innovative navigation system designed for **drones**, **air taxis**, and more generally for **next-generation aircraft** used in urban air mobility.

Unlike traditional navigation systems that rely on three-dimensional positioning (latitude, longitude, altitude), GPS 4D introduces a fourth essential dimension: **time**.

The objective of this project is to design a system capable of **planning**, **optimizing**, and **monitoring** aerial trajectories while simultaneously considering:

- **airspace geometry**,
- **regulatory constraints**,
- **real-time weather conditions**,
- **movements of other aircraft**,
- and **the urgency level of the mission**.

The system computes the **optimal trajectory** not only in **space** but also in **time**, in order to ensure **safer**, **faster**, and **more efficient** flights. It is also designed to dynamically adapt to **unexpected events** such as potential collisions, weather changes, restricted airspaces, or emergency situations.

---

## Repository Purpose

This repository provides **documentation** on how to **contribute** to the **Private Bee project**, including information about the **GitHub workflow**, **coding conventions**, and **templates** to streamline your work.

---

## Repository Structure

```
privatebee-docs/
├── CODE_OF_CONDUCT.md                 -> Expected behavior guidelines
├── CONTRIBUTING.md                    -> Guidelines for contributing
├── CONVENTIONS.md                     -> Coding standards and conventions
├── GIT-GITHUB-WORKFLOW-TUTORIAL.md    -> Git and GitHub workflow guide
├── GITIGNORE-TUTORIAL.md              -> Guide on using .gitignore effectively
├── GOVERNANCE.md                      -> Project governance structure
├── LICENSE.md                         -> Project license
├── README.md                          -> Project overview and documentation
├── Guide utilisation, Gestion et Workflow GitHub.pdf -> Guide for using GitHub and managing the project
├── Guide utilisation Discord.pdf      -> Guide for using Discord for communication
├── fiches_qualite_code/               -> Code quality checklists and guidelines
│   ├── Cheat_Sheet.pdf				   -> Cheat sheet for code quality with name conventions, commandes, etc.
│   ├── Fiche_Qualite_Code_C.pdf	   -> Code quality checklist for C code
│   ├── Fiche_Qualite_Code_CPP.pdf	   -> Code quality checklist for C++ code
│   ├── Fiche_Qualite_Code_JAVA.pdf	   -> Code quality checklist for Java code
│   └── Fiche_Qualite_Code_PYTHON.pdf  -> Code quality checklist for Python code 
└── .github/
	├── PULL_REQUEST_TEMPLATE.md       -> Generic pull request template
	└── ISSUE_TEMPLATE/                -> Issue templates
		├── bug-report.yml             -> Bug report template
		├── config.yml                 -> Issue template configuration
		└── new-feature.yml            -> Feature request template
```

---

## Getting Started

Before contributing, please read:
- [Guide utilisation, Gestion et Workflow GitHub.pdf](./Guide%20utilisation,%20Gestion%20et%20Workflow%20GitHub.pdf)
- [Guide utilisation Discord.pdf](./Guide%20utilisation%20Discord.pdf)
- [CONTRIBUTING.md](./CONTRIBUTING.md)
- [GOVERNANCE.md](./GOVERNANCE.md)

Please also refer to the quality code files in the [fiches_qualite_code](./fiches_qualite_code/) directory to ensure that your contributions meet the project's quality standards.

---

## Prerequisites

There are **no prerequisites** for this repository since it only contains **documentation**.

For other repositories, refer to their **README** for prerequisites.

---

## Conventions

The **coding conventions** for this project are described in [CONVENTIONS.md](./CONVENTIONS.md). Please **read them before starting** to work on the project.

---

## Git & GitHub Workflow Tutorial

To learn everything about using Git, GitHub, and the workflow you need to follow, please refer to the [GIT-GITHUB-WORKFLOW-TUTORIAL](./GIT-GITHUB-WORKFLOW-TUTORIAL.md) file.

For a focused guide on `.gitignore`, see [GITIGNORE-TUTORIAL.md](./GITIGNORE-TUTORIAL.md).

---

## Templates

### Pull Request and Issue Templates

In the [.github](.github/) directory, you can find **templates for pull requests and issues**. These templates **streamline your workflow** and **save you time**.

You can **modify the pull request template** as needed to adapt it to your project.

For issue templates, you can **add new ones** by creating a new **.yml file** following the structure from existing template files. This way, you can create issue templates for any type of issue you need.

---

### Repository Template

#### Purpose 

The [privatebee-template](https://github.com/PrivateBee/privatebee-template) repository serves as a **template for creating new repositories**. 

This template provides **essential files** that should be in every repository, such as the **license**, **governance documents**, **code of conduct**, and more.

It also includes a **README file** with **predefined sections** that you can complete based on your specific project needs.

---

#### Using the Repository Template

To use the repository template, click on the **New repository** button in the **repositories tab** of the project, and in the **configuration section**, select **privatebee-template**.

---

## Compilation / Build

This repository contains **documentation only**, so there is nothing to build here.

For other projects, refer to each project's **README** for build instructions.

---

## Installation

This repository contains **documentation only**, so there is nothing to install here.

For other projects, refer to each project's **README** for installation steps.

---

<!-- ## Project Status / Progress -->

<!-- TODO: voir ce qu'on en fait : le garder et le mettre à jour ? ou juste enlever ? -->

<!-- | Task                                             |   Status   |
| ------------------------------------------------ | :--------: |
| Needs analysis and project understanding         | [Completed] |
| State-of-the-art study (GNSS, weather, U-space)  | [Completed] |
| Definition of core functionalities               | [Completed] |
| Data modeling (Conceptual + Physical models)     | [Completed] |
| Software architecture selection                  | [Completed] |
| Environment setup (server, libraries)            | [Completed] |
| 3D visualization prototype (Cesium / Blender)   | [Completed] |
| Import and visualization of 3D models            | [Completed] |
| France modeling / airspace zones                 | [In Progress] |
| Weather integration (API)                        | [In Progress] |
| 4D visualization (time + animation)              | [In Progress] |
| Real-time communication (WebSocket)              | [In Progress] |
| Drone / VTOL flight simulation                   | [In Progress] |
| User interface (controls, visualization)         | [In Progress] |
| Crash scenario and impact zone detection         | [In Progress] |
| Intermediate testing and technical validation    | [In Progress] |
| Final integration (all modules connected)        | [To Do] |
| Full simulation of a real 4D trajectory          | [To Do] |
| Final demonstration and scenario design          | [To Do] |
| UI/UX optimization and 3D fluidity               | [To Do] |
| Final CY Tech report writing                     | [To Do] |
| Demonstration video creation                     | [To Do] |

--- -->

<!-- ## Team and Roles (2025-2026) -->

<!-- TODO: à voir si on garde, il faudrait vérifier les rôles de chaque école -->

<!-- | Institution                                     | Role |
| ----------------------------------------------- | :--: |
| Technoplane SAS                                 | [ Project Director ] |
| CY Tech, INEM                                   | [ Project Management ] |
| CY Tech, Visual Computing                       | [ ] |
| ENSTA Paris                                     | [ ] |
| ESTACA                                          | [ ] |
| INSA Toulouse                                   | [ ] |

--- -->

## License

This project is licensed under the terms described in the [LICENSE](./LICENSE.md) file.

---

## Support and Contact

If you have any questions or remarks about this repository, please **open an issue** in this repository or contact the **project maintainers via Discord**.

---
