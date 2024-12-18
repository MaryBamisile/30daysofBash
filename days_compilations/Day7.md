#### Learning about Bash structure

A basic Bash script typically follows this structure:

1. Shebang
2. Comments/Documentation
3. Global variables
4. Functions
5. Main script logic

#### Day 7 Learning achievment:
##### Wrote a script to: 
1. Accept a user's name as a command-line argument and include it in the greeting.
2. Add error handling to the count_down function to ensure the input is a positive integer.
3. Create a new function that generates a random number between 1 and 10, and use it in the main script logic.
4. log its output to a file in addition to displaying it on the screen.
5. Add a menu system to your script, allowing the user to choose between different functions to execute.

```bash

#!/bin/bash

# Global variables
GREETING="Hello, World!"
LOG_FILE="script_output.log"
MAX_COUNT=5

# Functions

print_greeting() {
    local user_name=$1
    echo "Hello, $user_name!"
    echo "Hello, $user_name!" >> "$LOG_FILE"
}

count_down() {
    local count=$1

    # Error handling for positive integer input
    if ! [[ "$count" =~ ^[0-9]+$ ]] || [[ "$count" -le 0 ]]; then
        echo "Error: Please enter a positive integer for countdown."
        echo "Error: Please enter a positive integer for countdown." >> "$LOG_FILE"
        return 1
    fi

    while [ $count -gt 0 ]; do
        echo $count
        echo $count >> "$LOG_FILE"
        count=$((count - 1))
        sleep 1
    done

    echo "Blast off!"
    echo "Blast off!" >> "$LOG_FILE"
}

generate_random_number() {
    echo $((RANDOM % 10 + 1))
}

show_menu() {
    echo "Menu:"
    echo "1. Print Greeting"
    echo "2. Count Down"
    echo "3. Generate Random Number"
    echo "4. Exit"
}

# Main script execution starts here

# Clear the log file at the beginning
> "$LOG_FILE"

echo "Starting the script..."

# Get the user's name from command-line argument
if [[ -z "$1" ]]; then
    echo "Usage: $0 <your_name>"
    exit 1
fi

user_name="$1"
print_greeting "$user_name"

while true; do
    show_menu
    read -p "Choose an option: " choice

    case $choice in
        1)
            print_greeting "$user_name"
            ;;
        2)
            read -p "Enter a positive integer for countdown: " user_count
            count_down "$user_count"
            ;;
        3)
            random_number=$(generate_random_number)
            echo "Generated Random Number: $random_number"
            echo "Generated Random Number: $random_number" >> "$LOG_FILE"
            ;;
        4)
            echo "Exiting the script."
            echo "Exiting the script." >> "$LOG_FILE"
            break
            ;;
        *)
            echo "Invalid option. Please choose again."
            echo "Invalid option. Please choose again." >> "$LOG_FILE"
            ;;
    esac
done

echo "Script execution completed."
echo "Script execution completed." >> "$LOG_FILE"
```


#### OUTPUT

![image](https://github.com/user-attachments/assets/715025b2-b2a4-45bf-bbf6-1ace3a895a69)

