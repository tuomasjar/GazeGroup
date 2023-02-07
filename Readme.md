Gaze Estimation Group Project:

Sources:
https://github.com/luxonis/depthai-experiments
https://docs.openvino.ai/2020.1/_models_intel_head_pose_estimation_adas_0001_description_head_pose_estimation_adas_0001.html

https://www.aptiv.com/en/insights/article/what-is-a-driver-monitoring-system
Tuosta jotain turvallisuusjuttuja

- https://caffe.berkeleyvision.org/
- Tait-Bryan angles (Hieman muokattu Euler kulmat) Yaw, pitch, roll
	- Pitch on nousu eli lentokoneessa nousu/laskukulma
	- Roll on kierto eli lentokoneen kaarron kiertokulma (https://en.wikipedia.org/wiki/Euler_angles)
	- Yaw on maansuuntainen kulma eli laivassa peräsimen tekemä kääntö

https://docs.openvino.ai/latest/omz_models_model_gaze_estimation_adas_0002.html

- Ottaa kolme tietoa:
	- Vasemman silmän kuvan
	- Oikean silmän kuvan
	- Pään asennon Euler kulmat
- Tuottaa 3D-vektorin, joka kuvaa henkilön katseen suunnan, jossa z-akseli on silmien keskeltä kohti kameraa. 


https://pypi.org/project/blobconverter/
land_nn.setBlobPath(blobconverter.from_zoo(name="landmarks-regression-retail-0009", shaves=4))
shaves = Specifies number of SHAVE cores that converted model will use

Creating pipeline...
Yhteys Kameraan
Creating Color Camera...

Creating Face Detection Neural Network...
Tunnistetaan naama
face-detection-retail-0004

Creating Landmarks Detection Neural Network...
Tunnistetaan pääpiirteet naamasta
landmarks-regression-retail-0009


Creating Head Pose Neural Network...
Pään asento
head-pose-estimation-adas-0001

Creating Gaze Estimation Neural Network...
Katseen suunta arviointi
gaze-estimation-adas-0002

Itse silmien peitto on simppeliä, kun saadaan valmiiksi laatikot silmien paikoista. Sitten vaan otetaan vasemman laatikon yläkulma ja oikean laatikon alakulma ja piirretään siitä laatikko täyteen mustaa.

Lisäsin startti argumentin -bb ja --blackbox, joka aktivoi sitten silmien peittämisen ja automaattisesti laittaa -cam argumentin, että aktivoi kameran automaattisesti 

(-cam on kameran kuvasta tehdään juttuja ja -vid on valmiista video kuvasta)

Jos haluaa normi katseen arvioinnin niin voi käynnistää ihan -cam


Ehkäpä tämä olisi parempi esimerkki katseen suunnan seuraamisesta:

Googly eyes:
- Starttaa 
> python3 main.py -gg

tai

> python3 main.py --googlyeyes

- Tunnistaa katseen suunnan ja piirtää valkoisen silmän silmän päälle ja siitä sitten musta pupilli katseen suunnan mukaan
 

