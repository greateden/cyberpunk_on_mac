# Benchmarking Cyberpunk 2077 on MacBook Pro M1 (8 CPU + 8 GPU)

## 1. Introduction

With the release of Apple’s M4 chip and the upcoming native macOS version of Cyberpunk 2077, it’s an opportune time to assess how the game performs on earlier hardware. This benchmark aims to evaluate whether Cyberpunk 2077 can run effectively on a MacBook Pro equipped with the M1 chip. The findings serve as a reference for cross-generation capacity comparison and cross-platform performance evaluation.

## 2. Setup and Methodology

Hardware Configuration

	•	Device: MacBook Pro (Late 2020)
	•	Processor: Apple M1 chip (8-core CPU, 8-core GPU)
	•	Memory: 8 GB RAM
	•	Storage: 256 GB SSD
	•	Operating System: macOS Sequoia 15.2 beta

Software Configuration

	•	Virtual Machine: Whiskey (free virtualization tool)
	•	Container OS: Initially Windows 11, later shifted to Windows 10 for better performance
	•	Virtual Machine Settings:
	•	DXVK: Disabled
	•	AVX: Disabled
	•	Synchronization: Esync enabled (instead of Msync)
	•	Metal HUD: Enabled (optional for performance monitoring)

In-Game Settings

	•	Resolution: 1280×960 (lowest available)
	•	VSync: Disabled
	•	Graphics Preset: Low (all settings adjusted to lowest or off)
	•	Post-Benchmark Adjustments:
	•	FSR3: Disabled
	•	FFX2.1: Enabled with Ultra Performance mode
	•	Image Sharpening: Set to 1

## 3. Results

General Frame Rates

	•	Benchmark Average: ~22 FPS
	•	Simple Environments: 30–40 FPS
	•	Complex Environments (e.g., Driving): ~8 FPS

Detailed Benchmark Data

Anisotropic Filtering

	•	4× Anisotropy yielded the best performance unexpectedly.

Performance with Esync (in Whiskey)

With FSR3 and FFX3-AA

	•	Windows 11 Container:
	•	Average FPS: 14.94
	•	Minimum FPS: 9.17
	•	Maximum FPS: 42.18
	•	Windows 10 Container:
	•	Average FPS: 17.87
	•	Minimum FPS: 10.99
	•	Maximum FPS: 47.96

Based on these results, the container was switched to Windows 10 for subsequent tests.

Additional Settings under FSR3 and FFX3-AA

	•	With AVX Enabled:
	•	Average FPS: 15.29
	•	Minimum FPS: 9.77
	•	Maximum FPS: 46.94
	•	Without Enhancing Sync:
	•	Average FPS: 13.77
	•	Minimum FPS: 8.40
	•	Maximum FPS: 45.73
	•	With Msync Instead of Esync:
	•	Average FPS: 15.62
	•	Minimum FPS: 8.87
	•	Maximum FPS: 40.08

Performance with Esync and Without FSR3

Various FFX3 Settings

	•	FFX3-AA:
	•	Average FPS: 17.96
	•	Minimum FPS: 7.33
	•	Maximum FPS: 31.51
	•	FFX3-DRS:
	•	Average FPS: 17.76
	•	Minimum FPS: 6.62
	•	Maximum FPS: 43.02
	•	FFX3-Quality:
	•	Average FPS: 15.59
	•	Minimum FPS: 6.53
	•	Maximum FPS: 39.53
	•	FFX3-Performance:
	•	Average FPS: 15.97
	•	Minimum FPS: 5.60
	•	Maximum FPS: 45.81
	•	Without FFX3:
	•	Average FPS: 13.83
	•	Minimum FPS: 6.26
	•	Maximum FPS: 34.53

FFX2.1 Settings

	•	Ultra Performance Mode (Image Sharpening = 0.7):
	•	Average FPS: 19.74
	•	Minimum FPS: 6.67
	•	Maximum FPS: 48.13
	•	Image Sharpening Adjustments:
	•	Image Sharpening = 1:
	•	Average FPS: 21.19
	•	Minimum FPS: 7.79
	•	Maximum FPS: 48.03
	•	Image Sharpening = 0:
	•	Average FPS: 13.30
	•	Minimum FPS: 5.92
	•	Maximum FPS: 45.57
	•	FFX2.1-DRS:
	•	Average FPS: 14.27
	•	Minimum FPS: 6.04
	•	Maximum FPS: 44.27
	•	FFX2.1-Quality:
	•	Average FPS: 17.15
	•	Minimum FPS: 6.33
	•	Maximum FPS: 40.59

Intel Xe Boost

	•	Performance:
	•	Average FPS: 2.21
	•	Minimum FPS: 1.43
	•	Maximum FPS: 4.52

_Note: Other running processes may have affected the results. This is not formal research, and the results may vary._

## 4. Analysis (By GPT-o1 preview)

Given the data, several insights emerge:

	1.	Operating System Impact: Switching from Windows 11 to Windows 10 in the virtual machine container improved average FPS by approximately 3 frames. This suggests that Windows 10 is better optimized for virtualization on the M1 chip in this context.
 
	2.	Anisotropic Filtering: An unexpected finding was that setting anisotropy to 4× provided the best performance. This could indicate that certain mid-level graphics settings strike a better balance between quality and performance on the M1 GPU.
 
	3.	Synchronization Methods:
	•	Esync vs. Msync: Esync consistently outperformed Msync, implying better thread synchronization handling within the virtualized environment.
	•	Enhancing Sync: Disabling Enhancing Sync resulted in lower FPS, indicating its positive role in performance optimization.
 
	4.	Advanced Vector Extensions (AVX): Enabling AVX slightly decreased performance, possibly due to inefficient emulation of AVX instructions on the M1 architecture within the virtualization layer.
 
	5.	FSR3 and FFX Technologies:
	•	FSR3: Disabling FSR3 led to performance gains, suggesting it may not be fully compatible or optimized for this setup.
	•	FFX3 vs. FFX2.1: FFX2.1 in Ultra Performance mode with image sharpening set to 1 provided the highest average FPS (21.19). Adjusting image sharpening significantly impacted performance, with higher values yielding better results.
 
	6.	Intel Xe Boost: Activating Intel Xe Boost drastically reduced performance. This feature may not be compatible with the M1 chip or may not function correctly within the virtualized environment.
 
	7.	Environmental Complexity: The FPS dropped notably in complex environments like driving scenarios, highlighting the M1 GPU’s limitations in handling graphically intensive scenes in Cyberpunk 2077 under virtualization.

## 5. Conclusion and Recommendations

Running Cyberpunk 2077 on a MacBook Pro with an M1 chip via virtualization is possible but comes with significant performance limitations. While acceptable frame rates can be achieved in less demanding scenarios, the overall experience is hindered by low FPS in complex environments.

***
Recommendations:
	•	General Users: It’s not advisable to play Cyberpunk 2077 on this setup unless for experimental purposes.
	•	Await Native Support: Performance may improve with the anticipated native macOS release of Cyberpunk 2077.
	•	Optimization Tips:
	•	Use Windows 10 as the container OS in Whiskey.
	•	Enable Esync and keep Enhancing Sync active.
	•	Disable FSR3 and utilize FFX2.1 in Ultra Performance mode.
	•	Set image sharpening to 1 for the best balance between visual clarity and performance.
	•	Hardware Upgrade: Consider upgrading to newer hardware with improved GPU capabilities, such as devices equipped with the M4 chip, for a better gaming experience.
 ***

_Note: The performance data provided is based on informal testing and may not reflect all user experiences. Other applications running concurrently can affect game performance._
