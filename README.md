# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
   ![WhatsApp Image 2025-10-29 at 21 24 18_e1875930](https://github.com/user-attachments/assets/6f985ddc-453f-4606-b94a-09d784b85986)

2. Click **File → New STM32 Project**.
   ![WhatsApp Image 2025-10-29 at 21 22 41_167b2bcb](https://github.com/user-attachments/assets/9f053302-fafc-4577-9963-d2dd9a4d2355)
   ![WhatsApp Image 2025-10-29 at 21 28 25_cb3a2e25](https://github.com/user-attachments/assets/3952d7eb-24c3-4437-90b9-95c6f92c2e8f)


3. Select the **target microcontroller** or board and click **Next**.
![WhatsApp Image 2025-10-29 at 21 24 17_b63ece9a](https://github.com/user-attachments/assets/413537e3-eb74-4f73-8dee-a7f7bb0f7b20)


4. Name the project.
   ![WhatsApp Image 2025-10-29 at 21 31 07_bc1617e6](https://github.com/user-attachments/assets/dc437b99-f905-4d87-a78e-67b36362d94b)

5. The corresponding `.ioc` file will be generated automatically.
 ![WhatsApp Image 2025-10-29 at 21 24 18_1979992f](https://github.com/user-attachments/assets/fd2a97f8-4902-4b1e-9735-92d25bfdeaf0)

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
   ![WhatsApp Image 2025-10-29 at 21 35 06_4c9a5a78](https://github.com/user-attachments/assets/18f266e5-6238-4b48-b3a8-12a39c2a4e21)
   ![WhatsApp Image 2025-10-29 at 21 24 17_66581989](https://github.com/user-attachments/assets/bd42390d-c0d7-4197-8d21-dce3550b6e41)

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   ![WhatsApp Image 2025-10-29 at 21 37 33_e8b1d932](https://github.com/user-attachments/assets/dec23e5e-9943-4275-97dc-497d21c5d073)

8. Edit the generated main program as required.
   <img width="1110" height="624" alt="image" src="https://github.com/user-attachments/assets/05b39060-35d6-420d-9f4d-8721439bd82f" />
<img width="1104" height="621" alt="image" src="https://github.com/user-attachments/assets/2ec55709-a45f-4e6e-8738-6aa94138eab1" />

9. Click **Project → Build All**.
    <img width="1080" height="608" alt="image" src="https://github.com/user-attachments/assets/264cd0a8-3e96-4668-822e-838ecfafc527" />

10. Link the **HEX file** using the post-build process.
    <img width="1053" height="465" alt="image" src="https://github.com/user-attachments/assets/478187a0-0ee6-4c50-9cac-c3b5ee18521b" />

11. Click **Debug** and connect the **STM Nucleo Board**.
    <img width="1080" height="608" alt="image" src="https://github.com/user-attachments/assets/f72fff44-6073-4ae4-aa78-0da455df9af1" />

13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

CASE 2: LED OFF

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
