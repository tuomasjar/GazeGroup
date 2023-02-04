Gaze Estimation Group Project:

Sources:
https://github.com/luxonis/depthai-experiments
https://docs.openvino.ai/2020.1/_models_intel_head_pose_estimation_adas_0001_description_head_pose_estimation_adas_0001.html

- https://caffe.berkeleyvision.org/
- Tait-Bryan angles (Hieman muokattu Euler kulmat) Yaw, pitch, roll
	- Pitch on nousu eli lentokoneessa nousu/laskukulma
	- Roll on kierto eli lentokoneen kaarron kiertokulma
	- Yaw on maansuuntainen kulma eli laivassa peräsimen tekemä kääntö

https://docs.openvino.ai/latest/omz_models_model_gaze_estimation_adas_0002.html

Creating pipeline...
Yhteys Kameraan
Creating Color Camera...
Creating Face Detection Neural Network...
Tunnistetaan naama
Creating Landmarks Detection Neural Network...
Tunnistetaan pääpiirteet naamasta
Creating Head Pose Neural Network...
Pään asento
Creating Gaze Estimation Neural Network...
Katseen suunta arviointi


Itse silmien peitto on simppeliä, kun saadaan valmiiksi laatikot silmien paikoista. Sitten vaan otetaan vasemman laatikon yläkulma ja oikean laatikon alakulma ja piirretään siitä laatikko täyteen mustaa.

Lisäsin startti argumentin -bb ja --blackbox, joka aktivoi sitten silmien peittämisen ja automaattisesti laittaa -cam argumentin, että aktivoi kameran automaattisesti 

(-cam on kameran kuvasta tehdään juttuja ja -vid on valmiista video kuvasta)

Jos haluaa normi katseen arvioinnin niin voi käynnistää ihan -cam
