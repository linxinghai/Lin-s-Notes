# 通用命令
```Matlab
cd      显示或改变工作目录

dir     显示目录下内容

type

clear

clf

clc

echo

pack

hold

disp

path

save

load

diary

!

quit
```
# 项目

```Matlab
y=x+2;

x=1:0.5:10;

y=1:0.2:10;

plot(x,y);
```

```Matlab
clear all;

clc;

x=linspace(0,2*pi,60);

y=sin(x);

z=cos(x);

H1=figure;

plot(x,y);

title('sin(x)');

axis([0 2*pi -1 1]);

H2=figure;

plot(x,z);

title('cos(x)');

axis([0 2*pi -1 1]);
```