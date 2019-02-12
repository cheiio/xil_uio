# xil_uio

Xil Uio is a C language handler for PL devices on Xilinx FPGA using petalinux and the uio drivers:
It has a struct type that functions as a handler of /dev/uio* device on petalinux
These are the following functions:

//*************** Create Handler  ***************//

1. xil_uio* xil_uio__create(const char *_uio_dev, const uint32_t _uio_size);    // Creates UIO handler for /dev/uio* device

2. void xil_uio__destroy(xil_uio* self);                           // Destroys UIO handler for /dev/uio* device

//************** Private Variables *************//

3. uint32_t xil_uio__mapSize(xil_uio* self);     // Public method that contains mapsize

4. uint32_t xil_uio__fd(xil_uio* self);          // Public method that contains fd /dev/uio* file pointer

5. void*    xil_uio__virtAddr(xil_uio* self);    // Public method that contains virtual mem address for /dev/uio*

//******** Read and Write to PL devices ********//

6. uint32_t xil_uio__read32(xil_uio* self, const uint32_t offset); // reads data from virtual mem address with offset

7. void xil_uio__write32 (xil_uio* self, const uint32_t offset, const uint32_t writeval); 

Every data send is 32bit wide max
