1.) Comlete run show how you run your program AND the its complete outputs

Ans:PS D:\Fall 23 MS CS\CS-695 AI Safety & Assurance\Programming Assignment\pa2-VerifAI> python se.py

1st DNN

{  'o0': [0.0, 0.0],'o1': [0.0, 0.0],'i0': [0.0, 0.0],'i1': [0.0, 0.0],'n0_0': [0, 0], 'n0_1': [0, 0], 'n1_0': [0, 0],'n1_1': [0, 0] }

Outputs when inputs are fixed [i0 == 1, i1 == -1]

{  'o0': [1.0, 1.0],'o1': [-1.0, -1.0], 'i0': [1.0, 1.0], 'i1': [-1.0, -1.0], 'n0_0': [2.0, 2.0], 'n0_1': [0, 0], 'n1_0': [1.0, 1.0], 'n1_1': [0, 0] }

Simulate execution with precondition ( 0.1 <= i0 <= 0.3, -0.7 <= i1 <= 0.0)

{  'o0': [0.05, 0.44],'o1': [-0.05, -0.44],'i0': [0.05, 0.44],'i1': [-0.05, -0.44], 'n0_0': [0.1, 1.0], 'n0_1': [0, 0.3], 'n1_0': [0.05, 0.44], 'n1_1': [0, 0] }

Check if the output interval of 'o0' is completely between [0, 1] : The property is proved.

2nd DNN

{ 'o0': [0.0, 0.0], 'o1': [0.0, 0.0], 'i0': [0.0, 0.0], 'i1': [0.0, 0.0], 'i2': [0, 0], 'i3': [0, 0], 'n0_0': [0, 0], 'n0_1': [0, 0], 'n0_2': [0, 0], 
'n0_3': [0, 0],  'n1_0': [0, 0], 'n1_1': [0, 0],'n1_2': [0, 0],'n1_3': [0, 0],'n2_0': [0, 0], 'n2_1': [0, 0], 'n2_2': [0, 0], 'n2_3': [0, 0] }

Outputs when inputs are fixed [i0 == 1, i1 == -1]

{  'o0': [-1.0595000000000006, -1.0595000000000006],'o1': [4.843500000000001, 4.843500000000001], 'i0': [-1.0595000000000006, -1.0595000000000006], 
'i1': [4.843500000000001, 4.843500000000001], 'i2': [1.7950000000000002, 1.7950000000000002], 'i3': [2.31, 2.31], 'n0_0': [0.7, 0.7],'n0_1': [1.8, 1.8], 
'n0_2': [0.10000000000000003, 0.10000000000000003], 'n0_3': [1.5, 1.5], 'n1_0': [1.74, 1.74],'n1_1': [0.61, 0.61], 
'n1_2': [0.36000000000000004, 0.36000000000000004], 'n1_3': [1.8300000000000003, 1.8300000000000003],'n2_0': [3.0810000000000004, 3.0810000000000004], 
'n2_1': [0, 0], 'n2_2': [1.7950000000000002, 1.7950000000000002], 'n2_3': [2.31, 2.31] }

Simulate execution with precondition ( 0.1 <= i0 <= 0.3, -0.7 <= i1 <= 0.0)

{  'o0': [-0.5291800000000002, -1.1693900000000002],'o1': [2.40054, 4.69443],'i0': [-0.5291800000000002, -1.1693900000000002],
'i1': [2.40054, 4.69443], 'i2': [0.4814, 1.6829000000000003], 'i3': [1.2328000000000001, 2.0984000000000003], 
'n0_0': [0.10000000000000003, 0.54], 'n0_1': [0.53, 1.29], 'n0_2': [0, 0.35],'n0_3': [0.74, 1.4100000000000001], 
'n1_0': [0.7000000000000001, 1.5790000000000002],'n1_1': [0.445, 0.555], 'n1_2': [0, 0.585], 'n1_3': [0.8280000000000001, 1.733],
'n2_0': [1.463, 3.0502000000000002], 'n2_1': [0, 0], 'n2_2': [0.4814, 1.6829000000000003],'n2_3': [1.2328000000000001, 2.0984000000000003] }

Check if the output interval of 'o0' is completely between [0, 1] : The property is not proved.

2.i.) Briefly describe what you did for part 1 and part 2
Ans: Part1: We created a random feedforward neural network (DNN) with specified neuron sizes and weight ranges using created_random() function. The DNN's architecture was created with random weights and biases, and random choices for whether to use ReLU activation functions.We ran symbolic execution on the DNN using the my_symbolic_execution() function and measured the time it took to solve the symbolic state. We defined some data points representing different neuron sizes and their corresponding execution times for the symbolic execution. We performed curve fitting on the data to obtain a power-law function that describes the relationship between neuron size and execution time. A scatter plot was created to visualize the data points and the fitted curve, showing the relationship between neuron size and execution time.

Part2: We defined functions for ReLU activation and computing intervals for neural network nodes. The interval_execution function computes input, output, and hidden node intervals for the given DNN using the provided interval conditions. The function returns a dictionary containing the intervals for each node. The results of the interval abstraction were printed, including the intervals for each node, which were calculated based on the architecture and provided interval conditions. Manual checks of assertions were performed to verify properties of the output intervals, such as ensuring they are within a specific range. We defined some data points representing different neuron sizes and their corresponding execution times for the interval abstraction. We performed curve fitting on the data to obtain a power-law function that describes the relationship between neuron size and execution time. A scatter plot was created to visualize the data points and the fitted curve, showing the relationship between neuron size and execution time.

ii.) Describe the plots and conclusions you have for scalability of both parts 1 and 2 

Ans:  Part-1 and Part-2 Observations:

Abstract Interval Domain Graph
https://github.com/atharvasalehittal/pa2/blob/296177bb4dba26e555ea5c3338ad297f2d93657c/abstract_interval_domain.png

Symbolic Execution Graph
https://github.com/atharvasalehittal/pa2/blob/296177bb4dba26e555ea5c3338ad297f2d93657c/symbolic_execution.png

a.) Data Points: The scatter plot shows several data points, where each data point represents a specific neuron size (x-axis) and its corresponding execution time in seconds (y-axis).

b.) Fitted Curve: The red curve on the plot represents the fitted curve obtained through curve fitting using a power-law function which is Execution Time = a * Neuron Size^b, where 'a' and 'b' are parameters obtained from curve fitting. The function has two parameters, 'a' and 'b,' which were determined through the curve fitting process.

c.) Axis Labels: The x-axis is labeled as 'Neuron Sizes,' representing the different sizes of neural networks. The y-axis is labeled as 'Execution Time (seconds),' representing the time it takes for symbolic execution.

d.) Legend: The plot includes a legend indicating the data points ('Execution Time') and the fitted curve ('Fitted Curve').

Part-1 Conclusion on Scalability: As the number of neurons (neuron sizes) increases, the execution time also increases. This suggests that symbolic execution becomes slower as the neural network's complexity grows. The fitted curve, which follows a power-law relationship, indicates that the execution time grows exponentially with the increase in neuron size.

Part-2 Conculsion on Scalability: The fitted curve provides insights into the scalability of interval abstraction. The value of 'b' in the power-law equation is a crucial parameter. If 'b' is close to 1, it suggests a linear relationship between neuron size and execution time, indicating that the execution time scales linearly with the network's size. On the other hand, if 'b' significantly deviates from 1, it suggests non-linear scalability, the plot and curve fitting confirm that the execution time is affected by the neuron size in a manner consistent with a power-law relationship, which implies that larger neural networks lead to increased execution time during interval abstraction.

iii.) What do you think the most difficult part of this assignment?

Ans: The most difficult part of this assignment is to program an generalized interval abstraction function which works for any dnn provided by the user. The next difficult part is the running of the dnn of various sizes to calculate execution time for symbolic execution of dnn to plot a graph.

iv.) What advice do you give other students (e.g., students in this class next year) about this PA?

Ans: Our advice to the students will be to understand interval abstraction and try to first pratice it on paper and then step by step start programming on Python. 
