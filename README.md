Case: Imperial Memory

Executive Summary: You are provided with the user and password 'derrek:r3s3arch3r to reconnet if needed. Inspect the dump file to find clues for unlocking the archive file. Also analyze and investigate the Docx file. Examine the secrets.txt fileto see what was hiding on the desktop computer. Next day you find that a note was left saying "Always keep this in your memory". Implied I was doing something with a memory dump.

Findings and analysis:

Finding:

Hash

Finding Details:

0f235385d25ade312a2d151a2cc43865

Description:

The MD5 hash of the secrets.txt file

This hash was discovered by unzipping the secrets.txt file on the target computer

Finding:

Malicious file

Finding Details:

Secrets.txt

This file was suspicious on the computer

This file appears to be a suspicious file that was downloaded on your computer

Methodology:

Tools and Technologies Used:

Cd: is a command used to change the Directory of the file to a different directory
Ls: is a command used to see what is in the directory
Vol.py: is the main command line script used to analyze Ram and memory dumps amd used to uncover things like running processes and malware running in the memory
Unzip: used to unzip a zipped file to see whts in the file
Malfind: used to find malicious processes in the directory
Imageinfo: used to get info for the image of the file
MD5sum: finds the MD5 hash of a file 

Investigation Process

1. I started by changing the directory to the Desktop directory
2. Next I used ls to see what files were on the Desktop directory
3. After that, I saw that the gift.7z file was in the Desktop and I used 7z x gift.7z which the 7z is the command-line version of the 7-zip that worked with our version of volatility, thex extracts full paths and then the gift.7z is the file I was extracting from
4. Next, I went a different direction with the information as I was not getting anywhere and started looking in the Emperor.vmem file with getting the image info of that file. Then from that information I found that there were two processes used for the file
5. Then, I used pstree to find the process tree of the Emperor.vmem file
6. Then, I looked up what command was used to find malicious files in vol.py and found it was malfind so I used that to find the malicious processes on the Emperor.vmem file
7. Next, I unzipped the suspicious file and found that the secrets file was in the suspicious docx file
8. Then, I found the MD5 Hash of the suspicious file which was not the right hash for the challege
9. Finally, I went a different direction and unzipped the secrets.txt file nd found the MD5 Hash of the secrets.txt file which was the right hash to get the challenge figured out

Reccommendations:

1. Automate scans that are repeatable on a machine if at all possible
2. Use multiple tools and not rely on one alone because you can't get complete coverage of the system or perfect accuracy, by combining them you increase your chances of finding hidden artifacts and the flags itself for the challenges
