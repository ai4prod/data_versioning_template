# Python Test

Python script to verify data integrity.
Each dataset could have different check

&nbsp;

# Create a customSuite{Task}

customSuite.py -> Will inclue all test that are task agnostic. Each task that is independet if I have a classification or object_detetion or ... task.

cutomSuite{Task}.py-> Will include all test specific to a task. For example there are some test for classification task that maybe are not good or useless for object_detection task.

Inside each cutomSuite.py you need to create test following **"How to create a new test"** section

&nbsp;

# How to create a new test

For each new Test Suite or Dataset version you need to create a new test. 
The name have to be test_suite{suite_number}_validate_dataset_v{dataset_version}

Each test will print an output_file with the result of every suite
If some data tests validation fail pytest result a failed test 

pytest test_dataIntegrity.py

&nbsp;

# How to Create a New suite  

Have a look inside customSuite.py
