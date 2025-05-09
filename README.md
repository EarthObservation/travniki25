Za pripravo je potrebno slediti
https://docs.sentinel-hub.com/api/latest/api/batchv2/
za shranjevanje je potrebno slediti navodilom https://docs.sentinel-hub.com/api/latest/api/batchv2/#aws-bucket-access
grid je že definiran tako da se lahko potem požene
02_batch_v2_data_download.ipynb
and
03_prepare_for_batch2eopatch.ipynb

then use aws cli and use the previously defined profile
set AWS_PROFILE=batch

aws install
sudo yum install git
git clone https://github.com/EarthObservation/travniki25.git
sudo yum install python3-pip
pip install eo-grow

cd travniki25
ray start --head --num-cpus=2
eogrow configs/01_batch_to_eopatch.json

