# Monotonic-Stack-
A monotonic stack is a stack that maintains its elements in either increasing or decreasing order — depending on the problem.
- Monotonic Increasing Stack: Top of the stack is the smallest; elements increase as you go down.
- Monotonic Decreasing Stack: Top of the stack is the largest; elements decrease as you go down.

🔍Use It
Monotonic stacks are perfect for problems like:
- Next Greater Element
- Next Smaller Element
- Stock Span
- Histogram Area
- Sliding Window Maximum
They help you:
- Avoid brute-force nested loops.
- Solve in O(n) time using stack memory.

🧠 Core Idea
As you iterate through the array:
- You pop elements from the stack that don’t satisfy the monotonic condition.
- You push the current element (or its index) to maintain the order.
- You use the stack to find the next greater/smaller element efficiently.

🧪 Example: Next Greater Element
Stack<Integer> stack = new Stack<>();
for (int i = n - 1; i >= 0; i--) {
    while (!stack.isEmpty() && stack.peek() <= arr[i]) {
        stack.pop();
    }
    ans[i] = stack.isEmpty() ? -1 : stack.peek();
    stack.push(arr[i]);
}

