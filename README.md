# How To Build ESP32-S2 ULP Risc-V Lib
## Step1:
Donwload from here to install Risc-v compiler:
```
链接：https://pan.baidu.com/s/1l7vXTXZuo79J7jYcxknL_g 
提取码：zyu5
```
## Step2:
Install Cmake

## Step3:
Edit system environment PATH variable,add compiler bin, cmake, ninja.exe to PATH

## Step4:
```
mkdir build
cd build
cmake .. -G "Ninja"
ninja
```

# LOG Output:
```
-- The C compiler identification is GNU 8.2.0
-- The CXX compiler identification is GNU 8.2.0
-- Configuring done
-- Generating done
-- Build files have been written to: D:/esp32/esp32s2-ulp-standalone/build
```


