#### 链表中倒数最后k个结点
```Java
import java.util.*;

/*
 * public class ListNode {
 *   int val;
 *   ListNode next = null;
 *   public ListNode(int val) {
 *     this.val = val;
 *   }
 * }
 */

public class Solution {
    /**
     * 代码中的类名、方法名、参数名已经指定，请勿修改，直接返回方法规定的值即可
     *
     * 
     * @param pHead ListNode类 
     * @param k int整型 
     * @return ListNode类
     */
    public ListNode FindKthToTail (ListNode pHead, int k) {
        // write code here
        if(pHead == null) return pHead;
        ListNode first = pHead;
        ListNode second = pHead;
        while(k > 0){
            if(first == null){
                return null;
            }
            first = first.next;
            k--;
        }
        while(first != null){
            first = first.next;
            second = second.next;
        }
        return second;
    }
}
```