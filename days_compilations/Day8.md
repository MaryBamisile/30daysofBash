#### Input/Output Redirection

###### Input/Output (I/O) redirection is a feature that allows you to control where input comes from and where output goes.I learnt about the three standard streams:
1. Standard Input (stdin) - Stream for input, file descriptor 0
2. Standard Output (stdout) - Stream for output, file descriptor 1
3. Standard Error (stderr) - Stream for error messages, file descriptor 2

###### Basic Redirection Operators
<li> >: Redirect stdout to a file (overwrite)
<li> >>: Redirect stdout to a file (append)
<li> <: Redirect stdin from a file
<li> 2>: Redirect stderr to a file
<li> &>: Redirect both stdout and stderr to a file

###### Overall, I was able to practice the usage by writing scripts with following details: 
1. Takes user input and appends it to a file. If the file doesn't exist, create it.
2. Reads a list of numbers from a file, sorts them, and writes the sorted list to a new file.
3. Executes a command, redirects its output to a file, and also displays the output.
4. Uses a here document to generate a simple HTML file.
5. Redirects errors to a log file, but still displays normal output on the screen.
script1:

![image](https://github.com/user-attachments/assets/5de9639e-987e-4e66-9d4d-06bf75514e2c)

Script2:

![image](https://github.com/user-attachments/assets/c95889a8-eb3f-45fd-a395-4b15d5bdadd5)

Script3: 

![Day8 3](https://github.com/user-attachments/assets/75866d5f-8fd2-4606-a458-c6d4be3df1b4)

Script4:

![image](https://github.com/user-attachments/assets/b206770d-fa79-4c85-9480-7529c5165188)

Script5:

![image](https://github.com/user-attachments/assets/1d75fab7-264c-47dc-8130-9026cd8db81a)
