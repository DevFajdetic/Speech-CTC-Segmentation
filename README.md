# Speech-CTC-Segmentation
Kloniranje skripti ili download skripti
```git clone https://github.com/DevFajdetic/Speech-CTC-Segmentation```

Python paketi potrebni
```python -m pip install git+https://github.com/NVIDIA/NeMo.git@$BRANCH#egg=nemo_toolkit[all]```
```! pip install pandas```
```! pip install plotly```
```! pip install ctc_segmentation==1.7.1```
```! pip install num2words```

Primjer pokretanja prepare_data.py
```! python prepare_data.py \
--in_text=./hr/text \
--output_dir=./processed/ \
--language='other' \
--additional_split_symbols=";|:|," \
--model="stt_hr_conformer_ctc_large" \
--audio_dir=./hr/audio```

Ctc_Segmentation.py
```! python run_ctc_segmentation.py \
--output_dir="hr_output" \
--data=./processed \
--model="stt_hr_conformer_ctc_large" \
--window_len=8000```

Cut_audio.py
```! python ./cut_audio.py \
--output_dir="hr_output" \
--alignment=./hr_output/segments/ \
--threshold=-2 \```

Transcribe.py
```! python transcribe_speech.py \
pretrained_name=$MODEL \
dataset_manifest=$OUTPUT_DIR/manifests/manifest.json \
output_filename=$OUTPUT_DIR/manifests/manifest_transcribed.json
--offset=0```
