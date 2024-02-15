# overview
The problem involves finding the largest possible perimeter of a polygon that can be formed using a given array of positive integers, where each integer represents the length of a side of the polygon. The conditions for forming a valid polygon are that it must be a closed plane figure with at least 3 sides, and the length of the longest side must be smaller than the sum of the lengths of the other sides.

In real-life scenarios, this problem can be related to optimization challenges in fields such as manufacturing or construction. For example, in manufacturing, where materials are limited, the problem can be interpreted as finding the most efficient way to use available resources to create a closed structure with a maximal perimeter. The problem highlights the importance of understanding geometric constraints and optimizing resource utilization.


# Approach sorting
The problem revolves around the construction of polygons from a given array of positive integers. The aim is to determine the largest possible perimeter of a polygon that can be formed using elements from the array and to return -1 if it is not feasible to create a polygon. A polygon, in this context, is defined as a closed plane figure with at least three sides, where the length of the longest side is less than the sum of the remaining sides.

To approach this problem intuitively, let's consider the nature of polygons and their side lengths. According to the problem description, a valid polygon consists of sides where the longest side is smaller than the sum of its other sides.

Conversely, if you have k (k >= 3) positive real numbers a1, a2, a3, ..., ak where a1 <= a2 <= a3 <= ... <= ak and a1 + a2 + a3 + ... + ak-1 > ak, then there always exists a polygon with k sides whose lengths are a1, a2, a3, ..., ak


This concept provides a key insight into how we might construct a valid polygon from the given array of positive integers. The requirement that the largest side must be smaller than the sum of the remaining sides suggests the need to establish an order among the side lengths. In other words, the challenge is to find a systematic way to consider side lengths such that the largest one is positioned last, allowing us to check if it is smaller than the sum of the others.

We can begin by sorting the array, which allows us to consider the elements in ascending order, facilitating a systematic examination of possible side lengths. The sorting operation ensures that we iterate through the array in increasing order of side lengths, so we encounter smaller sides first and the longest side last, which is useful because the longest side should be smaller than the sum of the others.

Now, as we traverse the sorted array, we need to maintain a running sum of the previously encountered elements. This sum represents the cumulative length of the sides that we have already considered. As we move through the array, we evaluate each element in relation to the sum of the previously encountered elements.

The pivotal insight of this algorithm is that if the current element is smaller than the sum of the previous elements, we can form a valid polygon because adding the current element to the sum satisfies the condition that the longest side is smaller than the sum of the others.

Therefore, the algorithm keeps track of the maximum possible perimeter by updating the answer whenever a valid combination of sides is found. This ensures that we always have the largest perimeter encountered so far.

To handle cases where a valid combination of sides to form a polygon is not found, the algorithm initializes the variable ans to -1. The algorithm ensures that if no valid combination is encountered during the iteration through the sorted array, the value of ans remains unchanged. Consequently, upon completion of the loop, the algorithm returns -1, indicating the absence of a feasible polygon with the given array of positive integers.
