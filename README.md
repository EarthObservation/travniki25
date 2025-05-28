Za pripravo je potrebno slediti
https://docs.sentinel-hub.com/api/latest/api/batchv2/
za shranjevanje je potrebno slediti navodilom https://docs.sentinel-hub.com/api/latest/api/batchv2/#aws-bucket-access
grid je že definiran tako da se lahko potem požene
02_batch_v2_data_download.ipynb in potem še 03_prepare_for_batch2eopatch.ipynb

# aws setup, ustvari instanco na AWS EC2, npr. m7i.8xlarge ali manjšo primerno prilagodi cpus=20 sicer manj
sudo yum install git
git clone https://github.com/EarthObservation/travniki25.git
sudo yum install python3-pip
pip install eo-grow

cd travniki25
ray start --head --num-cpus=2
eogrow configs/01_batch_to_eopatch.json

za prenos patchov se lahko uporabi S3 Browser in se sinhronizira mapo Tools>Folder Sync Tool
s3:batch-slo-24/eopatches/
v
\\KGKN-NAS\eo_data_2\travniki\eopatches\sentinel_l2a\bands

then go to jupyterhubeo, open a terminal
source /opt/tljh/user/bin/activate egrow
# če ga ni je osnova surs geos repozitorij
cd time-series-main
sudo -E conda create -y -p /opt/tljh/user/envs/eog-ts python=3.9
pip install -r requirements.txt
pip install -e .

source /opt/tljh/user/bin/activate eog
# skripte
git clone https://github.com/EarthObservation/travniki25.git

cd travniki25
eogrow configs/02_calc_features.json

cd git/time-series/
v configs/slovenia/signals/sentinel2_l2a/sentinel2_l2a_config.json
spremeni leto in poženi
eogrow configs/slovenia/signals/sentinel2_l2a/05_calc_features.json