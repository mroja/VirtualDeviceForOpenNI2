# location of the Boost Python include files and library
OPENNI2_INC = ../../kinect/Include
OPENNI2_LIB = ../../kinect/Redist
NITE2_INC = ../../kinect/Include
NITE2_LIB = ../../kinect/Redist
XNLIB_INC = ../../kinect/ThirdParty/PSCommon/XnLib/Include

CC = g++

TARGET = VirtualDevice
OBJS = VirtualDevice.o

$(TARGET).so: $(OBJS)
	$(CC) -shared -Wl,--export-dynamic $^ -L$(OPENNI2_LIB) -L$(NITE2_LIB) -lOpenNI2 -lNiTE2 -o $@

$(OBJS): %.o: %.cpp
	$(CC) -O2 -I$(NITE2_INC) -I$(OPENNI2_INC) -I$(XNLIB_INC) -std=gnu++11 -fPIC -c $< -o $@

clean:
	rm -f *.o
	rm -f *.so

.PHONY: clean

