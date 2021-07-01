# Longest Substring Without Repeating Characters
 Longest Substring Without Repeating Characters

Given a string s, find the length of the longest substring without repeating characters.

Example 1:
Input: s = "abcabcbb"
Output: 3

Explanation: The answer is "abc", with the length of 3.

Example 2:
Input: s = "bbbbb"
Output: 1

Explanation: The answer is "b", with the length of 1.

Example 3:
Input: s = "pwwkew"
Output: 3

Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

Example 4:
Input: s = ""
Output: 0

Constraints:
0 <= s.length <= 5 * 104
s consists of English letters, digits, symbols and spaces.
------------------------------------------------------------------------
Explain the solution
I'll be using a technique called sliding window. Here is how it works:

1.) Iterate over the string.

2.) Maintain two pointers to represent the left and right bound of a window. Both two pointers start at index 0.

3.) As we iterate along the string, the right pointer acts as the looping counter, while the left pointer stays where it was, unless the right pointer encounters a character that was visited before, and the left pointer is behind the visited character. When this happens, the left pointer moves to the next iteration position.

4.) To determine if a character was already visited or not, we need to maintain a hash map to store the indices of every character that the right pointer has encountered.

5.) For each iteration, we calculate the window length and compare it with the previous longest length. If the current length is longer, we update the longest length record.

6.) When the iteration finishes, we'll have the longest window length.
