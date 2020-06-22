## Upute za pokretanje učenja modela

Prvo je potrebno skinuti skup podataka za učenje.

```bash
https://transfer.sh/13wPrN/dataset5.zip
```

Zatim je potrebno otpakirati arhivu i podijeliti skup rečenica na skup za učenje i skup za evaluiranje.
```bash
unzip dataset5.zip
shuf hrt5_sve/domitran_utf8.txt > hrt5_sve/domitran_utf8_shuf.txt 
head -n 1700 hrt5_sve/domitran_utf8_shuf.txt > hrt5_sve/domitran_utf8_train.txt
tail -n 386 hrt5_sve/domitran_utf8_shuf.txt > hrt5_sve/domitran_utf8_val.txt
```

Skidanje modificiranom sustava Mozilla TTS
```bash
git clone https://github.com/lonelos/tts
```

```bash
cd tts
```


```bash
apt install espeak -y
pip3 install soundfile
python3 setup.py install
```

Pokretanje učenja modela
```bash
python3 train.py --config_path config-hrt5.json | tee training.log
```
