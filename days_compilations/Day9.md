





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
