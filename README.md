## Password_Strength_Checker

## Installation 

### Steps to Save Your Script Using Nano

1. **Open Terminal**:
   - Launch your terminal application.

2. **Create a New File with Nano**:
   - To create a new file named `password_strength_checker`, type:
     ```bash
     nano password_strength_checker
     ```

3. **Paste Your Code into Nano**:
   - After opening the `nano` editor, paste the password strength checker code into the editor. To paste in a terminal, you can usually use `Ctrl + Shift + V` (on Linux) or `Command + V` (on macOS).

   Here’s the code to paste:

   ```python
   import re

   def check_password_strength(password):
       """
       Checks the strength of a password based on length, complexity, and uniqueness.

       Args:
           password (str): The password to be checked.

       Returns:
           str: A string indicating the password strength ("Weak", "Medium", "Strong").
       """

       length_score = 0
       complexity_score = 0
       uniqueness_score = 0

       # Length score
       if len(password) < 8:
           length_score = 1
       elif len(password) < 12:
           length_score = 2
       else:
           length_score = 3

       # Complexity score
       if re.search(r"[a-z]", password) and re.search(r"[A-Z]", password) and re.search(r"[0-9]", password) and re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
           complexity_score = 3
       elif re.search(r"[a-z]", password) and re.search(r"[A-Z]", password) and re.search(r"[0-9]", password):
           complexity_score = 2
       elif re.search(r"[a-z]", password) and re.search(r"[A-Z]", password):
           complexity_score = 1
       else:
           complexity_score = 0

       # Uniqueness score (simplistic check)
       if len(set(password)) / len(password) > 0.7:
           uniqueness_score = 2
       elif len(set(password)) / len(password) > 0.5:
           uniqueness_score = 1
       else:
           uniqueness_score = 0

       total_score = length_score + complexity_score + uniqueness_score

       if total_score < 4:
           return "Weak"
       elif total_score < 7:
           return "Medium"
       else:
           return "Strong"


   # Example usage
   password = input("Enter a password: ")
   strength = check_password_strength(password)
   print(f"Password strength: {strength}")
   ```

4. **Save the File**:
   - After pasting the code, save the file by pressing `Ctrl + O` (the letter O, not zero).
   - Nano will prompt you to confirm the file name. Just press `Enter` to confirm.

5. **Exit Nano**:
   - To exit the nano editor, press `Ctrl + X`.

### Step 5: Run Your Script

1. **Make Sure You’re in the Right Directory**:
   - Verify that you're still in the directory where you saved the file.

2. **Run the Script**:
   - Execute the script with the following command:
     ```bash
     python3 password_strength_checker
or 
      python3 password_strength_checker
     ```
     

3. **Test the Functionality**:
   - Enter various passwords when prompted to see the strength ratings.

### Optional: Check if Python is Installed

If you encounter issues running the script, ensure that Python is installed on your system. You can check this by typing:

```bash
python --version
```
or
```bash
python3 --version
```

If Python is not installed, you must download and install it from [python. org](https://www.python.org/downloads/).







