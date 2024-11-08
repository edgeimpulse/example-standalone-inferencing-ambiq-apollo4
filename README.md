# Edge Impulse Example: standalone inferencing (Ambiq Apollo 4)

This runs an exported impulse on Ambiq Apollo 4 EVB.

## Prerequisites
1. Apollo 4 EVB (Plus / Blue / Blue Plus)
2. GCC v13.x.x
3. [Segger Jlink software](https://www.segger.com/downloads/jlink/)

4. In Edge Impulse Platform: deploy the impulse you want to test as a C++ library and copy the contents of the resulting ZIP (`model-parameters`, `tflite-model` and `edge-impulse-sdk` folders) into [src/edge-impulse](src/edge-impulse)

5. Paste the raw features array in the following array in `src/ei_main.cpp`
```
static const float features[] = {
    // copy raw features here
};
```

## Build
To build the application:
```bash
make -j `nproc`
```

To clean the build:
```bash
make clean
```

## Flash
To flash the board, first connect the EVK via Segger USB port on the board and run:
```bash
make deploy
```

## Debug on VsCode
> [!IMPORTANT]
> You need to install [JLink software](https://www.segger.com/downloads/jlink/) and [Cortex-Debug](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug) extension.
To start a debug session, make sure to connect the board to J6 (JLINK USB) and press F5.

## Connect to the board
Connect USB-C cables to both APOLLO4 USB connectors.
The board will show as a USB device.
