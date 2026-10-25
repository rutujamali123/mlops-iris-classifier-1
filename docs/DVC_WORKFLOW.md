# DVC Workflow

## Remote Configuration

The project uses a local DVC remote named `myremote`.

The DVC remote is configured as:

`C:/Users/SARTHAK/dvc-remote-storage`

## DVC Data Versioning Workflow

For every data change, the following workflow is followed:

dvc add → git add → git commit → dvc push

### 1. dvc add

The `dvc add` command tracks the dataset with DVC and creates a `.dvc` file.

### 2. git add

The generated `.dvc` file is staged with Git.

### 3. git commit

The DVC tracking file is committed to Git with a meaningful commit message.

### 4. dvc push

The actual dataset is pushed to the configured DVC remote.

## Comparing Dataset Versions

The `dvc diff` command is used to compare the current dataset with a previous dataset version.

Example:

`dvc diff 52b2abc`

This showed that `data/raw/iris_v1.csv` was modified.

## Restoring Dataset Versions

The `dvc checkout` command is used to restore a dataset version.

The historical Version 1 was restored using the Version 1 `.dvc` file, and the dataset was verified to contain 150 rows.

The latest Version 2 was then restored and verified to contain 170 rows.