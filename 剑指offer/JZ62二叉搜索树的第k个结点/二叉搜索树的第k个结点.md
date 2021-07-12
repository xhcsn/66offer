#### 二叉搜索树的第k个结点

给定一棵二叉搜索树，请找出其中的第k小的TreeNode结点。

```java
/*
public class TreeNode {
    int val = 0;
    TreeNode left = null;
    TreeNode right = null;

    public TreeNode(int val) {
        this.val = val;

    }

}
*/
//思路：二叉搜索树按照中序遍历的顺序打印出来正好就是排序好的顺序。
//     所以，按照中序遍历顺序找到第k个结点就是结果。
public class Solution {
   int index = 0; //计数器
	TreeNode KthNode(TreeNode root, int k)
    {
		if(root != null){ //中序遍历寻找第k个
			TreeNode node = KthNode(root.left,k);
			if(node != null)
				return node;
			index ++;
			if(index == k)
				return root;
			node = KthNode(root.right,k);
			if(node != null)
				return node;
		}
		return null;
    }
}
```