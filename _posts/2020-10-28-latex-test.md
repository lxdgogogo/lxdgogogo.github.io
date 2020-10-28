---
layout:     post
title:      latex markdown测试
subtitle:   latex markdown测试
date:       2020-10-27
author:     Yanxing
catalog:    false
tags:
    - Language Tips
---
$
xyz
$


$$ 
\left[ \begin{matrix}
	b_{1}&c_{1}& & & &0 \\
	a_{2}&b_{2}&c_{2}& & & \\ 
	 &a_{3}&b_{3}&\ddots& &  \\
	 & &\ddots&\ddots&c_{n-1} & \\
	0& & & &a_{n}&b_{n}
\end{matrix}\right] 
\left[ \begin{matrix}
	x_{1} \\
	x_{2} \\ 
	x_{3} \\
	\vdots\\
	x_{n}
\end{matrix}\right]  = 
\left[ \begin{matrix}
	d_{1} \\
	d_{2} \\ 
	d_{3} \\
	\vdots\\
	d_{n}
\end{matrix}\right]
\tag{2}
$$

$$ c'_i =
\begin{cases} 
\begin{array}{lcl}
  \cfrac{c_i}{b_i}                   & & ; i = 1 \\
  \cfrac{c_i}{b_i - a_i c'_{i - 1}}  & & ; i = 2, 3, \dots, n-1 \\
\end{array}
\end{cases}
\tag{3}$$