

Script 1:

```bash
#!/bin/bash

# Function to reverse each word in a given sentence
reverse_words() {
    local sentence="$1"
    local reversed=""
    
    # Split the sentence into words
    for word in $sentence; do
        reversed="$reversed $(echo "$word" | rev)"
    done
    
    # Trim leading space and print the result
    echo "$reversed"
}

# Get user input
read -p "Enter a sentence: " user_input
reversed_sentence=$(reverse_words "$user_input")
echo "Reversed words: $reversed_sentence"

```

Script2:

```bash
#!/bin/bash

# Function to count vowels in a given string
count_vowels() {
    local string="$1"
    local count=0

    # Iterate through each character in the string
    for (( i=0; i<${#string}; i++ )); do
        char="${string:i:1}"
        if [[ "$char" =~ [aeiouAEIOU] ]]; then
            ((count++))
        fi
    done

    echo "Number of vowels: $count"
}

# Example usage
read -p "Enter a string: " user_string
count_vowels "$user_string"

```

Script3

```bash
#!/bin/bash

# Check if filename is provided
if [ $# -ne 1 ]; then
    echo "Usage: $0 filename"
    exit 1
fi

# Get the filename and add prefix
filename="$1"
prefix="processed_"
new_filename="${prefix}${filename}"

# Rename the file
mv "$filename" "$new_filename"
echo "File renamed to: $new_filename"

```

Script4
```bash
#!/bin/bash

# Function to generate a random password
generate_password() {
    local length="$1"
    
    if (( length < 4 )); then
        echo "Password length must be at least 4."
        exit 1
    fi

    # Generate a random password
    password=$(cat /dev/urandom | tr -dc 'A-Za-z0-9@#$%&*!' | fold -w "$length" | head -n 1)

    # Ensure at least one uppercase letter, one lowercase letter, one number, and one special character
    while ! [[ "$password" =~ [A-Z] && "$password" =~ [a-z] && "$password" =~ [0-9] && "$password" =~ [@#$%&*!] ]]; do
        password=$(cat /dev/urandom | tr -dc 'A-Za-z0-9@#$%&*!' | fold -w "$length" | head -n 1)
    done

    echo "Generated password: $password"
}

# Get password length from user
read -p "Enter desired password length: " password_length
generate_password "$password_length"

```

```bash
#!/bin/bash

# Function to check if a string is a palindrome
is_palindrome() {
    local string="$1"
    local reversed="$(echo "$string" | rev)"

    if [[ "$string" == "$reversed" ]]; then
        echo "True: '$string' is a palindrome."
    else
        echo "False: '$string' is not a palindrome."
    fi
}

# Example usage
read -p "Enter a string to check if it's a palindrome: " user_string
is_palindrome "$user_string"

```
