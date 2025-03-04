<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="80" src="/logos/leetcode.png"></img></a>

# LeetCode OJ - Interviews Questions - Easy Problems

## contains duplicate
Problem Link: https://leetcode.com/problems/contains-duplicate

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        return len(nums) != len(set(nums))
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int> &nums) {
        set<int> set_nums(nums.begin(), nums.end());
        return size(nums) != size(set_nums);
    }
};
```

</details>

## missing number
Problem Link: https://leetcode.com/problems/missing-number

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        return n*(n+1)//2 - sum(nums)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int missingNumber(vector<int> &nums) {
        int n = size(nums);
        return n*(n+1)/2 - accumulate(nums.begin(), nums.end(), 0);
    }
};
```

</details>

## find all numbers disappeared in an array
Problem Link: https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def findDisappearedNumbers(self, nums: List[int]) -> List[int]:
        set_nums = set(nums)
        disappeared_num  = []
        for i in range(1, len(nums)+1):
            if i not in set_nums:
                disappeared_num.append(i)
        return disappeared_num
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int> &nums) {
        set<int> set_nums(nums.begin(), nums.end());
        vector<int> disappeared_num;
        for (int i=1; i<size(nums)+1; i++) {
            if (set_nums.find(i) == set_nums.end())
                disappeared_num.push_back(i);
        }
        return disappeared_num;
    }
};
```

</details>

## single number
Problem Link: https://leetcode.com/problems/single-number

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        cnt_nums = [0] * int(6e4)
        for i in nums:
            cnt_nums[i+int(3e4)] += 1
        for i in nums:
            if cnt_nums[i+int(3e4)] == 1:
                return i
        return 0
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int singleNumber(vector<int> &nums) {
        vector<int> cnt_nums(6e4, 0);
        for (int i:nums)
            cnt_nums[i+int(3e4)] ++;
        for (int i:nums) {
            if (cnt_nums[i+int(3e4)] == 1)
                return i;
        }
        return 0;
    }
};
```

</details>

## climbing stairs
Problem Link: https://leetcode.com/problems/climbing-stairs

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def climbStairs(self, n: int) -> int:
        memo = [0] * 46
        memo[0] = memo[1] = 1
        for i in range(2, n+1):
            memo[i] = memo[i-1] + memo[i-2]
        return memo[n]
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int climbStairs(int n) {
        vector<int> memo(46, 0);
        memo[0] = memo[1] = 1;
        for (int i=2; i<n+1; i++)
            memo[i] = memo[i-1] + memo[i-2];
        return memo[n];
    }
};
```

</details>

## best time to buy and sell stock
Problem Link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        min_vals = [1e4] * int(1e5+1)
        max_vals = [0]   * int(1e5+1)
        for i in range(len(prices)):
            min_vals[i+1] = min(min_vals[i], prices[i])
        for i in range(len(prices)-1, -1, -1):
            max_vals[i+1] = max(max_vals[i], prices[i])
        max_profit = 0
        for i in range(1, len(prices)+1):
            max_profit = max(max_profit, max_vals[i]-min_vals[i])
        return max_profit
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int maxProfit(vector<int> &prices) {
        vector<int> min_vals(1e5+1, 1e4);
        vector<int> max_vals(1e5+1, 0);
        for (int i=0; i<size(prices); i++)
            min_vals[i+1] = min(min_vals[i], prices[i]);
        for (int i=size(prices)-1; i>-1; i--)
            max_vals[i+1] = max(max_vals[i], prices[i]);
        int max_profit = 0;
        for (int i=1; i<size(prices)+1; i++)
            max_profit = max(max_profit, max_vals[i]-min_vals[i]);
        return max_profit;
    }
};
```

</details>

## maximum subarray
Problem Link: https://leetcode.com/problems/maximum-subarray

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        curr_subarray_sum = 0
        max_subarray_sum = nums[0]
        for i in nums:
            curr_subarray_sum = max(curr_subarray_sum, 0)
            curr_subarray_sum += i
            max_subarray_sum = max(max_subarray_sum, curr_subarray_sum)
        return max_subarray_sum
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int maxSubArray(vector<int> &nums) {
        int curr_subarray_sum = 0;
        int max_subarray_sum = nums[0];
        for (int i : nums) {
            curr_subarray_sum = max(curr_subarray_sum, 0);
            curr_subarray_sum += i;
            max_subarray_sum = max(max_subarray_sum, curr_subarray_sum);
        }
        return max_subarray_sum;
    }
};
```

</details>

## range sum query immutable
Problem Link: https://leetcode.com/problems/range-sum-query-immutable

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class NumArray:
    def __init__(self, nums: List[int]):
        self.cumulative_sum = nums.copy()
        self.cumulative_sum.insert(0, 0)
        for i in range(1, len(nums)+1):
            self.cumulative_sum[i] += self.cumulative_sum[i-1]

    def sumRange(self, left: int, right: int) -> int:
        return self.cumulative_sum[right+1] - self.cumulative_sum[left]
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class NumArray {
    vector<int> cumulative_sum;
public:
    NumArray(vector<int> &nums) {
        cumulative_sum.assign(nums.begin(), nums.end());
        cumulative_sum.insert(cumulative_sum.begin(), 0);
        for (int i=1; i<size(nums)+1; i++)
            cumulative_sum[i] += cumulative_sum[i-1];
    }
    int sumRange(int left, int right) {
        return cumulative_sum[right+1] - cumulative_sum[left];
    }
};
```

</details>

## counting bits
Problem Link: https://leetcode.com/problems/counting-bits

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def countBits(self, n: int) -> List[int]:
        cnt_ones = [0] * (n+1)
        for i in range(n+1):
            x = i
            cnt = 0
            while x > 0:
                cnt += x%2
                x //= 2
            cnt_ones[i] = cnt
        return cnt_ones
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> cnt_ones (n+1, 0);
        for (int i=0; i<n+1; i++) {
            int x = i;
            int cnt = 0;
            while (x > 0) {
                cnt += x%2;
                x /= 2;
            }
            cnt_ones[i] = cnt;
        }
        return cnt_ones;
    }
};
```

</details>

## linked list cycle
Problem Link: https://leetcode.com/problems/linked-list-cycle

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        curr1 = head
        curr2 = head
        while curr2 and curr2.next:
            curr2 = curr2.next.next
            curr1 = curr1.next
            if curr1 == curr2:
                return True
        return False
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    bool hasCycle(ListNode *head) {
        ListNode *curr1 = head;
        ListNode *curr2 = head;
        while (curr2 and curr2->next) {
            curr2 = curr2->next->next;
            curr1 = curr1->next;
            if (curr1 == curr2)
                return true;
        }
        return false;
    }
};
```

</details>

## middle of the linked list
Problem Link: https://leetcode.com/problems/middle-of-the-linked-list

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        curr1 = head
        curr2 = head
        while curr2 and curr2.next:
            curr2 = curr2.next.next
            curr1 = curr1.next
        return curr1
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    ListNode* middleNode(ListNode *head) {
        ListNode *curr1 = head;
        ListNode *curr2 = head;
        while (curr2 and curr2->next) {
            curr2 = curr2->next->next;
            curr1 = curr1->next;
        }
        return curr1;
    }
};
```

</details>

## palindrome linked list
Problem Link: https://leetcode.com/problems/palindrome-linked-list

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        stk = []
        curr = head
        while curr:
            stk.append(curr.val)
            curr = curr.next
        stk = stk[::-1]
        i = 0
        curr = head
        while curr:
            if stk[i] != curr.val:
                return False
            curr = curr.next
            i += 1
        return True
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    bool isPalindrome(ListNode *head) {
        vector<int> stk;
        ListNode *curr = head;
        while (curr) {
            stk.push_back(curr->val);
            curr = curr->next;
        }
        reverse(stk.begin(), stk.end());
        int i = 0;
        curr = head;
        while (curr) {
            if (stk[i] != curr->val)
                return false;
            curr = curr->next;
            i++;
        }
        return true;
    }
};
```

</details>

## remove linked list elements
Problem Link: https://leetcode.com/problems/remove-linked-list-elements

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def removeElements(self, head: Optional[ListNode], val: int) -> Optional[ListNode]:
        curr = head
        while curr and curr.next:
            if curr.next.val == val:
                temp = curr.next
                curr.next = curr.next.next
                del temp
            else:
                curr = curr.next
        if head and head.val == val:
            temp = head
            head = head.next
            del temp
        return head
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    ListNode* removeElements(ListNode *head, int val) {
        ListNode *curr = head;
        while (curr and curr->next) {
            if (curr->next->val == val) {
                ListNode *temp = curr->next;
                curr->next = curr->next->next;
                delete temp;
            }
            else
                curr = curr->next;
        }
        if (head and head->val == val) {
            ListNode *temp = head;
            head = head->next;
            delete temp;
        }
        return head;
    }
};
```

</details>

## remove duplicates from sorted list
Problem Link: https://leetcode.com/problems/remove-duplicates-from-sorted-list

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:
        curr = head
        while curr and curr.next:
            if curr.val == curr.next.val:
                temp = curr.next
                curr.next = curr.next.next
                del temp
            else:
                curr = curr.next
        return head
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode *head) {
        ListNode *curr = head;
        while (curr and curr->next) {
            if (curr->val == curr->next->val) {
                ListNode *temp = curr->next;
                curr->next = curr->next->next;
                delete temp;
            }
            else
                curr = curr->next;
        }
        return head;
    }
};
```

</details>

## reverse linked list
Problem Link: https://leetcode.com/problems/reverse-linked-list

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if head == None:
            return head
        prv = None
        cur = head
        nxt = cur.next
        while nxt:
            cur.next = prv
            prv = cur
            cur = nxt
            nxt = nxt.next
        cur.next = prv
        return cur
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode *head) {
        if (head == NULL)
            return head;
        ListNode *prv = NULL;
        ListNode *cur = head;
        ListNode *nxt = cur->next;
        while (nxt) {
            cur->next = prv;
            prv = cur;
            cur = nxt;
            nxt = nxt->next;
        }
        cur->next = prv;
        return cur;
    }
};
```

</details>

## merge two sorted lists
Problem Link: https://leetcode.com/problems/merge-two-sorted-lists

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        head = ListNode()
        curr = head
        while list1 and list2:
            if list1.val <= list2.val:
                curr.next = list1
                list1 = list1.next
            else:
                curr.next = list2
                list2 = list2.next
            curr = curr.next
        if list1:
            curr.next = list1
        if list2:
            curr.next = list2
        return head.next
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode *list1, ListNode *list2) {
        ListNode *head = new ListNode();
        ListNode *curr = head;
        while (list1 and list2) {
            if (list1->val <= list2->val)
                curr->next = list1,
                list1 = list1->next;
            else
                curr->next = list2,
                list2 = list2->next;
            curr = curr->next;
        }
        if (list1)
            curr->next = list1;
        if (list2)
            curr->next = list2;
        return head->next;
    }
};
```

</details>

## meeting rooms
Problem Link: https://leetcode.com/problems/meeting-rooms

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python

```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp

```

</details>

## binary search
Problem Link: https://leetcode.com/problems/binary-search

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        f, e = 0, len(nums)-1
        while f <= e:
            m = (f+e)//2
            if nums[m] == target:
                return m
            if nums[m] > target:
                e = m-1
            else:
                f = m+1
        return -1
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int search(vector<int> &nums, int target) {
        int f = 0, e = size(nums)-1;
        while (f <= e) {
            int m = (f+e)/2;
            if (nums[m] == target)
                return m;
            if (nums[m] > target)
                e = m-1;
            else
                f = m+1;
        }
        return -1;
    }
};
```

</details>

## find smallest letter greater than target
Problem Link: https://leetcode.com/problems/find-smallest-letter-greater-than-target

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def nextGreatestLetter(self, letters: List[str], target: str) -> str:
        f, e = 0, len(letters)-1
        while f <= e:
            m = (f+e)//2
            if letters[m] > target:
                e = m-1
            else:
                f = m+1
        return letters[f%len(letters)]
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    char nextGreatestLetter(vector<char> &letters, char target) {
        int f = 0, e = size(letters)-1;
        while (f <= e) {
            int m = (f+e)/2;
            if (letters[m] > target)
                e = m-1;
            else
                f = m+1;
        }
        return letters[f%size(letters)];
    }
};
```

</details>

## peak index in a mountain array
Problem Link: https://leetcode.com/problems/peak-index-in-a-mountain-array/

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def peakIndexInMountainArray(self, arr: List[int]) -> int:
        f, e = 0, len(arr)-1
        while f <= e:
            m = (f+e)//2
            if arr[m] < arr[m+1]:
                f = m+1
            else:
                e = m-1
        return f
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int peakIndexInMountainArray(vector<int> &arr) {
        int f = 0, e = size(arr)-1;
        while (f <= e) {
            int m = (f+e)/2;
            if (arr[m] < arr[m+1])
                f = m+1;
            else
                e = m-1;
        }
        return f;
    }
};
```

</details>

## average of levels in binary tree
Problem Link: https://leetcode.com/problems/average-of-levels-in-binary-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def averageOfLevels(self, root: Optional[TreeNode]) -> List[float]:
        sums = [0] * int(1e4)
        cnts = [0] * int(1e4)

        def dfs(curr, level):
            if curr == None:
                return
            sums[level] += curr.val
            cnts[level] += 1
            dfs(curr.left, level+1)
            dfs(curr.right, level+1)

        dfs(root, 0)
        avgs = [sums[i]/cnts[i] for i in range(int(1e4)) if cnts[i] != 0]
        return avgs
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    vector<long long> sums;
    vector<long long> cnts;

    void dfs(TreeNode *curr, int level) {
        if (curr == NULL)
            return;
        sums[level] += curr->val;
        cnts[level] ++;
        dfs(curr->left, level+1);
        dfs(curr->right, level+1);
    }
public:
    vector<double> averageOfLevels(TreeNode *root) {
        sums.assign(1e4, 0LL);
        cnts.assign(1e4, 0LL);
        dfs(root, 0);
        vector<double> avgs;
        for (int i=0; i<1e4; i++) {
            if (cnts[i] != 0)
                avgs.push_back(1.0*sums[i]/cnts[i]);
        }
        return avgs;
    }
};
```

</details>

## minimum depth of binary tree
Problem Link: https://leetcode.com/problems/minimum-depth-of-binary-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def minDepth(self, root: Optional[TreeNode]) -> int:
        def dfs(curr):
            if curr == None:
                return 0
            if curr.left == None:
                return dfs(curr.right)+1
            if curr.right == None:
                return dfs(curr.left)+1
            return min(dfs(curr.left), dfs(curr.right)) + 1

        return dfs(root)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    int dfs(TreeNode *curr) {
        if (curr == NULL)
            return 0;
        if (curr->left == NULL)
            return dfs(curr->right)+1;
        if (curr->right == NULL)
            return dfs(curr->left)+1;
        return min(dfs(curr->left), dfs(curr->right)) + 1;
    }
public:
    int minDepth(TreeNode *root) {
        return dfs(root);
    }
};
```

</details>

## same tree
Problem Link: https://leetcode.com/problems/same-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        def dfs(cur1, cur2):
            if cur1 == None and cur2 == None:
                return True
            if cur1 == None or cur2 == None:
                return False
            if cur1.val != cur2.val:
                return False
            return dfs(cur1.left, cur2.left) and dfs(cur1.right, cur2.right)

        return dfs(p, q)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    bool dfs(TreeNode* cur1, TreeNode* cur2) {
        if (cur1 == NULL and cur2 == NULL)
            return true;
        if (cur1 == NULL or cur2 == NULL)
            return false;
        if (cur1->val != cur2->val)
            return false;
        return dfs(cur1->left, cur2->left) and dfs(cur1->right, cur2->right);
    }
public:
    bool isSameTree(TreeNode* p, TreeNode* q) {
        return dfs(p, q);
    }
};
```

</details>

## path sum
Problem Link: https://leetcode.com/problems/path-sum

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:
        def dfs(curr, curr_sum):
            if curr == None:
                return curr_sum == 0
            is_valid_left = dfs(curr.left, curr_sum-curr.val)
            is_valid_right = dfs(curr.right, curr_sum-curr.val)
            if curr.right == None:
                return is_valid_left
            if curr.left == None:
                return is_valid_right
            return is_valid_left or is_valid_right

        if root == None:
            return False
        return dfs(root, targetSum)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    bool dfs(TreeNode *curr, int curr_sum) {
        if (curr == NULL)
            return curr_sum == 0;
        bool is_valid_left = dfs(curr->left, curr_sum-curr->val);
        bool is_valid_right = dfs(curr->right, curr_sum-curr->val);
        if (curr->right == NULL)
            return is_valid_left;
        if (curr->left == NULL)
            return is_valid_right;
        return is_valid_left or is_valid_right;
    }
public:
    bool hasPathSum(TreeNode *root, int targetSum) {
        if (root == NULL)
            return false;
        return dfs(root, targetSum);
    }
};
```

</details>

## maximum depth of binary tree
Problem Link: https://leetcode.com/problems/maximum-depth-of-binary-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        def dfs(curr):
            if curr == None:
                return 0
            return max(dfs(curr.left), dfs(curr.right)) + 1

        return dfs(root)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    int dfs(TreeNode *curr) {
        if (curr == NULL)
            return 0;
        return max(dfs(curr->left), dfs(curr->right)) + 1;
    }
public:
    int maxDepth(TreeNode *root) {
        return dfs(root);
    }
};
```

</details>

## diameter of binary tree
Problem Link: https://leetcode.com/problems/diameter-of-binary-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        def dfs(curr):
            if curr == None:
                return 0
            return max(dfs(curr.left), dfs(curr.right)) + 1

        def max_diameter(curr):
            if curr == None:
                return 0
            return max(max_diameter(curr.left), max_diameter(curr.right),
                       dfs(curr.left) + dfs(curr.right))

        return max_diameter(root)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    int dfs(TreeNode *curr) {
        if (curr == NULL)
            return 0;
        return max(dfs(curr->left), dfs(curr->right)) + 1;
    }
    int max_diameter(TreeNode *curr) {
        if (curr == NULL)
            return 0;
        return max(max(max_diameter(curr->left), max_diameter(curr->right)),
                   dfs(curr->left) + dfs(curr->right));
    }
public:
    int diameterOfBinaryTree(TreeNode *root) {
        return max_diameter(root);
    }
};
```

</details>

## merge two binary trees
Problem Link: https://leetcode.com/problems/merge-two-binary-trees

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def mergeTrees(self, root1: Optional[TreeNode], root2: Optional[TreeNode]) -> Optional[TreeNode]:
        def dfs(cur, cur1, cur2):
            if cur1 == None and cur2 == None:
                return None
            if cur1 == None:
                return cur2
            if cur2 == None:
                return cur1
            cur = TreeNode(cur1.val + cur2.val, TreeNode(), TreeNode())
            cur.left = dfs(cur.left, cur1.left, cur2.left)
            cur.right = dfs(cur.right, cur1.right, cur2.right)
            return cur

        root = TreeNode()
        return dfs(root, root1, root2)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    TreeNode* dfs(TreeNode* cur, TreeNode* cur1, TreeNode* cur2) {
        if (cur1 == NULL and cur2 == NULL)
            return NULL;
        if (cur1 == NULL)
            return cur2;
        if (cur2 == NULL)
            return cur1;
        cur = new TreeNode(cur1->val + cur2->val, new TreeNode(), new TreeNode());
        cur->left = dfs(cur->left, cur1->left, cur2->left);
        cur->right = dfs(cur->right, cur1->right, cur2->right);
        return cur;
    }
public:
    TreeNode* mergeTrees(TreeNode *root1, TreeNode *root2) {
        TreeNode *root = new TreeNode();
        return dfs(root, root1, root2);
    }
};
```

</details>

## lowest common ancestor of a binary search tree
Problem Link: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def lowestCommonAncestor(self, root: 'TreeNode', p: 'TreeNode', q: 'TreeNode') -> 'TreeNode':
        def LCA(curr, p, q):
            if curr == None:
                return None
            if p < curr.val and curr.val < q:
                return curr
            if curr.val > max(p, q):
                return LCA(curr.left, p, q)
            if curr.val < min(p, q):
                return LCA(curr.right, p, q)
            return curr

        return LCA(root, p.val, q.val)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    TreeNode* LCA(TreeNode *curr, int p, int q) {
        if (curr == NULL)
            return NULL;
        if (p < curr->val and curr->val < q)
            return curr;
        if (curr->val > max(p, q))
            return LCA(curr->left, p, q);
        if (curr->val < min(p, q))
            return LCA(curr->right, p, q);
        return curr;
    }
public:
    TreeNode* lowestCommonAncestor(TreeNode *root, TreeNode* p, TreeNode* q) {
        return LCA(root, p->val, q->val);
    }
};
```

</details>

## subtree of another tree
Problem Link: https://leetcode.com/problems/subtree-of-another-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        def isSameTree(cur1, cur2):
            if cur1 == None and cur2 == None:
                return True
            if cur1 == None or cur2 == None:
                return False
            if cur1.val != cur2.val:
                return False
            return isSameTree(cur1.left, cur2.left) and isSameTree(cur1.right, cur2.right)

        def find_subtree(curr, subRoot):
            if curr == None:
                return False
            if isSameTree(curr, subRoot):
                return True
            return find_subtree(curr.left, subRoot) or find_subtree(curr.right, subRoot)

        return find_subtree(root, subRoot)
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    bool isSameTree(TreeNode* cur1, TreeNode* cur2) {
        if (cur1 == NULL and cur2 == NULL)
            return true;
        if (cur1 == NULL or cur2 == NULL)
            return false;
        if (cur1->val != cur2->val)
            return false;
        return isSameTree(cur1->left, cur2->left) and isSameTree(cur1->right, cur2->right);
    }
    bool find_subtree(TreeNode *curr, TreeNode* subRoot) {
        if (curr == NULL)
            return false;
        if (isSameTree(curr, subRoot))
            return true;
        return find_subtree(curr->left, subRoot) or find_subtree(curr->right, subRoot);
    }
public:
    bool isSubtree(TreeNode *root, TreeNode* subRoot) {
        return find_subtree(root, subRoot);
    }
};
```

</details>

## invert binary tree
Problem Link: https://leetcode.com/problems/invert-binary-tree

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        def dfs(curr):
            if curr == None:
                return
            curr.left, curr.right = curr.right, curr.left
            dfs(curr.left)
            dfs(curr.right)

        dfs(root)
        return root
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    void dfs(TreeNode *curr) {
        if (curr == NULL)
            return;
        TreeNode* temp = curr->left;
        curr->left = curr->right;
        curr->right = temp;
        dfs(curr->left);
        dfs(curr->right);
    }
public:
    TreeNode* invertTree(TreeNode *root) {
        dfs(root);
        return root;
    }
};
```

</details>

## two sum
Problem Link: https://leetcode.com/problems/two-sum

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        idx = {}
        for i in range(len(nums)):
            idx[nums[i]] = idx.get(nums[i], [])
            idx[nums[i]].append(i)
        res = []
        for i in nums:
            if i in idx and target - i in idx:
                if i == target - i and len(idx[i]) == 1:
                    continue
                res = [idx[i][0], idx[target - i][-1]]
                break
        return res
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int> &nums, int target) {
        map<int, vector<int>> idx;
        for (int i=0; i<size(nums); i++)
            idx[nums[i]].push_back(i);
        vector<int> res;
        for (int i : nums) {
            if (idx.find(i) != idx.end() and idx.find(target - i) != idx.end()) {
                if (i == target - i and size(idx[i]) == 1)
                    continue;
                res = {idx[i][0], idx[target - i][size(idx[i])-1]};
                break;
            }
        }
        return res;
    }
};
```

</details>

## squares of a sorted array
Problem Link: https://leetcode.com/problems/squares-of-a-sorted-array

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        return sorted([i*i for i in nums])
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    vector<int> sortedSquares(vector<int> &nums) {
        vector<int> res(nums);
        for (int &i : res)
            i *= i;
        sort(res.begin(), res.end());
        return res;
    }
};
```

</details>

## backspace string compare
Problem Link: https://leetcode.com/problems/backspace-string-compare

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def backspaceCompare(self, s: str, t: str) -> bool:
        def move(w, idx, cnt):
            while idx != -1 and w[idx] == '#':
                cnt += 1
                idx -= 1
            while idx != -1 and cnt > 0 and w[idx] != '#':
                cnt -= 1
                idx -= 1
            return idx, cnt

        i, j = len(s)-1, len(t)-1
        cnt_s, cnt_t = 0, 0
        prev_i, prev_j = -1, -1
        while i != prev_i and j != prev_j:
            while i != prev_i:
                prev_i = i
                i, cnt_s = move(s, i, cnt_s)
            while j != prev_j:
                prev_j = j
                j, cnt_t = move(t, j, cnt_t)
            if i >= 0 and j >= 0:
                if s[i] != t[j]:
                    return False
                else:
                    i -= 1
                    j -= 1
        return i == -1 and j == -1
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
    void move(string w, int &idx, int &cnt) {
        while (idx != -1 and w[idx] == '#') {
            cnt += 1;
            idx -= 1;
        }
        while (idx != -1 and cnt > 0 and w[idx] != '#') {
            cnt -= 1;
            idx -= 1;
        }
    }
public:
    bool backspaceCompare(string s, string t) {
        int i = size(s)-1, j = size(t)-1;
        int cnt_s = 0, cnt_t = 0;
        int prev_i = -1, prev_j = -1;
        while (i != prev_i and j != prev_j) {
            while (i != prev_i) {
                prev_i = i;
                move(s, i, cnt_s);
            }
            while (j != prev_j) {
                prev_j = j;
                move(t, j, cnt_t);
            }
            if (i >= 0 and j >= 0) {
                if (s[i] != t[j])
                    return false;
                else
                    i --,
                    j --;
            }
        }
        return i == -1 and j == -1;
    }
};
```

</details>

## index pairs of a string
Problem Link: https://leetcode.com/problems/index-pairs-of-a-string

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python

```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp

```

</details>

## majority element
Problem Link: https://leetcode.com/problems/majority-element

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        cnt = {}
        for i in nums:
            cnt[i] = cnt.get(i, 0) + 1
        for i, j in cnt.items():
            if j > len(nums)//2:
                return i
        return -1
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    int majorityElement(vector<int> &nums) {
        map<int, int> cnt;
        for (int i : nums)
            cnt[i] ++;
        for (auto &[i, j] : cnt) {
            if (j > size(nums)/2)
                return i;
        }
        return -1;
    }
};
```

</details>

## convert 1d array into 2d array
Problem Link: https://leetcode.com/problems/convert-1d-array-into-2d-array

<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/python.png"></img></a>
<details>
    <summary><h5>Python Solution</h5></summary>

```python
class Solution:
    def construct2DArray(self, original: List[int], m: int, n: int) -> List[List[int]]:
        if n*m != len(original):
            return []
        res = [[[0] for i in range(n)] for j in range(m)]
        for i in range(len(original)):
            res[i//n][i%n] = original[i]
        return res
```

</details>
<a href="/level-4/leetcode/interviews-questions/solutions/easy-problems.md"><img align="right" width="50" src="https://github.com/cs-MohamedAyman/cs-MohamedAyman/blob/main/repos-logos/cpp.png"></img></a>
<details>
    <summary><h5>CPP Solution</h5></summary>

```cpp
class Solution {
public:
    vector<vector<int>> construct2DArray(vector<int> &original, int m, int n) {
        if (n*m != size(original))
            return {};
        vector<vector<int>> res(m);
        for (vector<int> &i : res)
            i = vector<int>(n);
        for (int i=0; i<size(original); i++)
            res[i/n][i%n] = original[i];
        return res;
    }
};
```

</details>
