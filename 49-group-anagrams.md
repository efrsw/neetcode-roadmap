---
time: 25
date: 2023-10-14
difficulty: easy
---

```ts
function groupAnagrams(strs: string[]): string[][] {
    let res: string[][] = [];
    let d: Map<string, string[]> = new Map();

    for(let s of strs) {
        let t = [...s];
        let key = t.sort().join("");
        d.has(key) ? d.get(key).push(s) : d.set(key, [s]);
    }

    for(let v of d.values()) {
        res.push(v);
    }
    return res;
};
```

В качетве решения за O(n\*m) можно сделать следующее: 
1. На каждой итерации цикла создавать массив из 26 элементов
2. Проходиться по строчке и добавлять в соответсвующий индекс вектора 1 за каждую встреченную букву
3. Далее полученная строка может служить ключем в словаре