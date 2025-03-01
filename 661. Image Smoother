class Solution:
    def imageSmoother(self, img: List[List[int]]) -> List[List[int]]:
        # Get the dimensions of the image matrix
        rows, cols = len(img), len(img[0])
        
        # Define a helper function to calculate the average value for a pixel
        def average_value(r, c):
            total, count = 0, 0

            # Define the boundaries for the neighboring pixels
            top = max(0, r - 1)
            bottom = min(rows, r + 2)
            left = max(0, c - 1)
            right = min(cols, c + 2)

            # Iterate over the neighboring pixels and calculate the sum and count
            for row in range(top, bottom):
                for col in range(left, right):
                    total += img[row][col]
                    count += 1

            # Calculate and return the average value for the pixel
            return total // count

        # Apply the average function to each pixel in the image matrix
        return [[average_value(r, c) for c in range(cols)] for r in range(rows)]
