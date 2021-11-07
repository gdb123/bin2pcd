# bin2pcd

clc;
clear;
close all;
fid=fopen('006013.bin','rb');
%以float32的格式将数据存放在列向量中
[a,count]=fread(fid,'float32');
fclose(fid);%关闭文件
x = a(1:4:end);
y = a(2:4:end);
z = a(3:4:end);
data = pointCloud([x y z]);
pcshow(data);
