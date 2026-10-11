# OSTEP Ch.4 Homework Answers

## Q1
- Prediction / 预测:Total time = 10 ticks; CPU utilization = 100%.
- Reasoning / 理由:Both processes have five CPU instructions and never perform I/O. The CPU stays busy until both processes finish.
- Verified result / 验证结果:
- Analysis / 分析:

## Q2
- Prediction / 预测:Total time = 11 ticks; CPU utilization = 54.55%.
- Reasoning / 理由:PID 0 executes four CPU instructions first. PID 1 then performs one I/O operation, which requires one tick to start, five blocked ticks, and one tick to finish.
- Verified result / 验证结果:
- Analysis / 分析:

## Q3
- Prediction / 预测:Total time = 9 ticks; CPU utilization = 66.67%.
- Reasoning / 理由:PID 0 starts with an I/O operation. Under the default SWITCH_ON_IO behavior, the CPU switches to PID 1 while PID 0 waits. PID 1 can use the CPU during the I/O wait.
- Verified result / 验证结果:
- Analysis / 分析:

## Q4
- Prediction / 预测:Total time = 13 ticks; CPU utilization = 46.15%.
- Reasoning / 理由:With SWITCH_ON_END, the system does not switch to PID 1 when PID 0 starts I/O. The CPU remains idle while PID 0 waits, and PID 1 runs after PID 0 finishes.
- Verified result / 验证结果:
- Analysis / 分析:

## Q5
- Prediction / 预测:Total time = 9 ticks; CPU utilization = 66.67%.
- Reasoning / 理由:With SWITCH_ON_IO, the system switches to PID 1 when PID 0 starts I/O. PID 1 can use the CPU while PID 0 is blocked, reducing idle time compared with Q4.
- Verified result / 验证结果:
- Analysis / 分析:

## Q6
- Prediction / 预测:Total time = 28 ticks; CPU utilization = 85.71%.
- Reasoning / 理由:With IO_RUN_LATER, PID 0 does not run immediately when its I/O completes. It waits until its turn, so other processes may execute first.
- Verified result / 验证结果:
- Analysis / 分析:

## Q7
- Prediction / 预测:Total time = 28 ticks; CPU utilization = 85.71%.
- Reasoning / 理由:With IO_RUN_IMMEDIATE, PID 0 runs immediately after its I/O completes. This changes the scheduling order compared with Q6 and may affect the total time.
- Verified result / 验证结果:
- Analysis / 分析:

## Q8
- Prediction / 预测:The process instruction sequences and total time depend on the random seed. Changing IO_DONE behavior or process-switching behavior can change the execution order and CPU utilization.
- Reasoning / 理由:Each process has three instructions with a 50% chance of CPU or I/O behavior. The random seed determines the generated instructions. IO_RUN_IMMEDIATE and SWITCH_ON_END change scheduling behavior, so the resulting traces and statistics may differ.
- Verified result / 验证结果:
- Analysis / 分析:

