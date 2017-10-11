# iRonArithmetic1
Arithmetic 1 / 算法题 1

## 题目：输入一个链表的头结点，‘从尾到头’打印每个结点的值 
<pre><code>


#include "arithmetic1.h"

/* 先定义链表的结点 */
struct ListNode {
    int m_nValue;
    struct ListNode *m_pNext;
};


/*
 *  1⃣️ 循环解法
 */

void PrintListReversingly_Iteratively (struct ListNode *pHead)
{
    /* 这是一个栈，每个元素是ListNode */
    std::stack <ListNode *>  nodes;
    
    struct ListNode *pNode = pHead;
    while (pNode != NULL) {
        /* push进栈 */
        nodes.push(pNode);
        pNode = pNode->m_pNext;
    }
    while (!nodes.empty()) {
        pNode = nodes.top();
        printf("%d\t",pNode->m_nValue);
        /* pop出栈 */
        nodes.pop();
    }
    
    
}


/*
 *  2⃣️ 用递归的方法
 */

void PrintListReversingly_Recursively (struct ListNode *pHead)
{
    if (pHead != NULL) {
        
        /*
         *  如果当前结点的下一结点不为空，就先打印下一结点，如此递归下去，最后是先打印尾部
         *  但如果链表很长，有可能导致函数调用栈溢出。。
         */
        if (pHead -> m_pNext != NULL) {
            PrintListReversingly_Recursively(pHead->m_pNext);
        }
        printf("%d\t",pHead->m_nValue);
        
    }
    
}

</code></pre>
