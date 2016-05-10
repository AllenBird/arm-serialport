# arm-serialport
Node.js package to access serial ports. Run in arm-cortex-a5
## NOTE
This project has merged with serialport. Future development will continue there. I will be depricating this module in the future.
### STEP1
```
npm install node-gyp -g
git clone git@github.com:AllenBird/arm-serialport.git
cd arm-serialport
npm install
```

### STEP2
```
export AR=arm-none-linux-gnueabi-ar
export CC=arm-none-linux-gnueabi-gcc
export CXX=arm-none-linux-gnueabi-g++
export LINK=arm-none-linux-gnueabi-g++
export CCFLAGS="-march=armv7-a -mtune=cortex-a5 -mfpu=vfpv4 -mfloat-abi=soft"
export CXXFLAGS="-march=armv7-a -mtune=cortex-a5 -mfpu=vfpv4 -mfloat-abi=soft"

node-gyp --arch=arm configure
node-gyp --arch=arm rebuild
```

## STEP3
```
tar cvf arm-serialport.tar arm-serialport
cd bin
node serialport-list.js
```
到ARM上运行node serialport-list.js进行测试
