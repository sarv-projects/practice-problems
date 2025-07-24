#3:Longest Substring Without Repeating Characters<br>
Link:https://leetcode.com/problems/longest-substring-without-repeating-characters/description/<br>
Problem Statement:Given a string s, find the length of the longest substring without repeating characters.<br>
Approach: Sliding Window + HashSet<br>
Intuition:<br>
1.Maintain a window [l, r] where all characters are unique.<br>
2.If you see a duplicate s[r], shrink from the left until it's gone(very important).<br>
3.set helps track uniqueness in O(1) time.<br>
some examples to dry run:<br>
Example 1:<br>
Input: s = "abcabcbb"<br>
Output: 3<br>
Explanation: The answer is "abc", with the length of 3.<br>
<br>
Example 2:<br>
Input: s = "bbbbb"<br>
Output: 1<br>
Explanation: The answer is "b", with the length of 1.<br>
<br>
Example 3:<br>
Input: s = "pwwkew"<br>
Output: 3<br>
Explanation: The answer is "wke", with the length of 3.<br>
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.<br>