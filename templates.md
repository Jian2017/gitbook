# templates

## Monte Carlo update and save data to hdf5

Becoming a super hero is a fairly straight forward process:

```python
import numpy as np
import h5py

class Ising1D:
    def __init__(self,L=32,t=1,alpha=0):
        self.s=np.random.choice(a=[False, True], size=(L,1), p=[0.5,0.5])
        self.L=L
        self.t=t
        self.alpha=alpha
        
    def update(self):
        # 这是随便的模拟　为了学会读取数据而言
        i=np.random.randint(0,self.L)
        ia=(i-1)%self.L
        ib=(i+1)%self.L
      #  print(self.s[ia]*1+self.s[ib]*1)
        if np.random.randint(2)==0:
            self.s[i]=not(self.s[i])
            
    def run(self,steps=30):
        f = h5py.File("mytestfile0.hdf5", "a")
        dset = f.create_dataset("bigBOOL",data=self.s,chunks=True,maxshape=(self.L,None))
        
        for i in range(steps):
            if i%1000==0:
                print(i)
            self.update()
            dset.resize(dset.shape[1]+1, axis=1)
            dset[:,-1:]=self.s
                
        f.close()
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```



