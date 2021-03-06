## 剑指Offer

#### [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

```rust
use std::collections::HashMap;
impl Solution {
    pub fn find_repeat_number(nums: Vec<i32>) -> i32 {
        let mut m: HashMap<i32, i32> = HashMap::new();
        for n in nums {
            let cnt = m.entry(n).or_insert(0);
            *cnt += 1;
            if *cnt > 1 {
                return n;
            }
        }
        0
    }
}
```

#### [剑指 Offer 04. 二维数组中的查找](https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)

```
impl Solution {
    pub fn find_number_in2_d_array(matrix: Vec<Vec<i32>>, target: i32) -> bool {
        if matrix.is_empty() {
            return false;
        }

        let x = matrix.len();
        let y = matrix[0].len();

        for i in 0..x {
            for j in (0..y).rev() {
                if matrix[i][j] == target {
                    return true;
                } else if matrix[i][j] < target {
                    break;
                } else if matrix[i][j] > target {
                    continue;
                }
            }
        }
        false
    }
}
```



#### [剑指 Offer 09. 用两个栈实现队列](https://leetcode-cn.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/)

```rust
struct CQueue {
    list: Vec<i32>
}


/**
 * `&self` means the method takes an immutable reference.
 * If you need a mutable reference, change it to `&mut self` instead.
 */
impl CQueue {
    fn new() -> Self {
        CQueue {
            list: Vec::new(),
        }
    }

    fn append_tail(&mut self, value: i32) {
        self.list.push(value);
    }

    fn delete_head(&mut self) -> i32 {
        return if self.list.is_empty() {
            -1
        } else {
            let i = self.list[0];
            self.list = self.list[1..self.list.len()].to_vec();
            i
        }
    }
}

/**
 * Your CQueue object will be instantiated and called as such:
 * let obj = CQueue::new();
 * obj.append_tail(value);
 * let ret_2: i32 = obj.delete_head();
 */
```



#### [剑指 Offer 10- I. 斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/)

```rust
impl Solution {
    pub fn fib(n: i32) -> i32 {
        if n == 0 {
            return 0;
        }
        if n == 1 {
            return 1;
        }

        let mut a = 0;
        let mut b = 1;
        let mut c = 1;
        for _i in 2..n {
            a = b % 1000000007;
            b = c % 1000000007;
            c = (a + b) % 1000000007;
        }
        c
    }
}
```

#### [剑指 Offer 10- II. 青蛙跳台阶问题](https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/)

```rust
impl Solution {
    pub fn num_ways(n: i32) -> i32 {
        if n == 0 {
            return 1;
        }
        if n == 1 {
            return 1;
        }

        let mut a = 1;
        let mut b = 1;
        let mut c = 2;

        for i in 2..n {
            a = b % 1000000007;
            b = c % 1000000007;
            c = (a + b) % 1000000007;
        }
        c
    }
}
```

