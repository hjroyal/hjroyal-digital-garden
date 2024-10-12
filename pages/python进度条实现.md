- ```
  pip install tqdm
  pip install rich
  ```
- ```python
  from tqdm.rich import trange
  
  X = 10000
  for i in trange(X):
    for j in range(X):
      k = j*i
  print("完成！")
  ```