# Assignment 5: Quicksort Algorithm – Implementation, Analysis, and Randomization
## Overview
This project focuses on the implementation, analysis, and performance evaluation of the Quicksort algorithm. Quicksort is a comparison-based sorting algorithm that follows the divide-and-conquer approach by selecting a pivot, partitioning the array into smaller subarrays, and recursively sorting the partitions.
This assignment implements and compares two versions of Quicksort:
1. Deterministic Quicksort
•	Uses a fixed pivot selection strategy.
•	The implementation selects the last element as the pivot.
•	Demonstrates how poor pivot selection can lead to worst-case performance.
2. Randomized Quicksort
•	Selects the pivot randomly during each partition step.
•	Reduces the probability of encountering highly unbalanced partitions.
•	Provides more consistent performance across different input distributions.
The objective of this project is to understand the effect of pivot selection on Quicksort performance and compare theoretical complexity analysis with experimental runtime results.
# Project Structure
•	Quicksort Algorithm Implementation, Analysis, and Randomization.ipynb
•	README.md
•	Quicksort_Algorithm_Implementation_Analysis_and_Randomization_Report.pdf
# Requirements
The project was implemented using Python 3.
## Required Libraries
The following Python libraries are used:
-	random - for randomized pivot selection
-	time - for measuring execution time
-	sys - for adjusting recursion limits
-	pandas - for displaying experimental results
-	matplotlib - for optional performance visualization
Most libraries are included with Python. Additional packages can be installed using:
bash
pip install pandas matplotlib
# How to Run the Code
## Running Using Jupyter Notebook
1. Clone or download this repository.
2. Navigate to the project directory:
bash
cd MSCS_532_B01_Assignment5
3. Start Jupyter Notebook:
bash
jupyter notebook
4. Open the notebook:
•	Quicksort Algorithm Implementation, Analysis, and Randomization.ipynb
5. Run all cells in order.
The notebook will:
-	Implement deterministic Quicksort
-	Implement randomized Quicksort
-	Test sorting correctness
-	Generate different input datasets
-	Measure execution times
-	Compare algorithm performance
# Algorithm Implementations
## 1. Deterministic Quicksort
The deterministic version uses a fixed pivot selection strategy.
### Implementation Steps
-	Select the last element as the pivot.
-	Partition the array around the pivot.
-	Recursively sort the left partition.
-	Recursively sort the right partition.
### Complexity Analysis
Case	Time Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n²)
The worst-case scenario occurs when the pivot repeatedly produces highly unbalanced partitions, such as when processing already sorted or reverse-sorted arrays.
## 2. Randomized Quicksort
The randomized version improves pivot selection by randomly choosing the pivot element.
### Implementation Steps
-	Select a random pivot from the current subarray.
-	Move the pivot into position.
-	Partition the array.
-	Recursively sort both partitions.
### Complexity Analysis
Case	Time Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n²) (extremely unlikely)
Randomized Quicksort reduces the probability of repeatedly selecting poor pivots and provides more consistent performance.
# Experimental Analysis
The algorithms were evaluated using different input distributions:
-	Random arrays
-	Sorted arrays
-	Reverse-sorted arrays
-	Arrays containing duplicate values
## Input Sizes Tested
-	1,000 elements
-	5,000 elements
-	10,000 elements
Execution time was measured using Python's:
python
time.perf_counter()
# Results and Findings
## Random Input
For randomly generated arrays, both algorithms performed efficiently because the partitions were generally balanced.
For 10,000 random elements:
-	Deterministic Quicksort: approximately 0.0118 seconds
-	Randomized Quicksort: approximately 0.0163 seconds
The results show that both approaches perform similarly when the input distribution is random.
## Sorted Input
The deterministic version showed significant performance degradation on sorted arrays because selecting a fixed pivot repeatedly created unbalanced partitions.
For 10,000 sorted elements:
- Deterministic Quicksort: approximately 4.4329 seconds
- Randomized Quicksort: approximately 0.0155 seconds
Randomized Quicksort avoided the worst-case behavior by selecting pivots independently of the input order.
## Reverse-Sorted Input
Reverse-sorted arrays produced similar results.
For 10,000 reverse-sorted elements:
-	Deterministic Quicksort: approximately 2.9418 seconds
-	Randomized Quicksort: approximately 0.0157 seconds
The deterministic implementation approached its worst-case complexity, while randomized Quicksort maintained stable performance.
## Duplicate Values
For datasets containing duplicate values, both algorithms performed efficiently.
The execution times remained close because the partitioning strategy handled repeated values effectively.
Comparison of Deterministic and Randomized Quicksort
Feature	Deterministic Quicksort	Randomized Quicksort
Pivot Selection	Last element (fixed pivot)	Random element
Best Case	O(n log n)	O(n log n)
Average Case	O(n log n)	O(n log n)
Worst Case	O(n²)	O(n²) (extremely unlikely)
Space Complexity	O(log n) average, O(n) worst case	O(log n) average, O(n) worst case
Performance on Sorted Data	Poor (can approach O(n²))	Excellent (avoids predictable bad pivots)
Performance on Random Data	Good	Good
Chance of Worst Case	Higher for specific input patterns	Extremely low due to random pivot selection
# Overall Conclusion
This project demonstrated the implementation, analysis, and comparison of deterministic and randomized versions of the Quicksort algorithm.
The deterministic implementation performs efficiently in average cases with O(n log n) time complexity but can degrade to O(n²) when poor pivot selections repeatedly create unbalanced partitions. Randomized Quicksort reduces this risk by selecting pivots randomly, resulting in an expected O(n log n) runtime across different input distributions.
The experimental results confirmed the theoretical analysis. Both algorithms performed similarly on random datasets, while randomized Quicksort significantly outperformed deterministic Quicksort on sorted and reverse-sorted inputs.
Overall, randomized Quicksort provides a more reliable and robust sorting approach when the characteristics of the input data are unknown because it minimizes the probability of encountering worst-case scenarios.
# References
1. Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022).  
   Introduction to Algorithms (4th ed.). MIT Press.
2. Sedgewick, R., & Wayne, K. (2011).  
   Algorithms (4th ed.). Addison-Wesley Professional.
3. Goodrich, M. T., Tamassia, R., & Goldwasser, M. H. (2014).  
   Data Structures and Algorithms in Pythons. Wiley.

<img width="468" height="646" alt="image" src="https://github.com/user-attachments/assets/15adc0b1-6c01-4484-b879-ba8cc1eeff0d" />
