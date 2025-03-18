* Veri seti SR için oluşturulmadığı için ön işleme tabi tutuldu.
* Görüntüler 4x - bicubic interpolasyon ile downsampling uygulandı, LR görüntü haline getirildi.
* Oluşturulan LR görüntüleri 4x - bicubic interpolasyon ile upscale uygulandı, LR_upscale görüntüler oluşturuldu.
* Model eğitiminde bu LR_upscale görüntüler kullanılacak. Model, bu görüntüleri "iyileştirerek" orijinal HR görüntüyü oluşturmayı hedefler. 
* SRCNN, bicubic interpolasyon ile büyütülmüş (bulanık) görüntüyü alır ve HR görüntüyü olabildiğince en iyi şekilde üretmeyi öğrenir.
* HR -> downsampling -> LR -> upscale -> LR_upscale (bulanık HR)

* Veri seti yapısı:
* SR_Dataset:	
	* HR:
		* train (1654 görüntü)
		* test (414 görüntü)
	* LR:
		* train (1654 görüntü)
		* test (414 görüntü)
	* LR_upscale:
		* train (1654 görüntü)
		* test (414 görüntü)

* HR görüntü boyutu: [540x1024]
* LR görüntü boyutu: [135x256]
* LR_upscale görüntü boyutu: [540x1024]
