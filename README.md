# Binary-Search-On-Answers-
# FIND THE SQRT OF A NUMBER
def floorSqrt(self, n: int) -> int:
        low=1
        high=n
        ans=0
        while low<high:
            mid=low+(high-low)//2
            if mid*mid<=n:
                ans=mid
                low=mid+1
            else:
                high=mid-1
        return ans
