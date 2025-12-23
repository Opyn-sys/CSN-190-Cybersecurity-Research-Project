#### From Setup to Scan: Deploying OWASP Nettacker in Kali Linux as a Cybersecurity Student

#### INTRODUCTION
- After setting up my first cybersecurity tools in a Kali Linux virtual machine, I quickly realized installing software is only half the challenge. The real learning happens when you make a tool actually run, troubleshoot what breaks, and understand what the results mean. That realization led me to OWASP Nettacker, an open-source automated reconnaissance and security scanning framework.
In this article, I documented my hands-on experience deploying OWASP Nettacker from GitHub, resolving dependency errors in a Python virtual environment, and successfully running the tool to perform a practical scan. Rather than listing features, I focus on what I did: cloning the repository, activating a virtual environment, fixing missing Python modules, and generating real scan output. I chose Nettacker because I am interested in penetration testing and reconnaissance, which are foundational skills in cybersecurity. Tools like Nettacker are often used at the beginning of security assessments to identify exposed services and possible entry points. This project helped me transition from guided labs to real-world troubleshooting.

#### PURPOSE AND BACKGROUND
- OWASP Nettacker is an automated penetration testing and reconnaissance framework developed under the OWASP project. Its purpose is to assist security professionals during the discovery and assessment phases of a security engagement by running modular scans against a target system. I chose this tool because it reflects how real-world security tools behave. Unlike classroom labs, Nettacker required me to understand module naming, dependency management, and Linux troubleshooting. Initially, I expected a simple installation process, but I encountered multiple missing dependency errors. Solving these issues forced me to read error messages carefully and research documentation. This experience reinforced an important lesson, automation does not replace understanding. A tool is only as effective as the person using it. Learning how to deploy and troubleshoot Nettacker helped me build practical skills that apply directly to penetration testing and cybersecurity operations.


#### INSTALLATION AND SETUP
- The project was deployed in a Kali Linux virtual machine.
- Prerequisites included Kali Linux, Python 3, pip, git, and internet connectivity.
- After updating the system and installing required packages, I cloned the OWASP Nettacker repository from GitHub. I created and activated a Python virtual environment to isolate project dependencies. When running Nettacker for the first time, I encountered multiple ModuleNotFoundError messages. These were resolved by installing the required Python libraries individually inside the virtual environment. Using AI tools helped speed up troubleshooting by explaining error messages and identifying which pip packages provided missing modules.
![6 2 mkdir clone githun link and create virtual environmnet](https://github.com/user-attachments/assets/2186bfdf-15af-4e21-9f59-37764f531541)

![6 2 phython updated](https://github.com/user-attachments/assets/0ba1e969-80da-410a-8852-59fce8310e0f)

#### Step 1: Navigate to Project Directory
- Command: cd ~/CSN190/Nettacker
- Getting into the project directory that has the phython code ready for execution
 <img width="973" height="448" alt="image" src="https://github.com/user-attachments/assets/efafec01-a3a8-4e8b-ac8d-64c6335cd31a" />

Figure 2: Navigating to the Nettacker project directory

#### Step 2: Activate Virtual Environment
- Command: source venv/bin/activate
- This command activates the Python virtual environment created for the Nettacker project. The virtual environment isolates project dependencies from the system-wide Python installation, preventing conflicts and ensuring that all required libraries are installed and used only for this project.
<img width="889" height="317" alt="image" src="https://github.com/user-attachments/assets/a3460f02-a7dd-4477-afba-5592b848fba4" />
 
Figure 3: Python virtual environment activated
#### Step 3: List Available Modules
- Command: python3 nettacker.py --show-all-modules
- This command displays all available scanning and vulnerability modules included with OWASP Nettacker. Reviewing the module list is important because Nettacker requires exact module names to execute scans. This step helps identify valid modules that can be used for testing.
 <img width="972" height="480" alt="image" src="https://github.com/user-attachments/assets/6c07af98-aca0-40fb-8e12-9c0c9f4aafda" />

Figure 4: Listing all available Nettacker scanning modules
Section: Running a Scan with Nettacker
#### Step 4: Execute a Scan Module
- Command: python3 nettacker.py -i 127.0.0.1 -m admin_scan -o results.json

- In this step, Nettacker is instructed to run the admin_scan module against the target IP address 127.0.0.1, which refers to the local machine. The admin_scan module attempts to identify common administrative directories and endpoints. Using localhost as the target is safe and legal because it only scans the system running the tool. The -o results.json option forces Nettacker to save the scan results to a JSON file for later review.
 <img width="975" height="473" alt="image" src="https://github.com/user-attachments/assets/20e60578-3f59-4872-898e-1e7a75d7918d" />

Figure 5: Running the admin_scan module against the local host
#### Step 5: Verify Output File
The ls command confirms that the scan output file was successfully created in the project directory. The cat results.json command displays the contents of the results file, allowing verification that Nettacker generated structured output data from the scan. This confirms that the scan module executed correctly and produced results.
Commands:
•	ls
•	cat results.json
When the scan runs successfully, OWASP Nettacker loads the selected module and performs reconnaissance against the specified target. After execution, an output file is generated containing structured scan results in JSON format. These results confirm that Nettacker executed a real task and processed scan data correctly. Even if no vulnerabilities are found, the presence of the output file demonstrates successful operation

#### CHALLENGES AND PROBLEM-SOLVING
The main challenge was dependency management. Nettacker did not include a traditional requirements.txt file, which caused repeated missing module errors. Each issue was resolved by carefully reading traceback messages and installing dependencies inside the virtual environment. Another challenge involved module naming. Guessing module names resulted in failed scans. Listing available modules and selecting valid names solved the problem.
<img width="877" height="233" alt="6 2 error 5" src="https://github.com/user-attachments/assets/3b5b640b-aecc-42dd-8590-7f9c2712d17d" />
<img width="923" height="470" alt="6 2 error 4" src="https://github.com/user-attachments/assets/d00b6869-77ba-4302-9fbb-5201c20861d9" />
<img width="863" height="334" alt="6 2 error 3" src="https://github.com/user-attachments/assets/64a4f33f-b07e-4884-837e-39697308e0f9" />
<img width="801" height="333" alt="6 2 error 2" src="https://github.com/user-attachments/assets/4f4ebc5e-2c0b-4e8f-a43d-ae9450456d74" />
<img width="909" height="279" alt="6 2 error 1" src="https://github.com/user-attachments/assets/00da7cc4-db88-46ee-827a-332021d08644" />

#### CONCLUSION AND FUTURE APPLICATIONS
This project demonstrated the realities of deploying cybersecurity tools outside of guided labs. I learned how to manage Python environments, troubleshoot Linux-based issues, and document technical work clearly. In the future, I plan to test Nettacker against authorized lab environments and compare its results with other reconnaissance tools. This project strengthened both my technical skills and my ability to communicate cybersecurity work effectively.

#### RESOURCES AND LINKS
#### Software and Tools
- OWASP Foundation. (n.d.). OWASP Nettacker. GitHub. https://github.com/OWASP/Nettacker
- Offensive Security. (n.d.). Kali Linux documentation. https://www.kali.org/docs/
- Python Software Foundation. (n.d.). Python programming language. https://www.python.org/
- Git SCM. (n.d.). Git version control system. https://git-scm.com/
- Microsoft. (n.d.). Visual Studio Code. https://code.visualstudio.com/

#### Python Libraries and Dependencies
- McKerns, M. et al. (n.d.). multiprocess [Python library]. Python Package Index (PyPI). https://pypi.org/project/multiprocess/
- Simonov, K. (n.d.). PyYAML [Python library]. Python Package Index (PyPI). https://pypi.org/project/PyYAML/
- Netaddr Project. (n.d.). netaddr [Python library]. Python Package Index (PyPI). https://pypi.org/project/netaddr/
- Kenneth Reitz. (n.d.). requests: HTTP for humans [Python library]. Python Package Index (PyPI). https://pypi.org/project/requests/
- Leplat, B. (n.d.). texttable [Python library]. Python Package Index (PyPI). https://pypi.org/project/texttable/

#### Research and Standards
- OWASP Foundation. (n.d.). OWASP projects. https://owasp.org/www-projects/
- National Institute of Standards and Technology. (n.d.). Cybersecurity Framework. https://www.nist.gov/cyberframework
- National Institute of Standards and Technology. (n.d.). Special Publication 800 Series. https://csrc.nist.gov/publications/sp800

#### Learning Platforms and Labs
- TryHackMe. (n.d.). Hands-on cybersecurity training platform. https://tryhackme.com/
- Hack The Box. (n.d.). Offensive security labs and challenges. https://www.hackthebox.com/

#### AI and Development Assistance Tools
- GitHub. (n.d.). GitHub Copilot. https://github.com/features/copilot
- OpenAI. (n.d.). ChatGPT. https://chat.openai.com/
