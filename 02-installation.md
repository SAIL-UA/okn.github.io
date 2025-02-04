---
layout: default
title: "Installation"
nav_order: 2
---

# Installation

## Prerequisites

Before installing LEAP, ensure you have the following dependencies installed:

- Python 3.6 or later
- pip (Python package manager)
- Git (for cloning the repository)

## Clone the Repository

To get started, clone the LEAP repository from GitHub:

```bash
git clone https://github.com/SAIL-UA/LEAP.git
cd LEAP
```

## Install Dependencies

LEAP requires several Python libraries. Install them using the following command:

```bash
pip install -r requirements.txt
```

If you plan to contribute to the project, install the development dependencies as well:

```bash
pip install -r dev-requirements.txt
```

## Verify Installation

To ensure that LEAP is installed correctly, run the following command:

```bash
python -c "import leap; print('LEAP installed successfully')"
```

If you see the message `LEAP installed successfully`, the installation was successful.

## Optional: Virtual Environment

For better dependency management, consider using a virtual environment:

```bash
python -m venv leap-env
source leap-env/bin/activate  # On Windows use: leap-env\Scripts\activate
pip install -r requirements.txt
```

## Next Steps

After installation, proceed to the [Data Load](data-load.md) section to learn how to load sensor data.
