# my-learning-wiki
Personal knowledge base for embedded security, QNX, and system design.

https://www.lynx.com/blog/dm-verity-without-an-initramfs/


**Once life cycle is moved : **

Once an ECU's lifecycle is advanced to the Production State, traditional open JTAG and UART lines are permanently disabled via internal hardware e-fuses to minimize the vehicle's physical attack surface. To debug a production unit, we utilize a Secure Debug Authentication framework.We pull the chip's unique hardware ID via standard UDS diagnostics and submit it to the OEM's secure certificate authority. The server generates a device-specific, time-bounded cryptographic unlock token signed by the OEM private key. When injected back into the ECU, the HSM acts as the gatekeeper—verifying the certificate using its internal secure root of trust. Upon a successful match, the HSM temporarily updates the hardware debug registers, re-enabling JTAG visibility exclusively for that debugging session. Once power is cycled or the token expires, the hardware automatically re-locks itself, ensuring production integrity.
