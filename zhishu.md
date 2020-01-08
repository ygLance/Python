# 求质数的几个方法
* **1** 最常见:循环遍历
  ```
	(x for x in range(2,1000) if 0 not in	[i%d for d in range(2,int(d**0.5+1))])
	```
* **2** 去算是否被比他小的质数整除(数值大了这玩意比法一还慢)
  ```
  a=[2]
  for i in range(3,1000):
	for j in a:
		if i%j==0:
			break
	else:a.append(i)
	```
* **3** 筛法
  ```
  def func(n):
	ans=[]
	loc=[1 for i in range(n)]
	loc[0]=0
	for i in range(n):
		if loc[i]!=0:
			ans.append(i+1)
			for j in range(i+1,n+1,i+1):
				loc[j-1]=0
	return ans
	```
