1.RC电路仿真

RC一阶电路，我们在计算机里如何仿真？？？

![](/assets/MathCircuit_S2_E3.png)

Uc的导数，还记不记得，我们高等数学里是怎么算的？？？

![](/assets/MathCircuit_S2_E4.png)

在高等数学里，利用极限来得到导数，当我们用计算机仿真的时候，是反向来用把导数离散化

![](/assets/MathCircuit_S2_E5.png)

于是我们就可以用matlab写代码仿真RC电路的动态过程

```
R=1e3;%1000欧
C=1e-6;%1uF

dt=100e-6;%delta T 时间
T=1e-2;%仿真时间长度
t=0:dt:T;%时间轴
Us=ones(length(t),1);%1V
Uc=zeros(length(t),1);
for k=1:1:length(t)-1
    Uc(k+1)=Uc(k)+(Us(k)-Uc(k))*dt/(R*C);
end

plot(t,Uc)
grid on
xlabel('t/s')
ylabel('Uc/V')
```



