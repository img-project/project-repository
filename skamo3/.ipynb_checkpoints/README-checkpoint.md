# skamo3 README
 - Input = (96,96,1)
 - Conv = Convolutional layer
 - BN = BatchNormalization
 - MP = MaxPolling
 - DO = DropOut
 - GAP = GlovalAveragePooling
 - Output = 7
 - LeRU = LeakyReLU
## Test 1
 - (Conv8-BN-ReLU)x3-MP-DO -> (Conv32-BN-ReLU)x3-MP-DO -> (Conv64-BN-ReLU)x3-MP-DO -> (Conv128-BN-ReLU)x3-MP-DO -> GAP -> Dense256(ReLU) -> Dense128(ReLU) -> Dense7(softmax)
 - Conv option : padding = same / kernal size = 3,3 / stride = 1 
 - BatchSize : 32
 - epochs : 60
 - learning rate : 0.001
 
 ### Test Result
 - loss : 0.3132
 - train accuracy : 0.8855
 - test accuracy : 0.6439  
 

## Test 2
 - Conv96-BN-ReLU-MP-DO -> Conv128-BN-ReLU-MP-DO -> Conv96-BN-ReLU-MP-DO -> Conv96-BN-ReLU-MP-DO -> GAP -> Dense96(ReLU) -> Dense32(ReLU) -> Dense7(softmax)
 - BatchSize : 64 
 - epochs : 250
 - learning rate : 0.003
 
 ### Test Result
 - loss : 0.3775
 - train accuracy : 0.8608
 - test accuracy : 0.6119
 
 ## Test 3
 - (Conv16-LeRU)x3-BN(before LeRU)-MP-DO(0.3) -> (Conv32-LeRU)x3-BN(before LeRU)-MP-DO(0.3) -> (Conv64-LeRU)x3-BN(before LeRU)-MP-DO(0.3) -> (Conv128-LeRU)x3-BN(before LeRU)-MP-DO(0.3) -> (Conv256-LeRU)x3-BN(before LeRU)-MP-DO(0.3) -> GAP -> Dense96(LeRU) -> Dense32(LeRU) -> Dense7(softmax)
 - BatchSize : 96
 - epoch : 300
 - learning rate : 0.003
 
 ### Test Result
 - loss : 0.0763
 - train accuracy : 0.9736
 - test accuracy : 0.6570
 