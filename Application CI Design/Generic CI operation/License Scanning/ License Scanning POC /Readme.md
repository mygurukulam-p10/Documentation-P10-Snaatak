
# License Scanning : Proof Of Concept - FOSSA

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 24-09-24    | version 1  | Amit Nagar      | 26-09-24       |

***
## Table Of Contents 
+ [Introduction](#introduction)
+ [FOSSA](#fossa)
+ [FOSSA Setup](#fossa-setup)
+ [License Scanning via FOSSA](#license-scanning-via-FOSSA)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)
***
## Introduction 
License scanning refers to the process of automatically analyzing and identifying software licenses associated with code or components within a software project. This practice is crucial for organizations to ensure compliance with open-source licenses, proprietary licenses, and other legal requirements.
***


## FOSSA Setup
### Installation Steps 

**Step 1:** 
Go to the [FOSSA Website](https://fossa.com/) and select *Start For Free*
![Screenshot from 2024-09-26 01-15-15](https://github.com/user-attachments/assets/31ef5936-33ff-4c0b-87c8-9ca10c8df414)

**Step 2:** Select CLI Option
![Screenshot from 2024-09-26 02-22-34](https://github.com/user-attachments/assets/b04b94b0-f5d4-4c8a-806a-67cc1b5e2d5c)

**Step 3:** Run command on your machine.

![Screenshot from 2024-09-26 02-25-00](https://github.com/user-attachments/assets/6217650a-7d7a-4013-bea8-1115efd7328c)

**Step 4:** Set your API key

```shell
export FOSSA_API_KEY=<Your-API-Key>
```

***
## License Scanning via FOSSA 

Navigate into your code directory and run the following command.
```shell
fossa analyze
```

![Screenshot from 2024-09-26 02-27-23](https://github.com/user-attachments/assets/c9854450-5470-4ead-8007-1bd0966fe5d2)

![Screenshot from 2024-09-26 02-32-26](https://github.com/user-attachments/assets/5f1db66e-f06d-497b-a800-0d954cde81e2)


## Conclusion
As organizations increasingly recognize the importance of managing open-source components effectively, FOSSA emerges as a valuable tool in safeguarding intellectual property, mitigating legal risks, and promoting secure and compliant software development practices. Its adoption signifies a commitment to transparency, efficiency, and the long-term sustainability of software projects in an ever-evolving landscape of open-source contributions.


## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
| FOSSA Setup  | https://blog.opstree.com/2023/04/04/fossa-audit-grade-open-source-dependency-protection/#more-13285 |
| FOSSA Docs | (https://docs.fossa.com/docs/introduction)https://docs.fossa.com/docs/introduction | 


