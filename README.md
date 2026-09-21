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

# SMALLEST DIVISOR 
def smallestDivisor(self, nums, limit):
        low=1
        high=max(nums)
        while low<high:
            mid=low+(high-low)//2
            total=0                 #reset toatl for every mid=
            for num in nums:
                total+=(num + mid-1)//mid
            if total<=limit:
                high=mid
            else:
                low=mid+1
        return low
                
# FIND MINIMUM DAYS TO MAKE M BOUQETS
def roseGarden(self, n, nums, k, m):
        if m*k>len(nums):
            return -1
        low=min(nums)
        high=max(nums)
        while low<=high:
            mid=low+(high-low)//2
            bouqets=0
            flowers=0
            for day in nums:
                if day<=mid:
                    flowers+=1
                    if flowers==k:
                        bouqets+=1
                        flowers=0
                else:
                    flowers=0
            if bouqets>=m:
                high=mid-1
            else:
                low=mid+1
        return low

