TA 

模板构建：

1. 现有设备$uTarget$  对于一个data和一个密钥key,设置一个训练值（p,t）

2. 由于这个设备是白盒情况，我们采集N条曲线作为这个训练集Trace(n,j)

3. 这个模板上，选取一个泄露模型，这里我们使用HW。根据（p,t）,计算加密算法后产生的中间值，这里我们选择的是after(Sbox), 然后得到每个曲线对应的中间值，中间值 HW（n,i）这里i代表字节数，考虑到重复性，我们取i = 0

4. 关键点选取·：

   1. 首先我们选择一种统计方式来采样尖峰值，这里我们尝试使用SOD(sum of differentials)[$\sum(K_1-k_2),for k1\neq k2 and here k1\ k2 \in (HW(0,8))$]，我们将HW（n,i）以及对应的Trace(n,j)做一个分组T0 to T8，得到

      > 1. get mean trace[HW[i],j]for i in n [get mean power of each set for 0 to 8 ]
      > 2.  get sum $T_i -Tk,k\neq i$, then return poi = sum.argmax [get the differential for each set]
      > 3. rank the points and get certain points[get the peek point (leakage point)]

   2. 接下来，我们计算这些pois出现的概率，也就是完成均值和协方差矩阵的求解

      > 1. 计算每个HW值对应的poi的均值向量，样本数据同样是N，得到mean-matrix
      > 2. 计算这些HW值对应的协方差矩阵，也就是每个点与其他点的相关性

pseudocode

```pseudocode
def --init-- (self,traces,pt,num-pois,leak_model,poi_space)
1.sort HW for every trace and point # [eg:10000 spacing to 9 traces ]
2.Finding SOD OF EACH POINT sum of difference [cumulative all the poi differences value to show the most intersing point] #
3.Find poi which is the argmax, defing a spacing range allow the poi range then
	1. get the mean_matrix for [each HW ref to each poi] 
	2. get the cov- matrix for [a point for all other poi's pearson] 
4.attack
	1.get the introduce trace with ref poi(i,t)
	2.for each HW: that is each guess key:
		get possibility of  
```

To be solved:

1. 矩阵求逆需要什么
   1. review矩阵的逆的几何意义
   2. 矩阵求逆问题 （对数取值不能为负值，det(C)>0，且不能=0，也就是不能是奇异矩阵，编程可以跳过这个难关）
   3. 



