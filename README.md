Student Registration Number: 24/1401/BSCE-J
Program
24_1401_BSCE-J_W02.ipynb is a Google Colab notebook. It sets my student ID, prints a greeting, calculates proof_sum = 2 + 2 (4), updates a readings variable (12 + 5 = 17), and reads site_inspection_log.csv into a list called rows (4 records). It also contains my written explanation of execution order.
File list
	•	24_1401_BSCE-J_W02.ipynb: my completed main notebook, saved with outputs
	•	site_inspection_log.csv: the supplied practice dataset (4 rows)
	•	01_missing_module.ipynb: repaired practice notebook
	•	02_wrong_runtime.ipynb: repaired practice notebook
	•	03_wrong_path.ipynb: repaired practice notebook
	•	04_hidden_state.ipynb: repaired practice notebook
	•	README.md: this file
How to run
	1.	Download or clone this repository.
	2.	Go to https://colab.research.google.com and sign in.
	3.	Choose File > Upload notebook and select YOUR_REG_NUMBER_W02.ipynb.
	4.	Open the Files panel (folder icon) and upload site_inspection_log.csv.
	5.	Choose Runtime > Restart session and run all.
	6.	It should finish with no errors and print 4, 17 and 4 (rows).
What changed when I repeated a cell
When I ran readings = readings + 5 the first time it printed 17, because readings was 12. Running it again printed 22, and a third time printed 27. The cell does not reset readings. It adds 5 to whatever value the notebook currently remembers, so each run builds on the last one.
What Restart and Run All does
It clears the notebook's memory (all variables and imports) and then runs every cell once, from top to bottom, in order. After it, readings starts at 12 again and ends at 17. If it finishes with no errors, the notebook does not depend on hidden state or on cells being run out of order.
Engineering problems
1. Missing module (01_missing_module.ipynb)
Error: ModuleNotFoundError: No module named 'course_package_not_installed'
Cause: Python could not find a module with that name. It was not installed in the Colab environment, and the name did not belong to any real package.
Fix: I replaced the import with import math, a module that exists in Python's standard library, and reran the cell. It finished with a green tick and no error. For a real missing package, I would install it first with !pip install packagename and then rerun the import.
2. Wrong Python version (02_wrong_runtime.ipynb)
Error: AssertionError: Notebook expects Python 2, but the course uses Python 3
Cause: The notebook checked that sys.version_info.major == 2, but Colab runs Python 3, so the assertion failed.
Fix: I changed the check to sys.version_info.major == 3 and reran the cell. It finished with a green tick and no error.
3. Wrong file path (03_wrong_path.ipynb)
Error: FileNotFoundError: [Errno 2] No such file or directory: 'missing_folder/site_inspection_log.csv'
Cause: The code looked for the CSV inside a folder called missing_folder, which does not exist. The file was uploaded to the top level of Colab's Files panel.
Fix: I changed the path to "site_inspection_log.csv" and reran the cell. It printed the header row, reading_id,crack_width_mm, with no error.
4. Hidden state / overwritten variable (04_hidden_state.ipynb)
Problem: The cell ran without an error but printed 12 instead of the expected 17.
Cause: The line readings = 12 appeared twice. The second one ran after readings = readings + 5 and overwrote the result, so the value was reset before it was printed.
Fix: I deleted the second readings = 12 line and reran the cell. It printed 17, matching the expected result.