# leetcode_container_with_most_water
+ 물을 가장 많이 체울수 있는 공간 구하는 문제
+ 求出可以容納最大容量水的空間 (左邊要大於右邊)

-----
+ Example1
```
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```
----
+ Example2
```
Input: height = [1,1]
Output: 1
```
----
```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        l, r, res= 0, len(height) - 1, 0
        while(l < r): # 마지막에 도달하기까지..
            res = max(res, (r-l) * min(height[l],height[r])) # 현재 저장되있는 값과 width *  작은수 l or r한값들중에 잴 큰 값 저장
            if height[l] < height[r]: # 만약 오른쪽이 더 크면 앞으로 한칸
                l += 1
            else: # 아니면 뒤로 한칸
                r -= 1
        return res
```
---
```
결론 : 
이번에는 문제를 이해하는게 중요했다 문제 이해하는데 더 오래 걸린것같다.. 결론 한 부분은 높아야하고 그 높은것을 기준으로 높은 면적을 찾는 문제
```
---
```
結論:
在了解題目花了不少時間XDDDD 看得懂就很快就可以寫出來 結論就是找出最大值後 由於那個最大值找出最大面積並回傳
```
---
### Result
Runtime: 942 ms, faster than 64.63% of Python3 online submissions for Container With Most Water.\
Memory Usage: 27.6 MB, less than 15.20% of Python3 online submissions for Container With Most Water.
