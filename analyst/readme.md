## Overview

To solve these tasks, you must use both Python and Pandas, but otherwise feel free to `pip install` whatever library you would like. These tasks are designed to test your ability to:

- Call REST APIs
- Import and export data as CSVs
- Clean messy data
- Do copy operations in `Pandas` like grouping and joining
- Write Python

Once you have completed the assignment, please email the Python files to paulzakin@bsd.uchicago.edu.

### Important

- This task is not restricted in any way. So feel free to use Google, Stack Overflow, etc. The only thing you cannot do is ask a friend for help! 

- This task should **not** take you longer than 3 hours. It took that last developer ~ 1 hour to complete it fully. If you exceed three hours, **please stop**. This test is **not** designed to be an all-day assignment. We made a bunch of questions **bonus** specifically so you don't have to go over time.

## Instructions

### Pandas

1. Using a GET request, pull down appointments.csv and people.csv from these links and convert them into DataFrames:
   
   - [People](https://raw.githubusercontent.com/ipph-development/programming-analyst-interview-test/main/people.csv)
   - [Appointments](https://raw.githubusercontent.com/ipph-development/programming-analyst-interview-test/main/appointments.csv)

2. Replace \n in the address column with a `" "`

3. Extract out the `zipcode` into a new column called `zipcode` using **regex**. For this test, you can assume that the `zipcode` will always be a five-digit number. Hint: Pandas has a method called `str.extract`.

4. Bonus: Replace all phone numbers not in this format: `XXX-XXX-XXXX` with the string “INVALID”. For example, 779-477-6793 is valid while 779-477-6793-121 is not.
 
5. Bonus: Replace `weight_in_lbs` below 90 and above 250 with `np.nan`.

6. Bonus: Create a `bmi` column: [formula here](https://www.cdc.gov/nccdphp/dnpao/growthcharts/training/bmiage/page5_2.html).
   
7. Bonus: Create a `metabolic_syndrome` column which is `True` 
   1. The participant has a `bmi` > 30, 
   2. `has_hypertension` is true
   3. `has_diabetes` is also true
   
8.  Bonus: Create another column, `BMI_by_sex`, which contains the average BMI of each sex. Hint: This will require you to `INNER JOIN` the datasets. Be sure to remove any duplicate `participant_id` from both the person and appointments DataFrame before you do!

9.  Bonus: Export the combined dataset as `combined.csv`.

### Python

Write a simple Request class whose constructor takes a single parameter of `path`. The concept of path is constrained to just refer to two elements resource and `id` in the form `resource_name/id`

#### Tasks    

- Validate that the path that was passed was a string. Raise a `TypeError` with the message "Path should be a string with two elements".
  
- Split the path based on the "/" delimiter. You can leave off handling a case where a wrong delimiter was passed in.  
  
- Check the first element of the path is a word. [Hint](https://docs.python.org/3/library/stdtypes.html#str.isalpha).
  
- Assign to an instance variable `resource` if this is true and raise `ValueError` if it is not.
  
- Check the second element is an integral number.
  
- Assign to an instance variable `id` if this is true and raise ValueError if it is not.
  
- If these assignments worked out, go ahead and set a boolean instance variable `valid`. 

#### Deliverable Notes

- All the code you write will be in the constructor of a class Request found in a module `server`.
- Unit tests are provided for you that reiterate the above specification of tasks.  
- To test your code, run the following from your project root directory `python -m unittest` 

