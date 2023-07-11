# DSAAssign7

# Q1

```
function isIsomorphic(s, t) {
    if (s.length !== t.length) {
        return false;
    }
    
    const sMap = new Map();
    const tMap = new Map();
    
    for (let i = 0; i < s.length; i++) {
        const sChar = s[i];
        const tChar = t[i];
        
        if (sMap.has(sChar) && sMap.get(sChar) !== tChar) {
            return false;
        }
        
        if (tMap.has(tChar) && tMap.get(tChar) !== sChar) {
            return false;
        }
        
        sMap.set(sChar, tChar);
        tMap.set(tChar, sChar);
    }
    
    return true;
}


```

# Q2

```
function isStrobogrammatic(num) {
    const map = {
        '0': '0',
        '1': '1',
        '6': '9',
        '8': '8',
        '9': '6'
    };
    
    let left = 0;
    let right = num.length - 1;
    
    while (left <= right) {
        if (!map.hasOwnProperty(num[left]) || map[num[left]] !== num[right]) {
            return false;
        }
        
        left++;
        right--;
    }
    
    return true;
}

```


# Q3 


```

function addStrings(num1, num2) {
    let i = num1.length - 1;
    let j = num2.length - 1;
    let sum = "";
    let carry = 0;
    
    while (i >= 0 || j >= 0 || carry > 0) {
        const digit1 = i >= 0 ? parseInt(num1[i]) : 0;
        const digit2 = j >= 0 ? parseInt(num2[j]) : 0;
        const currentSum = digit1 + digit2 + carry;
        
        sum = (currentSum % 10) + sum;
        carry = Math.floor(currentSum / 10);
        
        i--;
        j--;
    }
    
    return sum;
}

```

# Q4

```

function reverseWords(s) {
    const words = s.split(" ");
    
    for (let i = 0; i < words.length; i++) {
        words[i] = words[i].split("").reverse().join("");
    }
    
    return words.join(" ");
}

```

# Q5

```

function reverseStr(s, k) {
    const arr = s.split("");
    
    for (let i = 0; i < arr.length; i += 2 * k) {
        let start = i;
        let end = Math.min(i + k - 1, arr.length - 1);
        
        while (start < end) {
            let temp = arr[start];
            arr[start] = arr[end];
            arr[end] = temp;
            
            start++;
            end--;
        }
    }
    
    return arr.join("");
}

```

# Q6

```
function rotateString(s, goal) {
    if (s.length !== goal.length) {
        return false;
    }
    
    const concatenated = s + s;
    
    return concatenated.includes(goal);
}

```

# Q7

```
function backspaceCompare(s, t) {
    const stackS = [];
    const stackT = [];
    
    for (let char of s) {
        if (char === "#") {
            stackS.pop();
        } else {
            stackS.push(char);
        }
    }
    
    for (let char of t) {
        if (char === "#") {
            stackT.pop();
        } else {
            stackT.push(char);
        }
    }
    
    return stackS.join("") === stackT.join("");
}

```


# Q8

```

function checkStraightLine(coordinates) {
    const [x0, y0] = coordinates[0];
    const [x1, y1] = coordinates[1];
    const dx = x1 - x0;
    const dy = y1 - y0;
    
    for (let i = 2; i < coordinates.length; i++) {
        const [x, y] = coordinates[i];
        const currentDx = x - x0;
        const currentDy = y - y0;
        
        if (dx * currentDy !== dy * currentDx) {
            return false;
        }
    }
    
    return true;
}

```





