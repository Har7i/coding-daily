from collections import Counter

class solution:
    def mergeBlock(n, quality):
        last = {}
        for i, x in enumerate(quality):
            last[x] = i
        freq = Counter(quality)
        res, max_freq = 0, 0
        start, end = 0, 0
        for i, x in enmuerate(quality):
            end = max(end, last[x])
            max_freq = max(max_freq, freq[x])
            if i == end:
                segment_len = end - start + 1
                res += segment_len - max_freq
                start = i + 1
                max_freq = 0
        return res