# LeetCode Summary

## Progress

| # | Problem | Topic | Difficulty | Solution |
|---|---|---|---|---|
| 1 | Two Sum | Hash Table | Easy | [Python](../problems/Hash%20Table/0001-two-sum.md) |
| 20 | Valid Parentheses | Stack | Easy | [Python](../problems/Stack/0020-valid-parentheses.md) |
| 49 | Group Anagrams | Hash Table / Sorting | Medium | [Python](../problems/Hash%20Table/0049-group-anagrams.md) |
| 128 | Longest Consecutive Sequence | Hash Table / Set | Medium | [Python](../problems/Hash%20Table/0128-longest-consecutive-sequence.md) |
| 155 | Min Stack | Stack / Design | Medium | [Python](../problems/Stack/0155-min-stack.md) |
| 394 | Decode String | Stack / String | Medium | [Python](../problems/Stack/0394-decode-string.md) |
| 560 | Subarray Sum Equals K | Hash Table / Prefix Sum | Medium | [Python](../problems/Hash%20Table/0560-subarray-sum-equals-k.md) |
| 739 | Daily Temperatures | Stack / Monotonic Stack | Medium | [Python](../problems/Stack/0739-daily-temperatures.md) |

## Topic Progress

| Topic | Count | Problems |
|---|---:|---|
| Hash Table | 4 | 1, 49, 128, 560 |
| Stack | 4 | 20, 155, 394, 739 |
| Total | 8 | - |

## Patterns

- Hash Table: use a dictionary or set to turn repeated lookups into O(1) average-time checks.
- Frequency Counting: convert strings or values into comparable keys, such as a 26-length count tuple.
- Set Expansion: start from the beginning of a sequence and expand only once to avoid repeated work.
- Prefix Sum: track cumulative sums and count previous prefixes to find valid subarrays in one pass.
- Stack Matching: push opening states and validate each closing state against the latest unmatched item.
- Auxiliary Stack: maintain extra state, such as the current minimum, alongside the main stack for O(1) queries.
- Nested State Stack: save the repeat count and previous string when entering a bracketed scope, then rebuild on close.
- Monotonic Stack: keep candidate indexes in order so each item is pushed and popped at most once.

## Current Focus

LeetCode Top 100 Liked problems, currently covering Hash Table and Stack patterns.
