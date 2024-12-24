- **闭环控制系统**是一种基于反馈原理的控制方法。它通过测量输出信号并与期望的参考信号进行比较，使系统能够根据误差信号自动调整其行为，以达到期望的控制目标。闭环控制系统能够处理外部干扰、系统变化和模型误差等不确定因素，提高系统的稳定性和鲁棒性。
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2024-07-14T16:00:00.000Z
  card-last-reviewed:: 2024-07-14T14:12:23.008Z
  card-last-score:: 1
- **模糊控制**是一种基于模糊逻辑的控制方法，能够处理具有模糊和不确定性特征的系统。它利用模糊推理和模糊集合理论，通过模糊规则描述输入变量和输出变量之间的关系，并通过模糊推理确定控制规则。模糊控制系统在处理非线性、复杂系统和模型不准确情况下表现出色。
  collapsed:: true
	- 一个简单的温度控制系统，其中温度为输入变量，功率为输出变量。模糊控制器根据温度的模糊集和设定的规则，计算出相应的功率输出。
	- ```python
	  import numpy as np
	  import skfuzzy as fuzz
	  from skfuzzy import control as ctrl
	  
	  # 创建模糊控制变量
	  temperature = ctrl.Antecedent(np.arange(0, 101, 1), 'temperature')
	  power = ctrl.Consequent(np.arange(0, 11, 1), 'power')
	  
	  # 定义模糊集和隶属函数
	  temperature['low'] = fuzz.trimf(temperature.universe, [0, 0, 50])
	  temperature['medium'] = fuzz.trimf(temperature.universe, [0, 50, 100])
	  temperature['high'] = fuzz.trimf(temperature.universe, [50, 100, 100])
	  
	  power['low'] = fuzz.trimf(power.universe, [0, 0, 5])
	  power['medium'] = fuzz.trimf(power.universe, [0, 5, 10])
	  power['high'] = fuzz.trimf(power.universe, [5, 10, 10])
	  
	  # 定义模糊规则
	  rule1 = ctrl.Rule(temperature['low'], power['high'])
	  rule2 = ctrl.Rule(temperature['medium'], power['medium'])
	  rule3 = ctrl.Rule(temperature['high'], power['low'])
	  
	  # 创建模糊控制系统
	  temperature_ctrl = ctrl.ControlSystem([rule1, rule2, rule3])
	  temperature_simulation = ctrl.ControlSystemSimulation(temperature_ctrl)
	  
	  # 模拟温度控制过程
	  for t in range(0, 101):
	      temperature_simulation.input['temperature'] = t
	      temperature_simulation.compute()
	      power_output = temperature_simulation.output['power']
	      print(f"Temperature: {t} - Power Output: {power_output}")
	  ```
- **非线性控制**是一种应对线性系统的控制方法。相较于线性控制方法，非线性控制通过使用非线性模型和控制策略来描述系统，能够更好地处理高度非线性和时变系统。在许多实际工业应用中，系统的非线性特性非常明显，此时非线性控制方法能够提供更准确的控制性能。
  collapsed:: true
	- 在机械臂控制系统中可以采用非线性控制方法。该系统利用模型预测控制和适应性控制算法，能够处理机械臂在复杂环境下的路径规划和动态响应。
	- ```python
	  import numpy as np
	  from scipy.integrate import odeint
	  import matplotlib.pyplot as plt
	  
	  def nonlinear_system(x, t):
	      # 定义非线性系统的动态方程
	      dxdt = np.sin(x) + np.cos(x)  # 这里只是一个示例方程，非线性系统的具体方程根据应用场景而定
	      return dxdt
	  
	  # 定义初始条件和时间点
	  x0 = 0.1
	  t = np.linspace(0, 10, 100)
	  
	  # 模拟非线性系统的响应
	  x = odeint(nonlinear_system, x0, t)
	  
	  # 绘制响应曲线
	  plt.plot(t, x)
	  plt.xlabel('Time')
	  plt.ylabel('State')
	  plt.title('Nonlinear System Response')
	  plt.show()
	  ```
- **鲁棒控制**是一种针对系统参数变化和建模误差的控制方法。它通过考虑系统不确定性，设计控制器来保证系统的稳定性和鲁棒性。鲁棒控制方法对于系统参数变化较大、具有不确定性的系统具有更强的适应能力。
  collapsed:: true
	- 例如，在汽车悬挂系统中可以采用鲁棒控制方法。该系统能够在道路条件变化和车辆负载变化的情况下，保持车辆悬挂系统的性能和安全性。
	- ```python
	  import control
	  from control import TransferFunction
	  import matplotlib.pyplot as plt
	  
	  # 定义系统的传递函数
	  G = TransferFunction([1], [1, 1, 1])
	  
	  # 设计鲁棒控制器
	  # 这里使用H∞鲁棒控制器作为示例，实际应用中的设计方法根据具体需求选择
	  controller = control.robust.hinfsyn(G)
	  
	  # 创建闭环系统
	  closed_loop_system = control.feedback(controller * G, 1)
	  
	  # 绘制阶跃响应曲线
	  t, y = control.step_response(closed_loop_system)
	  plt.plot(t, y)
	  plt.xlabel('Time')
	  plt.ylabel('Output')
	  plt.title('Robust Control Step Response')
	  plt.grid(True)
	  plt.show()
	  ```
-
- python [[control]] 库
	- ```
	  pip install control
	  ```
	- [python-control/python-control (github.com)](https://github.com/python-control/python-control)