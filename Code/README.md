```R
summary(m1)  
2.	  
3.	Call:  
4.	lm(formula = data$r ~ data$TDS + data$T + data$CaC03 + data$A +   
5.	    data$pH + data$conductivity + data$T:data$TDS + data$T:data$CaC03 +   
6.	    data$T:data$A + data$T:data$pH + data$T:data$conductivity +   
7.	    data$A:data$pH + data$A:data$CaC03 + data$pH:data$CaC03)  
8.	  
9.	Residuals:  
10.	     Min       1Q   Median       3Q      Max   
11.	-0.20959 -0.06950 -0.01937  0.06816  0.37928   
12.	  
13.	Coefficients:  
14.	                           Estimate Std. Error t value Pr(>|t|)  
15.	(Intercept)              -2.955e+02  4.653e+02  -0.635    0.531  
16.	data$TDS                  7.457e-03  2.040e-02   0.366    0.718  
17.	data$T                    6.899e+00  1.045e+01   0.661    0.515  
18.	data$CaC03                3.405e-03  8.750e-02   0.039    0.969  
19.	data$A                   -7.120e-02  2.395e-01  -0.297    0.769  
20.	data$pH                   3.468e+01  5.578e+01   0.622    0.540  
21.	data$conductivity         3.207e-02  2.997e-02   1.070    0.295  
22.	data$TDS:data$T          -1.857e-04  4.708e-04  -0.394    0.697  
23.	data$T:data$CaC03         6.752e-05  1.456e-03   0.046    0.963  
24.	data$T:data$A             1.362e-03  2.745e-03   0.496    0.624  
25.	data$T:data$pH           -8.099e-01  1.251e+00  -0.647    0.523  
26.	data$T:data$conductivity -7.110e-04  6.924e-04  -1.027    0.314  
27.	data$A:data$pH            1.282e-03  2.040e-02   0.063    0.950  
28.	data$CaC03:data$A         5.419e-06  2.164e-05   0.250    0.804  
29.	data$CaC03:data$pH       -7.639e-04  9.820e-03  -0.078    0.939  
30.	  
31.	Residual standard error: 0.1459 on 25 degrees of freedom  
32.	Multiple R-squared:  0.7551,    Adjusted R-squared:  0.6179   
33.	F-statistic: 5.505 on 14 and 25 DF,  p-value: 0.0001117  
34.	  
35.	  
36.	> best=step(m1)  
37.	Start:  AIC=-142.81  
38.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
39.	    data$conductivity + data$T:data$TDS + data$T:data$CaC03 +   
40.	    data$T:data$A + data$T:data$pH + data$T:data$conductivity +   
41.	    data$A:data$pH + data$A:data$CaC03 + data$pH:data$CaC03  
42.	  
43.	                           Df Sum of Sq     RSS     AIC  
44.	- data$T:data$CaC03         1 0.0000458 0.53190 -144.81  
45.	- data$A:data$pH            1 0.0000839 0.53194 -144.80  
46.	- data$CaC03:data$pH        1 0.0001288 0.53199 -144.80  
47.	- data$CaC03:data$A         1 0.0013342 0.53319 -144.71  
48.	- data$TDS:data$T           1 0.0033107 0.53517 -144.56  
49.	- data$T:data$A             1 0.0052414 0.53710 -144.42  
50.	- data$T:data$pH            1 0.0089159 0.54077 -144.15  
51.	- data$T:data$conductivity  1 0.0224372 0.55429 -143.16  
52.	<none>                                  0.53186 -142.81  
53.	  
54.	Step:  AIC=-144.81  
55.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
56.	    data$conductivity + data$TDS:data$T + data$T:data$A + data$T:data$pH +   
57.	    data$T:data$conductivity + data$A:data$pH + data$CaC03:data$A +   
58.	    data$CaC03:data$pH  
59.	  
60.	                           Df Sum of Sq     RSS     AIC  
61.	- data$CaC03:data$pH        1 0.0000962 0.53200 -146.80  
62.	- data$A:data$pH            1 0.0001319 0.53203 -146.80  
63.	- data$CaC03:data$A         1 0.0013234 0.53323 -146.71  
64.	- data$TDS:data$T           1 0.0061521 0.53805 -146.35  
65.	- data$T:data$A             1 0.0080541 0.53996 -146.21  
66.	- data$T:data$pH            1 0.0089269 0.54083 -146.14  
67.	- data$T:data$conductivity  1 0.0256288 0.55753 -144.93  
68.	<none>                                  0.53190 -144.81  
69.	  
70.	Step:  AIC=-146.8  
71.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
72.	    data$conductivity + data$TDS:data$T + data$T:data$A + data$T:data$pH +   
73.	    data$T:data$conductivity + data$A:data$pH + data$CaC03:data$A  
74.	  
75.	                           Df Sum of Sq     RSS     AIC  
76.	- data$A:data$pH            1 0.0000849 0.53208 -148.79  
77.	- data$CaC03:data$A         1 0.0013392 0.53334 -148.70  
78.	- data$TDS:data$T           1 0.0072105 0.53921 -148.26  
79.	- data$T:data$A             1 0.0079583 0.53996 -148.21  
80.	- data$T:data$pH            1 0.0114565 0.54346 -147.95  
81.	- data$T:data$conductivity  1 0.0270755 0.55907 -146.81  
82.	<none>                                  0.53200 -146.80  
83.	  
84.	Step:  AIC=-148.79  
85.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
86.	    data$conductivity + data$TDS:data$T + data$T:data$A + data$T:data$pH +   
87.	    data$T:data$conductivity + data$CaC03:data$A  
88.	  
89.	                           Df Sum of Sq     RSS     AIC  
90.	- data$CaC03:data$A         1 0.0012593 0.53334 -150.70  
91.	- data$TDS:data$T           1 0.0072722 0.53936 -150.25  
92.	- data$T:data$A             1 0.0079621 0.54005 -150.20  
93.	- data$T:data$pH            1 0.0122243 0.54431 -149.88  
94.	<none>                                  0.53208 -148.79  
95.	- data$T:data$conductivity  1 0.0273066 0.55939 -148.79  
96.	  
97.	Step:  AIC=-150.7  
98.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
99.	    data$conductivity + data$TDS:data$T + data$T:data$A + data$T:data$pH +   
100.	    data$T:data$conductivity  
101.	  
102.	                           Df Sum of Sq     RSS     AIC  
103.	- data$TDS:data$T           1 0.0066634 0.54001 -152.20  
104.	- data$T:data$A             1 0.0067304 0.54007 -152.20  
105.	- data$T:data$pH            1 0.0124399 0.54578 -151.78  
106.	- data$CaC03                1 0.0249363 0.55828 -150.87  
107.	<none>                                  0.53334 -150.70  
108.	- data$T:data$conductivity  1 0.0303059 0.56365 -150.49  
109.	  
110.	Step:  AIC=-152.2  
111.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
112.	    data$conductivity + data$T:data$A + data$T:data$pH + data$T:data$conductivity  
113.	  
114.	                           Df Sum of Sq     RSS     AIC  
115.	- data$T:data$A             1  0.002892 0.54290 -153.99  
116.	- data$T:data$pH            1  0.006490 0.54650 -153.72  
117.	- data$CaC03                1  0.021341 0.56135 -152.65  
118.	<none>                                  0.54001 -152.20  
119.	- data$T:data$conductivity  1  0.027836 0.56784 -152.19  
120.	- data$TDS                  1  0.080996 0.62100 -148.61  
121.	  
122.	Step:  AIC=-153.99  
123.	data$r ~ data$TDS + data$T + data$CaC03 + data$A + data$pH +   
124.	    data$conductivity + data$T:data$pH + data$T:data$conductivity  
125.	  
126.	                           Df Sum of Sq     RSS     AIC  
127.	- data$A                    1  0.002291 0.54519 -155.82  
128.	- data$T:data$pH            1  0.005360 0.54826 -155.60  
129.	- data$CaC03                1  0.024042 0.56694 -154.25  
130.	- data$T:data$conductivity  1  0.025628 0.56853 -154.14  
131.	<none>                                  0.54290 -153.99  
132.	- data$TDS                  1  0.083850 0.62675 -150.24  
133.	  
134.	Step:  AIC=-155.82  
135.	data$r ~ data$TDS + data$T + data$CaC03 + data$pH + data$conductivity +   
136.	    data$T:data$pH + data$T:data$conductivity  
137.	  
138.	                           Df Sum of Sq     RSS     AIC  
139.	- data$T:data$pH            1  0.004752 0.54994 -157.47  
140.	- data$T:data$conductivity  1  0.023608 0.56880 -156.12  
141.	<none>                                  0.54519 -155.82  
142.	- data$CaC03                1  0.030775 0.57596 -155.62  
143.	- data$TDS                  1  0.081861 0.62705 -152.22  
144.	  
145.	Step:  AIC=-157.47  
146.	data$r ~ data$TDS + data$T + data$CaC03 + data$pH + data$conductivity +   
147.	    data$T:data$conductivity  
148.	  
149.	                           Df Sum of Sq     RSS     AIC  
150.	- data$T:data$conductivity  1  0.020076 0.57002 -158.04  
151.	<none>                                  0.54994 -157.47  
152.	- data$pH                   1  0.028482 0.57842 -157.45  
153.	- data$CaC03                1  0.038937 0.58888 -156.74  
154.	- data$TDS                  1  0.095017 0.64496 -153.10  
155.	  
156.	Step:  AIC=-158.04  
157.	data$r ~ data$TDS + data$T + data$CaC03 + data$pH + data$conductivity  
158.	  
159.	                    Df Sum of Sq     RSS     AIC  
160.	- data$T             1   0.00695 0.57696 -159.55  
161.	- data$pH            1   0.01959 0.58961 -158.69  
162.	<none>                           0.57002 -158.04  
163.	- data$CaC03         1   0.04162 0.61163 -157.22  
164.	- data$TDS           1   0.09809 0.66810 -153.69  
165.	- data$conductivity  1   0.41397 0.98399 -138.20  
166.	  
167.	Step:  AIC=-159.55  
168.	data$r ~ data$TDS + data$CaC03 + data$pH + data$conductivity  
169.	  
170.	                    Df Sum of Sq     RSS     AIC  
171.	- data$pH            1   0.02535 0.60231 -159.83  
172.	<none>                           0.57696 -159.55  
173.	- data$CaC03         1   0.03708 0.61404 -159.06  
174.	- data$TDS           1   0.10528 0.68225 -154.85  
175.	- data$conductivity  1   0.40719 0.98416 -140.19  
176.	  
177.	Step:  AIC=-159.83  
178.	data$r ~ data$TDS + data$CaC03 + data$conductivity  
179.	  
180.	                    Df Sum of Sq     RSS     AIC  
181.	<none>                           0.60231 -159.83  
182.	- data$CaC03         1   0.03886 0.64118 -159.33  
183.	- data$TDS           1   0.08371 0.68602 -156.63  
184.	- data$conductivity  1   0.87000 1.47231 -126.08  
185.	  
186.	  
187.	#用AIC报告中的最佳逐步回归结果建立MVR模型  
188.	fitbest=lm(data$r~data$TDS+data$CaC03+data$conductivity)  
189.	> fitbest  
190.	  
191.	Call:  
192.	lm(formula = data$r ~ data$TDS + data$CaC03 + data$conductivity)  
193.	  
194.	Coefficients:  
195.	      (Intercept)           data$TDS         data$CaC03  data$conductivity    
196.	       -0.2144224         -0.0005241          0.0007030          0.0013569    
197.	  
198.	> summary(fitbest)  
199.	  
200.	Call:  
201.	lm(formula = data$r ~ data$TDS + data$CaC03 + data$conductivity)  
202.	  
203.	Residuals:  
204.	     Min       1Q   Median       3Q      Max   
205.	-0.19862 -0.09245 -0.00355  0.07910  0.37172   
206.	  
207.	Coefficients:  
208.	                    Estimate Std. Error t value Pr(>|t|)      
209.	(Intercept)       -0.2144224  0.1216924  -1.762   0.0866 .    
210.	data$TDS          -0.0005241  0.0002343  -2.237   0.0316 *    
211.	data$CaC03         0.0007030  0.0004613   1.524   0.1362      
212.	data$conductivity  0.0013569  0.0001882   7.211 1.74e-08 ***  
213.	---  
214.	Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1  
215.	  
216.	Residual standard error: 0.1293 on 36 degrees of freedom  
217.	Multiple R-squared:  0.7226,    Adjusted R-squared:  0.6995   
218.	F-statistic: 31.26 on 3 and 36 DF,  p-value: 3.959e-10  
219.	  
220.	#p-value显著小于置信度0.05，通过假设检验  
221.	  
222.	#进行假设检验条件的检验  
223.	par(mfrow=c(2,2))  
224.	> plot(fitbest)  
225.	图  
226.	  
227.	  
228.	  
229.	#多重共线性检验  
230.	vif(fitbest)  
231.	         data$TDS        data$CaC03 data$conductivity   
232.	         2.805841          2.345735          1.310447   
233.	  
234.	<<R in action>>指出VIF大于4时存在共线性关系，理想模型中VIF=1说明完全不存在共线性  
235.	  
236.	  
237.	#预测结果绘图  
238.	par(mfrow=c(1,1))  
239.	> plot(data$r,xlab='time',ylab='Thermal resistance',main='MVR-plot: Predicted and Experimental Values')  
240.	> lines(fitbest$fitted.values,col="red")  
241.	  
242.	  
243.	  
244.	#ARIMA模型准备：对于污垢热阻数据进行ADF平稳性检验  
245.	  
246.	adf.test(nd_r, alternative="stationary", k=0)Augmented Dickey-Fuller Test  
247.	data:  nd_r  
248.	Dickey-Fuller = -8.7973, Lag order = 0, p-value = 0.01  
249.	alternative hypothesis: stationary  
250.	  
251.	Warning message:  
252.	In adf.test(nd_r, alternative = "stationary", k = 0) :  
253.	  p-value smaller than printed p-value  
254.	  
255.	  
256.	#周期性数据分解  
257.	rts=ts(data$r,frequency=3)#生成时间序列对象  
258.	> library(TTR)  
259.	> rtsSMA=SMA(rts,n=3)#移动平滑法使得时间序列平稳  
260.	> plot.ts(rtsSMA)  
261.	> rtscomponents=decompose(rts)  
262.	>#去掉周期性数据  
263.	> rts_adjusted=rts-rtscomponents$seasonal  
264.	> plot(rts_adjusted)  
265.	  
266.	  
267.	#对影响污垢热阻的水质数据做ARMA变换使其满足平稳性条件，auto.arima函数用于确定使得AIC值与BIC值最小的ARIMA阶数(衡量模型拟合优良性准则）  
268.	> auto.arima(data$TDS)  
269.	Series: data$TDS   
270.	ARIMA(0,1,0)   
271.	  
272.	sigma^2 estimated as 3378:  log likelihood=-213.78  
273.	AIC=429.56   AICc=429.67   BIC=431.22  
274.	> auto.arima(data$CaC03)  
275.	Series: data$CaC03   
276.	ARIMA(0,1,0)   
277.	  
278.	sigma^2 estimated as 1600:  log likelihood=-199.21  
279.	AIC=400.41   AICc=400.52   BIC=402.07  
280.	> auto.arima(data$conductivity)  
281.	Series: data$conductivity   
282.	ARIMA(0,1,1) with drift   
283.	  
284.	Coefficients:  
285.	          ma1    drift  
286.	      -0.4688  10.3665  
287.	s.e.   0.1327   3.5806  
288.	  
289.	sigma^2 estimated as 1783:  log likelihood=-200.41  
290.	AIC=406.83   AICc=407.51   BIC=411.82  
291.	  
292.	  
293.	#ARIMAX模型  
294.	arimax(nd_r, order=c(0,0,1) , xtransf=data.frame(nd_c,nd_cdt,nd_TDS), transfer= list(c(0,0),c(0,1),c(0,0)) )  
295.	Call:  
296.	Coefficients:  
297.	          ma1  
298.	      -0.4269  
299.	s.e.   0.1333  
300.	  
301.	sigma^2 estimated as 0.009433:  log likelihood = 35.5,  aic = -69  
302.	  
303.	  
304.	#模型检验  
305.	Box.test(arimaxr$residuals,type="Ljung-Box")  
306.	    Box-Ljung test  
307.	  
308.	data:  arimaxr$residuals  
309.	X-squared = 0.41821, df = 1, p-value = 0.5178  
310.	  
311.	#预测结果  
312.	 prdt=predict(r_adjustedmodel,start=c(1,2),40)  
313.	> plot(data$r,xlab='time',ylab='Thermal resistnce',main='ARIMA prediction')  
314.	> lines(prdt$pred,col='red')  
315.	  
316.	#最终模型  
317.	Call:  
318.	arima(x = data$CaC03, order = c(0, 1, 0))  
319.	  
320.	  
321.	sigma^2 estimated as 1600:  log likelihood = -199.21,  aic = 398.41  
322.	> arma_cdt=auto.arima(data$TDS)  
323.	> arma_cdt  
324.	Series: data$TDS   
325.	ARIMA(0,1,0)   
326.	  
327.	sigma^2 estimated as 3378:  log likelihood=-213.78  
328.	AIC=429.56   AICc=429.67   BIC=431.22  
329.	> arma_TDS=auto.arima(data$TDS)  
330.	> arma_TDS  
331.	Series: data$TDS   
332.	ARIMA(0,1,0)   
333.	  
334.	sigma^2 estimated as 3378:  log likelihood=-213.78  
335.	AIC=429.56   AICc=429.67   BIC=431.22  
336.	> arma_cdt=auto.arima(data$conductivity)  
337.	> arma_cdt  
338.	Series: data$conductivity   
339.	ARIMA(0,1,1) with drift   
340.	  
341.	Coefficients:  
342.	          ma1    drift  
343.	      -0.4688  10.3665  
344.	s.e.   0.1327   3.5806  
345.	  
346.	sigma^2 estimated as 1783:  log likelihood=-200.41  
347.	AIC=406.83   AICc=407.51   BIC=411.82  
```
