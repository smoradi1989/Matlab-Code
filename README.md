clc;close all; clear;
%% inpout data 
[b,a]=uigetfile('*.xlsx');
[aa, c]=xlsread([a filesep b]);
%% plot lines
 x_boundary= [1,0, 0,  0.85,1,0.6, 1];
 y_boundary = [1,100, 500, 17000,10,350, 8000];

for i= 1 : numel(x_boundary)
  x(i) =x_boundary(i);
  y(i) =y_boundary(i);
  
end
     
   plot(x,y,  '*' ,'LineWidth', 0.5, 'color','r');
   line([x(1), x(2)], [y(1), y(2)], 'Color', 'r', 'LineStyle', '--','LineWidth', 1);
   line([x(3), x(4)], [y(3), y(4)], 'Color', 'r', 'LineStyle', '--','LineWidth', 1);
   line([x(5), x(6)], [y(5), y(6)], 'Color', 'r', 'LineStyle', '--','LineWidth', 1);
   line([x(6), x(7)], [y(6), y(7)], 'Color', 'r', 'LineStyle', '--','LineWidth', 1);
 
   set(gca, 'XScale', 'linear');
   set(gca, 'YScale', 'log');
   hold on;
   grid on;
  %% plot points
   plot(aa(:,1),aa(:,2),  'o' ,'LineWidth',1, 'color','b');
   
% Set axis labels
xlabel('Na/(Na+Ca)');
ylabel('Total dissolved salts (ppm)');

% Add additional annotations
title('Total Dissolved Salts vs. Na/(Na+Ca)');

box on;
xlim([0 1]);
ylim([10 10000]);

hold off;


