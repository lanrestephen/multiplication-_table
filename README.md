# multiplication-_table
I used the code.
#!/bin/bash

# Function to display the multiplication table
display_table() {
    local num=$1
    local start=$2
    local end=$3

    echo "Multiplication table for $num:"
    for i in $(seq $start $end); do
        echo "$num x $i = $((num * i))"
    done
}

# Prompt user for input
read -p "Please enter a number: " number

# Check if input is a valid number
if ! [[ "$number" =~ ^[0-9]+$ ]]; then
    echo "Invalid input! Please enter a positive integer."
    exit 1
fi

# Ask user for the type of table they want
echo "Would you like to see a (1) Full multiplication table (1-10) or (2) Partial table (within a specific range)?"
read -p "Enter 1 or 2: " choice

case $choice in
    1)
        # Display full table from 1 to 10
        display_table $number 1 10
        ;;
    2)
        # Prompt for range
        read -p "Enter the start of the range: " start
        read -p "Enter the end of the range: " end

        # Check if inputs are valid numbers
        if ! [[ "$start" =~ ^[0-9]+$ && "$end" =~ ^[0-9]+$ && $start -le $end ]]; then
            echo "Invalid range! Please enter valid positive integers where start is less than or equal to end."
            exit 1
        fi

        # Display the partial table
        display_table $number $start $end
        ;;
    *)
        echo "Invalid choice! Please enter 1 or 2."
        exit 1
        ;;
esac
then I change the permissions.
chmod +x multiplication_table.sh

Then I tested that it works.

![image](https://github.com/user-attachments/assets/66f37e52-c853-4c62-99da-2f54290ea25a)

