# Matlab-syntax

### 1.matlab中冒号的两种用法    
#### a.对于矩阵，冒号表示该维度上的所有元素.  
    A=  
    1 2 3  
    4 5 6  
    7 8 9  
    A(1，:)表示A的第一行，包含所有列的第一个元素。  
    A(1，:) =  [1 2 3]  
#### b.在循环语句中，冒号表示“从什么开始，间隔多少，到什么”
    for i = 0 : 2 : 10  
表示的是i从0开始，每次增长2，一直到10，所以循环的第一次i=0，第二次循环i=2,...第6次i为10，循环结束。相当于C语言中的for(i=0;i<=10;i=i+2)  
#### c.表示将矩阵按列排成一列  
```
I = 1 2 3  
    4 5 6  
    7 8 9  
I = I(:)  
I = [1 2 3 4 5 6 7 8 9]'  %列向量  
I = I'			  %转置变成行向量  
I = 1 2 3 4 5 6 7 8 9  
```

### 2.matlab的行和列的换行问题 
#### a.行向量可以用空格或者逗号隔开 
		A = [1 2 3] | A = [1, 2, 3]
#### b.列向量用分号隔开   
		A = [1 2 3;  4 5 6;  7 8 9]

### 3.matlab基本符号
![符号表](https://github.com/laofa/Matlab-note/blob/master/matlab%E7%AC%A6%E5%8F%B7.png)

### 4.matlab的索引是从1开始的
		A = [1 2 3]  
		>>>A[1]  
		>>>A[1] = 1  

### 5.zeros(height,width)是建立数组的简易方法  
		A = zeros(2, 3)
		A = [0 0 0; 0 0 0]  

### 6. subplot是MATLAB中的函数。
使用方法：subplot(m,n,p)或者subplot(m n p)  
subplot是将多个图画到一个平面上的工具。其中，m表示是图排成m行，n表示图排成n列，也就是整个figure中有n个图是排成一行的.一共m行，如果m=2就是表示2行图。p表示图所在的位置，p=1表示从左到右从上到下的第一个位置,把绘图窗口分成两行两列四块区域，然后在每个区域分别作图，基本步骤  
```
// 2、2、1之间没有逗号也可以  
subplot(2,2,1);  
// 在第一块绘图  
subplot(2,2,2);  
// 在第二块绘图  
subplot(2,2,3);  
// 在第三块绘图  
subplot(2,2,4);  
// 在第四块绘图  
```

### 7.min函数的标准用法[c, i]，c为各个列中最小的值，i为最小值所在的行号
		A = magic(5)  
		A =  
		17    24     1     8    15  
		23     5     7    14    16  
		 4     6    13    20    22  
		10    12    19    21     3  
		11    18    25     2     9  
		>> [c,i] = min(A)  
		
		c =  
		4     5     1     2     3  
		
		i =  
		3     2     1     5     4  



### 8.矩阵的元素引用要用小括号
		A[i] --------  错误  
		A(i) --------  正确  

### 9.获取图像size
		[height width] = size(img);  

### 10.选取矩阵的子矩阵
		A = B(1:3,1:3); // 选取3*3的矩阵  
		A = B(i:i+n-1, j:j+n-1); // 0~n-1共n个点  

### 11.矩阵算数运算：
		sum(A)或者sum(A, 1)求每列的和  
		sum(A, 2)求每行的和  
		mean(A)求每列的平均值  
		mean2(A)求所有元素的平均值  

### 12.A*B表示每个元素对应位置相乘，除法，加减法一样
		A = [1 2 3]  
		B = [2 3 4]
		C = A*B
		C = [2 6 12]

### 13.矩阵寻找最大值，最小值所在的位置：
		[x y] = find(A == max(max(A)));  
		[x y] = find(A == min(min(A)));

### 14.im2double和double的区别
double(A)是将A直接转换成double类型，数值上没有变化。  
im2double(A)是将A转换成double类型的同时进行归一化都(0, 1)。