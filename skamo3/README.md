# skamo3 README
 - Input = (96,96,1)
 - Conv = Convolutional layer
 - BN = BatchNormalization
 - MP = MaxPolling
 - DP = DropOut
 - GAP = GlovalAveragePooling
 - Output = 7
 
## Test 1
 - (Conv8-BN-ReLU)x3-MP-DP -> (Conv32-BN-ReLU)x3-MP-DP -> (Conv64-BN-ReLU)x3-MP-DP -> (Conv128-BN-ReLU)x3-MP-DP -> GAP -> Dense256(ReLU) -> Dense128(ReLU) -> Dense7(softmax)
 - BatchSize : 32
 - epochs : 60
 - learning rate : 0.001
 
 ### Test Result
 - loss : 0.3132
 - train accuracy : 0.8855
 - test accuracy : 0.6439  
 

## Test 2
 - Conv96-BN-ReLU-MP-DP -> Conv128-BN-ReLU-MP-DP -> Conv96-BN-ReLU-MP-DP -> Conv96-BN-ReLU-MP-DP -> Dense96(ReLU) -> Dense32(ReLU) -> Dense7(softmax)
 - BatchSize : 64 
 - epochs : 250
 - learning rate : 0.003
 
 ### Test Result
 - loss : 0.3775
 - train accuracy : 0.8608
 - test accuracy : 0.6119