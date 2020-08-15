# 83删除排序链表中的重复元素

## 日期
2020年8月10

给定一个排序链表，删除所有重复的元素，使得每个元素只出现一次。

## 示例1：
>输入: 1->1->2  
输出: 1->2

## 示例2：
>输入: 1->1->2->3->3  
输出: 1->2->3

## 代码
```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
    ListNode current = head;
    while (current != null && current.next != null) {
        if (current.next.val == current.val) {
            current.next = current.next.next;
        } else {
            current = current.next;
        }
    }
    return head;
    }
}
```

