# flipping-bits-hacker-rank
Hacker Rank Fliping Bits solution

<?php

/*
 * Complete the 'flippingBits' function below.
 *
 * The function is expected to return a LONG_INTEGER.
 * The function accepts LONG_INTEGER n as parameter.
 */

function flippingBits($n) {
    // Write your code here
    $binary = sprintf('%032b', $n);
    $fliped = strtr($binary, [1,0]);
    return bindec($fliped);
}

$fptr = fopen(getenv("OUTPUT_PATH"), "w");

$q = intval(trim(fgets(STDIN)));

for ($q_itr = 0; $q_itr < $q; $q_itr++) {
    $n = intval(trim(fgets(STDIN)));

    $result = flippingBits($n);

    fwrite($fptr, $result . "\n");
}

fclose($fptr);

