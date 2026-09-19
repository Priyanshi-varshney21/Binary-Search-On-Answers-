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

# FIND THE Nth ROOT
def NthRoot(self, n, m):
        low=1
        high=m
        while low<high:
            mid=low+(high-low)//2
            if mid**n==m:
                return mid
            elif mid**n<mid:
                low=mid+1
            else:
                high=mid-1
        return -1
    
# KOKO EATING BANANAS 
def minimumRateToEatBananas(self, piles, h):
        low=1
        high=max(piles)
        while low<high:
            hours=0
            mid=low+(high-low)//2
            for pile in piles:
                hours+=(pile + mid-1)//mid
            if hours<=h:
                high=mid-1  #to find the min
            else:
                low=mid+1
        return low
