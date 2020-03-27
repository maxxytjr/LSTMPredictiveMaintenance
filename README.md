# LSTMPredictiveMaintenance

## Background
Extracted telemetry data from the Universal Robot's collaborative robot, like joint currents, joint temperatures, joint voltages etc. can be used as a barometer for the robot's health.

This can motivate the end user to plan maintenance schedules, by spotting patterns in the behavior of the various metrics in their visualized forms and determining the best frequency of scheduled maintenance.

Going one step further, the data can be used to **predict** behavior of the metric of concern ahead of time. This enables the end user to achieve predictive maintenance; only performing maintenance when needed, and not just on a schedule, thus helping them to save costs.

## Method

The UR Cobot has 6 joints; the base joint's current data has been used for visualization and passed into a neural network containing **CNN, LSTM and Dense** layers for time series prediction.

Parameters such as **batch sizes**, **window size**, **filter sizes** for the CNN and LSTM layers were tuned to obtain the best **Mean Absolute Error** and **Loss** over 100 training epochs.

A **learning rate scheduler** was used to determine the best learning rate for training, passed in as a callback argument during model training.

All these performed under the **TensorFlow 2.0** environment.

## Results
#### Historical and Predicted
![historical and predicted]('historical_and_predicted.png')

#### Historical, Predicted and Actual
![historical, predicted and actual]('historical_predicted_actual.png')

#### Actual and Predicted (Close up)
![actual and predicted]('actual_predicted.png')
