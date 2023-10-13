---
time: 5
date: 2023-10-03
difficulty: easy
---

```ts
function containsDuplicate(nums: number[]): boolean {
    var a: Set<number> = new Set();
    var res = false;

    nums.forEach(x => {
        if (a.has(x)) {
            res = true;
        }
        a.add(x);
    });

    return res;
};
```

![[217-contains-duplicate.excalidraw]]