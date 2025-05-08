first run
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

eogrow config/signals/sentinel2_l2a/02_batch_to_eopatch.json