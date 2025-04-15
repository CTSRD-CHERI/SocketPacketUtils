Socket Packet Utils aims to provide hardware simulators with primitives used to interface with UNIX sockets.
It enables easy communication of bits of data straight from simulated signals to an external UNIX process for arbitrary processing.
It also enables external data to be delivered to the simulated hardware.
This can serve for example to help tracing circuit state, or allow a software generator to provide stimuli in a straight-forward manner.

It exposes the following primitives:

```C
unsigned long long serv_socket_create(const char * name, unsigned int dflt_port);
unsigned long long serv_socket_create_nameless(unsigned int dflt_port);
void serv_socket_init(unsigned long long ptr);
uint32_t serv_socket_get8(unsigned long long ptr);
uint8_t serv_socket_put8(unsigned long long ptr, uint8_t byte);
uint8_t serv_socket_put8_blocking(unsigned long long ptr, uint8_t byte);
void serv_socket_getN(void* result, unsigned long long ptr, int nbytes);
uint8_t serv_socket_putN(unsigned long long ptr, int nbytes, unsigned int* data);
unsigned long long client_socket_create(const char * name, unsigned int dflt_port);
void client_socket_init(unsigned long long ptr);
uint8_t client_socket_put8_blocking(unsigned long long ptr, uint8_t byte);
void client_socket_getN(void* result, unsigned long long ptr, int nbytes);
```
