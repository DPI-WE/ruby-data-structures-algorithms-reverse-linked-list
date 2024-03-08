# Reverse a Linked List ↩️

## The problem
Write a program that:

- takes the head of a singly linked list
- reverses the list
- returns the new head of the reversed list

Understanding this problem requires familiarity with the concept of a *linked list*, a fundamental data structure that consists of a sequence of elements, each contained in a "node." Each node holds a value and a pointer to the next node in the sequence, with the last node pointing to nil (or null, depending on your programming language).

Consider a linked list 1 -> 2 -> 3 -> nil. Reversing this list would result in a new list 3 -> 2 -> 1 -> nil.

## Understand the Problem
Before diving into the main challenge, let's simplify the task to ensure clarity on linked lists and the concept of reversing them.

- Consider the linked list 1 -> 2 -> nil. After reversing it, which element becomes the new head of the list?
- 1
  - Incorrect. Reversing the list changes the head to the last element before reversal. Re-evaluate the pointers.
- 2
  - Correct! When the list is reversed, 2, being the last element before reversal, becomes the new head.
- nil
  - Incorrect. nil represents the absence of a node or the end of a list, not a valid element that can serve as a head.
- None of the above
  - Incorrect. One of the given options correctly identifies the new head of the reversed list.
{: .choose_best #simple_reversal title="Consider the linked list 1 -> 2 -> nil. After reversing it, which element becomes the new head of the list?" points="1" answer="2" }

## Think Aloud
When tackling this problem, try talking it out with a rubber duck 🦆 to verbalize your thought process.

## Test your code
```ruby
class ListNode
  attr_accessor :val, :next

  def initialize(val = 0, _next = nil)
    @val = val
    @next = _next
  end
end

def reverse_list(head)

end
```
{: .repl #reverse_linked_list title="Reverse a Linked List" readonly_lines="[1,2,3,4,5,6,7]"}

```ruby
describe "Reverse Linked List" do
  it "reverses the list 1 -> 2 -> 3 -> nil to 3 -> 2 -> 1 -> nil" do
    list = array_to_list([1, 2, 3])
    reversed_list_head = reverse_list(list)
    expect(list_to_array(reversed_list_head)).to eq([3, 2, 1])
  end
end
```
{: .repl-test #reverse_linked_list_test_1 for="reverse_linked_list" title="Reverse Linked List reverses 1 -> 2 -> 3" points="1"}

```ruby
describe "Reverse Linked List" do
  it "returns nil for an empty list" do
    reversed_list_head = reverse_list(nil)
    expect(reversed_list_head).to eq(nil)
  end
end
```
{: .repl-test #reverse_linked_list_test_2 for="reverse_linked_list" title="Reverse Linked List handles empty list" points="1"}

```ruby
describe "Reverse Linked List" do
  it "properly handles a list with a single element" do
    list = array_to_list([1])
    reversed_list_head = reverse_list(list)
    expect(list_to_array(reversed_list_head)).to eq([1])
  end
end
```
{: .repl-test #reverse_linked_list_test_3 for="reverse_linked_list" title="Reverse Linked List handles single element list" points="1"}

## Tips and Clues for Solving the Problem
- **Pointer Manipulation**: Understanding how to manipulate pointers is crucial. You'll need to keep track of the previous node as you iterate through the list to reverse the direction of the pointers.
- **Iterative Approach**: An iterative approach might utilize a loop to reverse the pointers one by one, resulting in linear time complexity (O(n)) and constant space complexity (O(1)).
- **Recursive Approach**: A recursive strategy might require calling a function that reverses the rest of the list and then adjusts the current pointers accordingly. This has space complexity ramifications since it adds frames to the call stack, resulting in O(n) space complexity.
- **Edge Cases**: Always consider the edge cases, such as an empty list or a list with only one element. Your solution should gracefully handle these.

## Quiz
- What is a key concept in reversing a linked list?
- Manipulating values within nodes
  - Incorrect. While nodes do contain values, reversing a linked list focuses on changing the pointers, not the values themselves.
- Changing the direction of pointers
  - Correct! The essence of reversing a linked list lies in adjusting the pointers so that each node points to its predecessor.
- Increasing list size
  - Incorrect. Reversing a list does not affect its size; it only changes the order of the nodes.
- Decreasing list size
  - Incorrect. Reversing a list maintains the same number of nodes; it merely inverts their order.
{: .choose_best #key_concept title="What is a key concept in reversing a linked list?" points="1" answer="2" }

- Which approach to reversing a linked list does not use additional space on the call stack?
- Recursive approach
  - Incorrect. Recursion involves adding frames to the call stack for each recursive call, which uses additional space.
- Iterative approach
  - Correct! An iterative approach uses a loop to reverse the list and does not add extra frames to the call stack, making it more space-efficient in this context.
- Both approaches use additional space
  - Incorrect. While recursion uses additional space on the call stack, an iterative approach does not.
{: .choose_best #approach_space title="Which approach to reversing a linked list does not use additional space on the call stack?" points="1" answer="2" }

## Conclusion
In this lesson, we've tackled the problem of reversing a singly linked list. This challenge allowed us to apply critical programming concepts, such as pointer manipulation and understanding the differences between iterative and recursive solutions. By carefully considering how to reverse the direction of the list, we've developed a solid foundation for working with linked lists and similar data structures in future problems.
