vezba12
def binary_search(arr, target):
    """
    Perform a binary search to find the index of the target value in a sorted array.
    
    :param arr: List of sorted elements.
    :param target: The element to search for.
    :return: The index of the target in the array if found, otherwise -1.
    """
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2  # Find the middle index
        
        # Check if the target is at the middle
        if arr[mid] == target:
            return mid
        # If the target is greater than the middle element, discard the left half
        elif arr[mid] < target:
            low = mid + 1
        # If the target is less than the middle element, discard the right half
        else:
            high = mid - 1
    
    # If we exit the loop, the target is not in the array
    return -1

# Example usage
arr = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
target = 7
result = binary_search(arr, target)

if result != -1:
    print(f"Element found at index {result}")
else:
    print("Element not found")
