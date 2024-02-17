# Php-assignment-
SOLUTION 1
<?php
function calculateGrade($cgpa) {
    $grade = '';
    
    if ($cgpa >= 4.0) {
        $grade = 'Excellent (A)';
    } elseif ($cgpa >= 3.5 && $cgpa < 4.0) {
        $grade = 'Very Good (B+)';
    } elseif ($cgpa >= 3.0 && $cgpa < 3.5) {
        $grade = 'Good (B)';
    } elseif ($cgpa >= 2.5 && $cgpa < 3.0) {
        $grade = 'Fair (C+)';
    } elseif ($cgpa >= 2.0 && $cgpa < 2.5) {
        $grade = 'Pass (C)';
    } else {
        $grade = 'Fail (F)';
    }
    
    return "CGPA: $cgpa - $grade";
}
?>

SOLUTION 2
?php

// Function to validate the entered date
function validateDate($year, $month, $day) {
    return checkdate($month, $day, $year);
}

// Function to check if the given year is a leap year
function isLeapYear($year) {
    return (($year % 4 == 0 && $year % 100 != 0) || $year % 400 == 0);
}

// Function to calculate the day of the week
function calculateDayOfWeek($year, $month, $day) {
    $timestamp = strtotime("$year-$month-$day");
    return date('l', $timestamp);
}

// Input from the user
$year = readline("Enter the year: ");
$month = readline("Enter the month (1-12): ");
$day = readline("Enter the day: ");

// Validate the date
if (!validateDate($year, $month, $day)) {
    echo "Invalid date entered. Please enter a valid date.\n";
    exit();
}

// Check if it's a leap year
$is_leap_year = isLeapYear($year);

// Switch statement to determine the day of the week
$day_of_week = calculateDayOfWeek($year, $month, $day);

// Output the result
echo "The day of the week for $year-$month-$day is: $day_of_week\n";
?>

SOLUTION 3
?php
function twoSum($nums, $target) {
    $map = array();
    
    foreach ($nums as $key => $value) {
        $complement = $target - $value;
        
        if (array_key_exists($complement, $map)) {
            return [$map[$complement], $key];
        }
        
        $map[$value] = $key;
    }
    
    return null; // No two numbers found that add up to the target
}

// Example usage:
$nums = [2, 7, 11, 15];
$target = 9;
$result = twoSum($nums, $target);
if ($result !== null) {
    echo "Indices of two numbers that add up to $target: " . $result[0] . ", " . $result[1];
} else {
    echo "No two numbers found that add up to $target.";
}
?>

SOLUTION 4
?php

function is_palindrome($s) {
    return $s === strrev($s);
}

$string = "radar";
if (is_palindrome($string)) {
    echo "It's a palindrome!";
} else {
    echo "It's not a palindrome.";
}

?>
