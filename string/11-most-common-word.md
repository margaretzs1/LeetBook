# Most Common Word

---

Given a paragraph and a list of banned words, return the most frequent word that is not in the list of banned words.  It is guaranteed there is at least one word that isn't banned, and that the answer is unique.

Words in the list of banned words are given in lowercase, and free of punctuation.  Words in the paragraph are not case sensitive.  The answer is in lowercase.

---

```
class Solution(object):
    def mostCommonWord(self, paragraph, banned):
        """
        :type paragraph: str
        :type banned: List[str]
        :rtype: str
        """
        import re
        words = re.split(r'\W+', paragraph.lower())


        from collections import Counter
        c = Counter(words)
        del c['']
        for word in words:
            if word in banned:
                del c[word]
        return c.most_common(1)[0][0]
```

---

### Key Learning Points

1. regular expression: import **re**
2. split by '**\W+**': non-word characters
3. from collections import **Counter**
4. Counter.**most\_common**\(n\): returns an array of tuples



