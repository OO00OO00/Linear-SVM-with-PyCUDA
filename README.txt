Date:
2018-06-01

Author:
WRF

Description:
This project demonstrates how PyCUDA can be used to build a linear support vector machine using the Huberized squared hinge loss.

Setup (other than installing packages denoted in the scripts):
- GPU
- Install NVIDIA GPU Computing Toolkit with CUDA v9.2: https://developer.nvidia.com/cuda-downloads
- Install MS Visual Studio 2017 Community version (v14.14.26428 worked for me)

Notes: You may need to do the following:
1) In the file host_config.h found here,
	C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.2\include\crt
change line 131 from:
	#if _MSC_VER < 1600 || _MSC_VER > 1913
to:
	#if _MSC_VER < 1600	
This prevents an error being thrown by PyCUDA. Although this has let me use PyCUDA, I do not know it's other ramifications!

2) In %PYTHON%\Lib\site-packages\skcuda, you may need to manually set the location of the relevant cublas.dll file. For me, this DLL file is in:
	%PYTHON%\DLL
	