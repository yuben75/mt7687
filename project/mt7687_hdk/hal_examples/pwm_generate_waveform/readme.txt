/* Copyright Statement:
 *
 * (C) 2005-2016  MediaTek Inc. All rights reserved.
 *
 * This software/firmware and related documentation ("MediaTek Software") are
 * protected under relevant copyright laws. The information contained herein
 * is confidential and proprietary to MediaTek Inc. ("MediaTek") and/or its licensors.
 * Without the prior written permission of MediaTek and/or its licensors,
 * any reproduction, modification, use or disclosure of MediaTek Software,
 * and information contained herein, in whole or in part, shall be strictly prohibited.
 * You may only use, reproduce, modify, or distribute (as applicable) MediaTek Software
 * if you have agreed to and been bound by the applicable license agreement with
 * MediaTek ("License Agreement") and been granted explicit permission to do so within
 * the License Agreement ("Permitted User").  If you are not a Permitted User,
 * please cease any access or use of MediaTek Software immediately.
 * BY OPENING THIS FILE, RECEIVER HEREBY UNEQUIVOCALLY ACKNOWLEDGES AND AGREES
 * THAT MEDIATEK SOFTWARE RECEIVED FROM MEDIATEK AND/OR ITS REPRESENTATIVES
 * ARE PROVIDED TO RECEIVER ON AN "AS-IS" BASIS ONLY. MEDIATEK EXPRESSLY DISCLAIMS ANY AND ALL
 * WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE IMPLIED WARRANTIES OF
 * MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE OR NONINFRINGEMENT.
 * NEITHER DOES MEDIATEK PROVIDE ANY WARRANTY WHATSOEVER WITH RESPECT TO THE
 * SOFTWARE OF ANY THIRD PARTY WHICH MAY BE USED BY, INCORPORATED IN, OR
 * SUPPLIED WITH MEDIATEK SOFTWARE, AND RECEIVER AGREES TO LOOK ONLY TO SUCH
 * THIRD PARTY FOR ANY WARRANTY CLAIM RELATING THERETO. RECEIVER EXPRESSLY ACKNOWLEDGES
 * THAT IT IS RECEIVER'S SOLE RESPONSIBILITY TO OBTAIN FROM ANY THIRD PARTY ALL PROPER LICENSES
 * CONTAINED IN MEDIATEK SOFTWARE. MEDIATEK SHALL ALSO NOT BE RESPONSIBLE FOR ANY MEDIATEK
 * SOFTWARE RELEASES MADE TO RECEIVER'S SPECIFICATION OR TO CONFORM TO A PARTICULAR
 * STANDARD OR OPEN FORUM. RECEIVER'S SOLE AND EXCLUSIVE REMEDY AND MEDIATEK'S ENTIRE AND
 * CUMULATIVE LIABILITY WITH RESPECT TO MEDIATEK SOFTWARE RELEASED HEREUNDER WILL BE,
 * AT MEDIATEK'S OPTION, TO REVISE OR REPLACE MEDIATEK SOFTWARE AT ISSUE,
 * OR REFUND ANY SOFTWARE LICENSE FEES OR SERVICE CHARGE PAID BY RECEIVER TO
 * MEDIATEK FOR SUCH MEDIATEK SOFTWARE AT ISSUE.
 */

/** 
  * @page hal_pwm PWM example project 
  * @{

@par Overview

 - Example project description
   - This example project shows the useage of APIs of PWM module and it runs without FreeRTOS.
 - Features of the example project
   - This example project demonstrates how to produce a waveform which has a fixed frequency 200Hz
     and a fixed duty cycle ratio 50%.
 - Process / procedure of the example
   - Input to the example
      - 32KHz source clock.
   - Output from the example
      - Log will show the fixed PWM frequency and duty cycle.

@par Hardware and Software environment

  - Supported platform
    - LinkIt MT7687 HDK
  - HDK switches and pin configuration
    - PWM module channel mapping is listed below.
  |CHx	|GPIOx	|PINx	|
  |-------	|--------- 	|---------	|
  |  0	|  0	|J35.6 |

- PC/environment configuration
   - A serial tool is required, such as hyper terminal, for UART logging.
   - COM port settings. baudrate: 115200, data bits: 8, stop bit: 1, parity: none and flow control: off.

@par Directory contents
  - Source and header files
   - hal_examples/pwm_generate_waveform/src/main.c  			       Main program.
   - hal_examples/pwm_generate_waveform/src/system_mt7687.c		       MT76x7's clock configuration file.
   - hal_examples/pwm_generate_waveform/inc/hal_feature_config.h 	       MT76x7's feature configuration file.
   - hal_examples/pwm_generate_waveform/inc/flash_map.h		               MT76x7's memory layout symbol file.
   - hal_examples/pwm_generate_waveform/GCC/startup_mt7687.s		       MT76x7's startup file for GCC.
   - hal_examples/pwm_generate_waveform/GCC/syscalls.c			       MT76x7's syscalls for GCC.
   - hal_examples/pwm_generate_waveform/MDK-ARM/startup_mt7687.s	       MT76x7's startup file for Keil.

  - Project configuration files using GCC
   - hal_examples/pwm_generate_waveform/GCC/feature.mk		    	        Feature configuration .
   - hal_examples/pwm_generate_waveform/GCC/Makefile		 	        Makefile.
   - hal_examples/pwm_generate_waveform/GCC/mt7687_flash.ld			Linker script.

  - Project configuration files using Keil
   - hal_examples/pwm_generate_waveform/MDK-ARM/pwm_generate_waveform.uvprojx		uVision5 project file. Contains the project structure in XML format.
   - hal_examples/pwm_generate_waveform/MDK-ARM/pwm_generate_waveform.uvoptx		uVision5 project options. Contains the settings for the debugger, trace configuration, breakpoints, currently open files, etc.
   - hal_examples/pwm_generate_waveform/MDK-ARM/flash.sct		                 Linker script.

  - Project configuration files using IAR
   - hal_examples/pwm_generate_waveform/EWARM/pwm_generate_waveform.ewd		 IAR project options. Contains the settings for the debugger.
   - hal_examples/pwm_generate_waveform/EWARM/pwm_generate_waveform.ewp           IAR project file. Contains the project structure in XML format
   - hal_examples/pwm_generate_waveform/EWARM/pwm_generate_waveform.eww           IAR workspace file. Contains project information.
   - hal_examples/pwm_generate_waveform/EWARM/flash.icf			           Linker script.

@par Run the example
  - Connect board to PC with serial port cable.
  - Build the example project with the command, "./build.sh mt7687_hdk pwm_generate_waveform" from the SDK root folder and download the bin file to LinkIt 7687 development board.
    - Run the example. Use oscilloscope to observe the waveform generated by PWM.

* @}
*/
