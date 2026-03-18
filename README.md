# EXPERIMENT – 04

# INTERFACING AN 16X2 LCD DISPLAY WITH ARM AND DISPLAY STRING

---

## Aim

To Interface a 16X2 LCD display to ARM controller, and simulate it in Proteus.

---

## Components Required

* STM32 CUBE IDE
* Proteus 8 simulator

---

## Theory

The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.

### What is an ARM7 Processor?

ARM7 processor is commonly used in embedded system applications. Also, it is a balance among classic as well as new-Cortex sequence. This processor is tremendous in finding the resources existing on the internet with excellence documentation offered by NXP Semiconductors. It suits completely for an apprentice to obtain in detail hardware & software design implementation.

STM32F401xB STM32F401xC ARM® Cortex®-M4 32b MCU+FPU, 105 DMIPS, 256KB Flash/64KB RAM, 11 TIMs, 1 ADC, 11 comm interfaces Datasheet - production data.

### Features

* Core: ARM® 32-bit Cortex®-M4 CPU with FPU
* Adaptive real-time accelerator (ART Accelerator™) allowing 0-wait state execution from Flash memory
* Frequency up to 84 MHz
* Memory protection unit
* 105 DMIPS / 1.25 DMIPS/MHz (Dhrystone 2.1)
* DSP instructions

### Memories

* Up to 256 Kbytes of Flash memory
* Up to 64 Kbytes of SRAM

---

# LCD 16X2

16×2 LCD is named so because it has **16 Columns and 2 Rows**. There are a lot of combinations available like:

* 8×1
* 8×2
* 10×2
* 16×1

But the most used one is the **16×2 LCD**, hence we are using it here.

All the above mentioned LCD display will have **16 Pins** and the programming approach is also the same and hence the choice is left to you.

Below is the **Pinout and Pin Description of 16x2 LCD Module**:

![image](https://user-images.githubusercontent.com/36288975/233858086-7b1a88a2-f941-475c-86c2-b3bae68bdf7e.png)

![image](https://user-images.githubusercontent.com/36288975/233857710-541ac1c2-786c-4dfc-b7b5-e3a4868a9cb6.png)

![image](https://user-images.githubusercontent.com/36288975/233857733-05df5dbf-1a1e-479e-85bb-8014a39ad878.png)

---

# 4-bit and 8-bit Mode of LCD

The LCD can work in two different modes:

* **4-bit mode**
* **8-bit mode**

### 4-bit Mode

In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble.

For those of you who don’t know what a nibble is:
A **nibble** is a group of four bits.

* Lower four bits (D0–D3) form the **lower nibble**
* Upper four bits (D4–D7) form the **higher nibble**

This enables us to send **8-bit data**.

### 8-bit Mode

In 8 bit mode we can send the **8-bit data directly in one stroke** since we use all the **8 data lines**.

8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs **8 data lines connected to the microcontroller**. This will make us run out of I/O pins on our MCU, so **4-bit mode is widely used**.

No control pins are used to set these modes.

---

# LCD Commands

There are some preset command instructions in LCD which we need to send to LCD through some microcontroller.

Some important command instructions are given below:

| Hex Code | Command to LCD Instruction Register      |
| -------- | ---------------------------------------- |
| 0F       | LCD ON, cursor ON                        |
| 01       | Clear display screen                     |
| 02       | Return home                              |
| 04       | Decrement cursor (shift cursor to left)  |
| 06       | Increment cursor (shift cursor to right) |
| 05       | Shift display right                      |
| 07       | Shift display left                       |
| 0E       | Display ON, cursor blinking              |
| 80       | Force cursor to beginning of first line  |
| C0       | Force cursor to beginning of second line |
| 38       | 2 lines and 5×7 matrix                   |
| 83       | Cursor line 1 position 3                 |
| 3C       | Activate second line                     |
| 08       | Display OFF, cursor OFF                  |
| C1       | Jump to second line, position 1          |
| 0C       | Display ON, cursor OFF                   |
| C1       | Jump to second line, position 1          |
| C2       | Jump to second line, position 2          |

---

# Procedure

### 1.

Click on **STM 32 CUBE IDE**, the following screen will appear.

![image](https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png)

---

### 2.

Click on **FILE**, then click on **New STM32 Project**.

![image](https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png)

![image](https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png)

---

### 3.

Select the **target to be programmed** as shown below and click **Next**.

![image](https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png)

---

### 4.

Select the **program name**.

![image](https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png)

---

### 5.

Corresponding **IOC file will be generated automatically**.

![image](https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png)

---

### 6.

Select the appropriate pins as **GPIO (input/output), USART or required options** and configure.

![image](https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png)

![image](https://user-images.githubusercontent.com/36288975/226189425-2b2414ce-49b3-4b61-a260-c658cb2e4152.png)

---

### 7.

Click **Ctrl + S**, automatically the **C program will be generated**.

![image](https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png)

![image](https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png)

---

### 8.

Edit the program as per requirement.

![image](https://user-images.githubusercontent.com/36288975/226189461-a573e62f-a109-4631-a250-a20925758fe0.png)

---

### 9.

Add necessary **library files of LCD 16x2**, write the program and **build the project**.

![image](https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png)

---

### 10.

Once the **project is build**.

![image](https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png)

---

### 11.

Click on **Debug option**.

![image](https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png)

---

### 12. Creating Proteus Project and Running the Simulation

We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.

---

### 13.

Create a **new Proteus project** and place **STM32F40xx**, the same MCU for which the project was created in STM32Cube IDE.

---

### 14.

After creation of the circuit as per requirement as shown below.

![image](https://user-images.githubusercontent.com/36288975/233856847-32bea88a-565f-4e01-9c7e-4f7ed546ddf6.png)

Double click on the MCU part to open settings. Next to the **Program File option**, give full path to the **Hex file generated using STM32Cube IDE**. Then set the **external crystal frequency to 8M (8 MHz)** and click **OK**.

[https://engineeringxpert.com/wp-content/uploads/2022/04/26.png](https://engineeringxpert.com/wp-content/uploads/2022/04/26.png)

---

### 15.

Click on **Debug and simulate** using simulation as shown below.

![image](https://user-images.githubusercontent.com/36288975/233856904-99eb708a-c907-4595-9025-c9dbd89b8879.png)

---

# Circuit Diagram

![image](https://user-images.githubusercontent.com/36288975/233857974-bda6200e-4f88-4e7b-b189-4da80210fa23.png)

---

# STM32 CUBE PROGRAM

### lcd.h

```c
#ifndef __LCD_H
#define __LCD_H

#include "stm32f1xx_hal.h"  // change based on MCU

void LCD_Init(void);
void LCD_Send_Command(uint8_t cmd);
void LCD_Send_Data(uint8_t data);
void LCD_Send_String(char *str);
void LCD_Set_Cursor(uint8_t row, uint8_t col);

#endif
```

---

### lcd.c

```c
#include "lcd.h"

// Pin definitions
#define RS_PIN GPIO_PIN_0
#define EN_PIN GPIO_PIN_1
#define D4_PIN GPIO_PIN_2
#define D5_PIN GPIO_PIN_3
#define D6_PIN GPIO_PIN_4
#define D7_PIN GPIO_PIN_5

#define LCD_PORT GPIOA

void LCD_Enable_Pulse()
{
    HAL_GPIO_WritePin(LCD_PORT, EN_PIN, GPIO_PIN_SET);
    HAL_Delay(1);
    HAL_GPIO_WritePin(LCD_PORT, EN_PIN, GPIO_PIN_RESET);
    HAL_Delay(1);
}

void LCD_Send_4Bits(uint8_t data)
{
    HAL_GPIO_WritePin(LCD_PORT, D4_PIN, (data & 0x01) ? GPIO_PIN_SET : GPIO_PIN_RESET);
    HAL_GPIO_WritePin(LCD_PORT, D5_PIN, (data & 0x02) ? GPIO_PIN_SET : GPIO_PIN_RESET);
    HAL_GPIO_WritePin(LCD_PORT, D6_PIN, (data & 0x04) ? GPIO_PIN_SET : GPIO_PIN_RESET);
    HAL_GPIO_WritePin(LCD_PORT, D7_PIN, (data & 0x08) ? GPIO_PIN_SET : GPIO_PIN_RESET);
}

void LCD_Send_Command(uint8_t cmd)
{
    HAL_GPIO_WritePin(LCD_PORT, RS_PIN, GPIO_PIN_RESET);

    LCD_Send_4Bits(cmd >> 4);
    LCD_Enable_Pulse();

    LCD_Send_4Bits(cmd & 0x0F);
    LCD_Enable_Pulse();

    HAL_Delay(2);
}

void LCD_Send_Data(uint8_t data)
{
    HAL_GPIO_WritePin(LCD_PORT, RS_PIN, GPIO_PIN_SET);

    LCD_Send_4Bits(data >> 4);
    LCD_Enable_Pulse();

    LCD_Send_4Bits(data & 0x0F);
    LCD_Enable_Pulse();

    HAL_Delay(2);
}

void LCD_Send_String(char *str)
{
    while (*str) LCD_Send_Data(*str++);
}

void LCD_Set_Cursor(uint8_t row, uint8_t col)
{
    uint8_t addr = (row == 0) ? 0x80 + col : 0xC0 + col;
    LCD_Send_Command(addr);
}

void LCD_Init()
{
    HAL_Delay(50);

    LCD_Send_4Bits(0x03);
    LCD_Enable_Pulse();
    HAL_Delay(5);

    LCD_Send_4Bits(0x03);
    LCD_Enable_Pulse();
    HAL_Delay(1);

    LCD_Send_4Bits(0x03);
    LCD_Enable_Pulse();

    LCD_Send_4Bits(0x02); // 4-bit mode
    LCD_Enable_Pulse();

    LCD_Send_Command(0x28); // 4-bit, 2 line
    LCD_Send_Command(0x0C); // display ON
    LCD_Send_Command(0x06); // entry mode
    LCD_Send_Command(0x01); // clear
    HAL_Delay(2);
}
```

---

## 4. main.c (Application)

```c
#include "main.h"
#include "lcd.h"

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    LCD_Init();

    LCD_Set_Cursor(0, 0);
    LCD_Send_String("Hello STM32");

    LCD_Set_Cursor(1, 0);
    LCD_Send_String("16x2 LCD");

    while (1)
    {
    }
}
```

---



# Output Screen Shots of Proteus

![WhatsApp Image 2025-04-11 at 08 18 23\_0eb0cec0](https://github.com/user-attachments/assets/d698f4a8-df57-4ca0-966b-1231c9651aab)

---

# CIRCUIT DIAGRAM (EXPORT THE GRAPHICS TO PDF AND ADD THE SCREEN SHOT HERE)

![WhatsApp Image 2025-04-11 at 08 20 16\_5ded175e](https://github.com/user-attachments/assets/9c7b05af-cbdc-4e6a-b6f1-a6595b266404)

---

# Result

Interfacing a lcd display with ARM microcontroller are simulated in proteus and the results are verified.

