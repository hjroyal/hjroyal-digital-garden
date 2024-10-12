- [用Python，实现时域和频域的FFT图像呈现 (qq.com)](https://mp.weixin.qq.com/s?__biz=Mzk0NzU5NDE0Ng==&mid=2247484064&idx=1&sn=cb0e4cdfb21726138829652eedac1d7c&chksm=c375346df402bd7bb064782d7b142d3cb8932349ce4f0759f98dc13d8f29e545db686d4ea457&mpshare=1&scene=1&srcid=0421bhOQ4XrYu568cylAjBLK&sharer_shareinfo=fba85fcda32d6ae2941510c41f497778&sharer_shareinfo_first=fba85fcda32d6ae2941510c41f497778#rd)
- [[python]]实现傅里叶变换
- python
	- ```python
	  import numpy as np
	  from scipy.fftpack import fft
	  import matplotlib.pyplot as plt
	  import matplotlib.gridspec as gc
	  
	  
	  def FFT(Fs, data):
	      """
	      对输入信号进行FFT
	      :param Fs:  采样频率
	      :param data:待FFT的序列
	      :return:
	      """
	      L = len(data)  # 信号长度
	      N = np.power(2, np.ceil(np.log2(L)))  # 下一个最近二次幂，也即N个点的FFT
	      result = np.abs(fft(x=data, n=int(N))) / L * 2  # N点FFT
	      axisFreq = np.arange(int(N / 2)) * Fs / N  # 频率坐标
	      result = result[range(int(N / 2))]  # 因为图形对称，所以取一半
	      return axisFreq, result
	  
	  if __name__ == '__main__':
	      Fs = 8000  # 采样频率
	      f1 = 820   # 信号频率1
	      f2 = 2500   # 信号频率2
	  
	      t = np.linspace(0, 1, Fs)  # 生成 1s 的时间序列
	      time_mag=1000
	      # 给定信号
	      y1 = 2 * np.sin(2 * np.pi * f1 * t)
	      y2 = 5 * np.sin(2 * np.pi * f2 * t)
	      y_init = y1 + y2
	      noise =2* np.random.normal(0, 5, len(y_init))
	      y_comp = y1 + y2 + noise
	  
	      y1_mag = 2 * np.sin(2 * np.pi * f1 * t/time_mag)
	      y2_mag = 5 * np.sin(2 * np.pi * f2 * t/time_mag)
	      y_init_mag = y1_mag + y2_mag
	  
	  
	      # 第一步，对没有添加噪声的信号进行FFT，验证分析是否正确
	      x_init, result_init = FFT(Fs, y_init)
	      x_comp, result_comp = FFT(Fs, y_comp)
	  
	      # 绘图
	      fig = plt.figure(figsize=(8, 8))
	      spec=gc.GridSpec(3,4,wspace=1,hspace=0.5)
	  
	      fig.add_subplot(spec[0,0:2])
	      plt.plot(t, y1_mag,color='green')
	      plt.title('SG1')
	      plt.xlabel('Time/ms')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      fig.add_subplot(spec[0,2:4])
	      plt.plot(t, y2_mag,color='green')
	      plt.title('SG2')
	      plt.xlabel('Time/ms')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      fig.add_subplot(spec[1,2:4])
	      plt.plot(t, noise,color='green')
	      plt.title('Noise')
	      plt.xlabel('Time/ms')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      fig.add_subplot(spec[1,0:2])
	      plt.plot(t, y_init_mag,color='blue')
	      plt.title('SG1+SG2')
	      plt.xlabel('Time/ms')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      fig.add_subplot(spec[2,0:2])
	      plt.plot(x_init, result_init,color='red')
	      plt.title('FFT-SG1+SG2')
	      plt.xlabel('Frequency/Hz')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      fig.add_subplot(spec[2,2:4])
	      plt.plot(x_comp, result_comp,color='red')
	      plt.title('FFT-SG1+SG2+noise')
	      plt.xlabel('Frequency/Hz')
	      plt.ylabel('Amplitude')
	      plt.grid()
	  
	      plt.show()
	  
	  ```