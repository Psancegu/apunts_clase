# Virtual Environment in Python

## Creating a Virtual Environment

```bash
>> python3 -m venv <venv_name>
```

## Activate the VENV

```bash
>> source env/bin/activate
```

## Deactivate the VENV

```bash
>> deactivate
```

## List of packages
```bash
>> pip list
```
Should appear empty because we are in the VENV.

## Install Packages (PIP)

```bash
>> pip install <package name>
```

## Saving Depenencies
```bash
>> pip freeze > requirements.txt
```
This creates a file with all the packages and its version.

## Import packages from other VENV (Using requirements.txt)
```bash
// In another VENV in the same folder of the /VENV.
>> pip install -r requirements.txt
```

