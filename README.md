class Solution:
    # Function to find the leaders in the array.
    def leaders(self, arr):
        n = len(arr)
        leaders_list = []
        
        # The rightmost element is always a leader
        max_from_right = arr[n-1]
        leaders_list.append(max_from_right)
        
        # Iterate from the second to last element down to the first
        for i in range(n-2, -1, -1):
            if arr[i] >= max_from_right:
                leaders_list.append(arr[i])
                # Update the maximum seen so far
                max_from_right = arr[i]
        
        # Since we collected leaders from right to left, 
        # reverse the list to maintain original order.
        return leaders_list[::-1]
