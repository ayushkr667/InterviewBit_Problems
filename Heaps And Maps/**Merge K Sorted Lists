struct Compare
{
    bool operator()(ListNode* const& a, ListNode* const& b)
    {
        return a->val > b->val;
    }
};

ListNode* Solution::mergeKLists(vector<ListNode*> &A) {
    if (A.empty())
        return NULL;
    ListNode* dummy = new ListNode(0);
    ListNode* tail = dummy;
    priority_queue<ListNode*, vector<ListNode*>, Compare> PQ;
    
    for (auto i = 0; i<A.size(); ++i)
    {
        if (A[i])
            PQ.emplace(A[i]);
    }
    
    while (!PQ.empty())
    {
        tail->next = PQ.top();
        PQ.pop();
        tail = tail->next;
        if (tail->next)
            PQ.emplace(tail->next);
    }
    return dummy->next;
}
