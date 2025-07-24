#3:Longest Substring Without Repeating Characters
Link:https://leetcode.com/problems/longest-substring-without-repeating-characters/description/
Problem Statement:Given a string s, find the length of the longest substring without repeating characters.
Approach: Sliding Window + HashSet

class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        l = 0
        max_len = 0
        seen = set()
        
        for r in range(len(s)):
            while s[r] in seen:
                seen.remove(s[l])
                l += 1
            seen.add(s[r])
            max_len = max(max_len, r - l + 1)
        
        return max_len
Intuition:
1.Maintain a window [l, r] where all characters are unique.
2.If you see a duplicate s[r], shrink from the left until it's gone(very important).
3.set helps track uniqueness in O(1) time.
some examples to dry run:"pwwkew"-sol:3,"abcabcbb"-sol:3