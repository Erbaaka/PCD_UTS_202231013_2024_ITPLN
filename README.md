
# UTS Pengolahan Citra Digital 

Pada kesempatan kali ini, saya akan menjelaskan terkait dengan hasil pengolahan citra. Citra yang akan digunakan merupakan citra dari nama lengkap dengan menggunakan warna Biru(Blue), Hijau(Green), Merah(Red) atau sering disingkat dengan BGR. Warna BGR sendiri adalah warna default dari OpenCV.

# Pendeteksian Warna
Pada citra ini, akan diolah menjadi sebuah citra untuk mendeteksi adanya warna utama dalam citra tersebut. Pendeteksiannya dengan mengubah mode warna dari BGR menjadi HSV. HSV atau Hue Saturation Value adalah model warna yang mendeskripsikan suatu warna terhadap shade(saturasi) dan kecerahan(value).

![biru_terdeteksi](https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/c1bb8d35-80d3-466f-82b4-c8449f5584a9)
![hijau_terdeteksi](https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/17483c3a-51e0-4841-b881-89cff28b2727)
![merah_terdeteksi](https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/06ab4ea0-5575-4cbc-9776-6f046ae26249)

Dapat terlihat bahwa gambar diatas merupakan hasil dari proses pendeteksian warna, hanya saja warna hijau tidak dapat dideteksi dengan jelas. Untuk mendeteksinya menggunakan lower_warna dan upper_warna dengan teknik masking. Setelah di masking, maka warna akan secara otomatis terdeteksi.

Penyebab warna hijau tidak terlalu terlihat bahkan tak terdeteksi bisa saja karena pemilihan nilai lower dan upper value yang kurang tepat.

<img width="407" alt="histogram_biru" src="https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/027fe96e-95ca-43b9-b7d7-b1c8dfdf9c03">
<img width="409" alt="histogram_hijau" src="https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/5197b896-9c58-4f87-ba90-50c56004fd0d">
<img width="404" alt="histogram_merah" src="https://github.com/Erbaaka/PCD_UTS_202231013_2024_ITPLN/assets/88221760/17633614-326f-4ec8-a56f-9592db98b84c">

Menurut dokumentasi OpenCV, histogram merupakan representasi secara grafis mengenai intensitas distribusi daripada gambar atau citra. Histogram pada gambar diatas memiliki bentuk puncak tunggal yang terletak pada nilai intensitas sekitar 128. Hal ini dapat disimpulkan bahwa sebagian besar piksel dalam gambar memiliki nilai intensitas yang dekat dengan abu-abu tengah.

# Pencarian Ambang Batas Citra
