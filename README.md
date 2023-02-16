# BOMAHUT Interview Question

a) Write an algorithm that given an M X N matrix return all numbers that are the maximum value inits row but the minimum in its column

For example if given the matrix
Input:matrix = [[5,16,20],[9,11,18],[15,16,17]]
Output:[17]
Explanation:17 is the only number since it is the maximum in its row and the minimum in its
column.

Input:matrix = [[100,60,20, 50],[70,80,10,90],[10,50,44,30]]
Output:[50]
Explanation:50 is the only number since it is the maximum in its row and the minimum in its
column.
Constraints:
● m == mat.length
● n == mat[i].length
● 1 <= n, m <= 50
● 1 <= matrix[i][j] <= 105.
● All elements in the matrix are distinct.

b) What is the space and time complexity of your solution?

c) Write 1-2 tests that you run to validate your answer.

## Solution

### 1.A

const arr1 = [
[5, 16, 20],
[9, 11, 18],
[15, 16, 17],
];

const arr2 = [
[100, 60, 20, 50],
[70, 80, 10, 90],
[10, 50, 44, 30],
];

const arr3 = [
[11, 60, 90, 50],
[7, 40, 69, 21],
[10, 88, 73, 30],
];

const myFunction = (matrix) => {

    let result = [];
    for (let i = 0; i < matrix.length; i++) {

        let row = matrix[i];

        // Find the maximum value in the current row
        let max = Math.max(...row);

        // Find the column index of the maximum value
        let maxIndex = row.indexOf(max);

        // Extract the column with the column index
        let column = matrix.map((row) => row[maxIndex]);

        let min = Math.min(...column);

        if (max === min) {
        result.push(max);
        }

    }

    return result;

};

const answervar = myFunction(arr3);

console.log(answervar);

### 1.B

Time complexity - O(MN);

Space complexity O(1)

### 1.C

Test cases

const arr1 = [
[5, 16, 20],
[9, 11, 18],
[15, 16, 17],
];

const arr2 = [
[100, 60, 20, 50],
[70, 80, 10, 90],
[10, 50, 44, 30],
];

const arr3 = [
[11, 60, 90, 50],
[7, 40, 69, 21],
[10, 88, 73, 30],
];
