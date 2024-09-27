

# POC of Static Code analysis in Python

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                |
|--------------------|------------|--------------|---------------------------|
| 20-09-2024         | 0.1        | Brij Singh   | Static Code Analysis      |

# Table of Contents
- [Introduction](#Introduction)
- [Pre-requisites](#pre-requisites)
- [Flow Diagram](#flow-diagram)
- [POC of Static Code Compilation in Python](#POC-of-Static-Code-Compilation-in-Python)
- [Output](#Output)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Resources and References](#resources-and-references)
***

# Introduction
Static code analysis is the process of analyzing source code without executing it. 

# Pre-requisites

| **Tool**   |    
| --------   | 
|  Python    | 
|  Pylint    |

| **Code**               |
| --------               | 
|  Any Python code       |

# Flow Diagram



# POC of Static Code Compilation in Python

**Step-1** Clone the Repository:
- Open a terminal (or command prompt).
- Navigate to the desired directory using cd commands.
- Clone the repository using 

```git clone  https://github.com/OT-MICROSERVICES/attendance-api.git

```



**Step-2** Install python and pylint
``` shell 
sudo apt install python3
sudo apt install pylint
``` 

++++++++

**Step-3** Run pylint
``` shell 
pylint app.py
```      
+++++++++

# Output
The output we received from running pylint on app.py file indicates the quality of our Python code according to pylint's metrics.
our code has been rated at 10.00/10: This means that pylint has evaluated Python code and assigned it a score of 10 out of 10. This is the highest possible score, indicating that pylint didn't find any issues or violations of Python coding standards in your code.

# Conclusion

The output from pylint indicates that your Python code has been analyzed and evaluated against a set of coding standards and best practices. The conclusions you can draw from the pylint output are:
* High Quality Code
* Code Health

In summary, the pylint output indicates that your Python code is of excellent quality.  This should give you confidence in the reliability and maintainability of your codebase.

## 📧 Contact Information

For questions or more info, you can reach out to:

| 📛 Name       | ✉️ Email Address                   |
|---------------|-----------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co |

# Resources and References


[POC](https://medium.com/@tlilyskander/static-code-analysis-with-pylint-49a078f029cf)

