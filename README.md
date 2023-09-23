# MATLAB_Gantt_Chart

https://simulationtutor.com/matlab-gantt-chart-a-comprehensive-guide/

%% Gantt Chart in MATLAB
clc,clear all,close all,
tasks = {'Task 1', 'Task 2', 'Task 3'};
start_times = [1, 4, 7]; % Start times in days
end_times = [3, 6, 9];   % End times in days
durations = end_times - start_times;
figure;
bar(start_times, durations, 'stacked');
% Add task labels
task_labels = strcat(tasks, ' (', num2str(durations), ' days)');
yticks(start_times + durations / 2);
yticklabels(task_labels);

% Set axis labels
xlabel('Time (days)');
ylabel('Tasks');
title('Gantt Chart');
grid on;
%figure;
% show;

%%
% clear all,close all,clc,
% Define your tasks and their start and end times
tasks = {'Task 1', 'Task 2', 'Task 3'};
start_times = [1, 4, 7]; % Start times in days
end_times = [3, 6, 9];   % End times in days

% Calculate the duration of each task
durations = end_times - start_times;

% Define colors for each task
colors = {'red', 'yellow', 'blue'};

% Create the Gantt chart
figure;

% Specify the time scale (you can change this as needed)
time_scale = 1; % In days, adjust as necessary

% Create a bar chart with specified colors
for i = 1:length(tasks)
    barh(i, durations(i) * time_scale, 'FaceColor', colors{i});
    hold on;
end

% Customize the Gantt chart appearance
yticks(1:length(tasks));
yticklabels(tasks);
xlabel('Time (days)');
ylabel('Tasks');
title('Customized Gantt Chart');
grid on;
xlim([0, max(end_times) * time_scale + 2]); % Adjust the x-axis limit as needed

% Show the Gantt chart
% show;
