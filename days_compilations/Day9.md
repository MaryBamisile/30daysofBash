





script 1
```bash

#!/bin/bash

# Define an array of favorite foods
favorite_foods=("Pizza" "Sushi" "Tacos" "Ice Cream" "Pasta")

# Print each item in the array on a new line
for food in "${favorite_foods[@]}"; do
    echo "$food"
done
```
![image](https://github.com/user-attachments/assets/5cdf9d6c-8f15-4982-9f75-7bbdd7548232)


script 2
```bash

#!/bin/bash

# Store command-line arguments in an array
args=("$@")

# Print the number of arguments
echo "Number of arguments: ${#args[@]}"

# Print each argument's value
for arg in "${args[@]}"; do
    echo "$arg"
done

```
![image](https://github.com/user-attachments/assets/ee38d5ee-6ca5-4b1e-b129-d517e026db70)

script 3
```bash
#!/bin/bash

# Function to return unique elements from an array
unique_elements() {
    local arr=("$@")
    local -A unique_map
    local unique_array=()

    for item in "${arr[@]}"; do
        unique_map["$item"]=1
    done

    # Retrieve unique items into an array
    for key in "${!unique_map[@]}"; do
        unique_array+=("$key")
    done

    echo "Unique elements: ${unique_array[@]}"
}

# Example usage
input_array=("apple" "banana" "apple" "orange" "banana")
unique_elements "${input_array[@]}"

```
Script 4
``` bash
#!/bin/bash

# Check if file is provided
if [ $# -ne 1 ]; then
    echo "Usage: $0 filename"
    exit 1
fi

# Read file into an array
mapfile -t lines < "$1"

# Convert each line to uppercase and print
for line in "${lines[@]}"; do
    echo "${line^^}"
done
```

script 5
``` bash
#!/bin/bash

# Declare an associative array
declare -A capitals

# Populate the associative array
capitals=( ["USA"]="Washington, D.C." ["France"]="Paris" ["Germany"]="Berlin" ["Japan"]="Tokyo" )

# Print each country and its capital
for country in "${!capitals[@]}"; do
    echo "The capital of $country is ${capitals[$country]}"
done

# Example of retrieving a specific capital
country_to_lookup="Germany"
echo "The capital of $country_to_lookup is ${capitals[$country_to_lookup]}"

```
