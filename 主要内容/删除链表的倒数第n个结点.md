# 删除链表的倒数第n个结点
---
---

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution{
    public ListNode removeNthFromEnd(ListNode head, int n) {

        ListNode dummyHead = new ListNode();
        dummyHead.next = head;
        //为什么要使用双指针呢，因为光靠一个fast没法单单根据n来确定移动几步。
        //即先让fast移动(n+1)步，然后slow开始移动，直到fast为Null，即走到最后尾结点的next处。
        ListNode fast = dummyHead;
        ListNode slow = dummyHead;

        for(int i = 0;i<n+1;i++){
            fast = fast.next;
        }
        
        while(fast != null){
            fast = fast.next;
            slow = slow.next;
        }
        
        slow.next = slow.next.next;
        return dummyHead.next;
    }
}
```

