
Results on the whole 10,000 test samples:
https://drive.google.com/drive/folders/1cta_VeXOaBPxEeishO2DLXIPJ9F4W7EP?usp=sharing

Download "MNIST_ATK_dat.zip" and extract the folder outside MNIST_ATK.
(Or, extract it anywhere you want and change the variables "dirname" and "dirname_fx" in ReadData.ipynb accordingly.)

Some of them (first 1000) have performance_log plots and the images of the attacked samples
They can be found in "/Res"

Samples are grouped by "testset"s and each testset has its own id (tid), from 0 to 1134.
Each testset has one set of images from 0 to 9 for tid = 0, .., 891.
For tid > 892, there are missing labels due to the unequal number of images for each label.

To be more precise, the number of images for each label is:
[980, 1135, 1032, 1010, 982, 892, 958, 1028, 974, 1009]  (from 0 to 9, respectively)


and each Results_(tid_begin) folder contains the set of results for tid = tid_begin.
( Results_0:    tid from 0 to 2,
  Results_3:    tid from 3 to 102
  Results_103:  tid from 103 to 199
  Results_200:  tid from 200 to 399
  Results_400:  tid from 400 to 599
  Results_600:  tid from 600 to 799
  Results_800:  tid from 800 to 1134 )

"/Results_(tid_begin)/img" have the original/attacked images as 28-by-28 numpy arrays.
e.g. "Results_3/2_22_RING_8.npy" is the attacked image of 2 (with tid=22), where RING method is used, and the classified label is 8 at the final stage.

Theh files "/Results_(tid_begin)/(opt_name).csv" contain the results from each sample.
Each row corresnponds to each sample, and it has the following format:
[tid, original_label, final_label, num_fevals, Status]
Status = "S" (Successful Attack) or "B" (Budget reached).

* Budget = 50,000

