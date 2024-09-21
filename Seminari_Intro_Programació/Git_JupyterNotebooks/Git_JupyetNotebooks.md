# Git and Jupyter Notebooks: The Ultimate Guide


## 1. Global Config

```bash
  >> git config --global user.name "Mona Lisa"
  >> git config --global user.email "email@example.com"
```

## 2. Git Clone

```bash
 >> git clone https://github.com/amit1rrr/projectA.git
```
## 3. Push Notebooks to Github

### 3.1 Track the file

```bash
>> git add analysis1.ipynb

// To check the status of the file "git status"

>> git status
```

### 3.2 Commit and Push

```bash
>> git commit -m "Adds customer data analysis notebook"
>> git push

```


# Develop in a Branch

## 1. Creating a New Branch
```bash
// Create a branch and change to it.
>> git branch branch_name
>> git checkout branch_name

// We can put this directly by using -b
>> git checkout -b customer_data_insights
```

## Push in the new branch

```bash
>> git push --set-upstream origin customer_data_insights
```

# Create Pull Request

## By Github
Using the Github UI