# sleep-stage-classification

Sleep staging (wake / REM / light / deep) from wristband signals only (PPG, accelerometer, skin temperature),
using the [DREAMT](https://physionet.org/content/dreamt/2.1.0/) dataset. Most of the time went into feature
extraction (HR/HRV, movement, temperature, some circadian and rolling-window features). After that we compared a
bunch of models with subject-wise CV and smoothed the predictions to get a hypnogram.

CatBoost was best (kappa ~0.29 in CV, LightGBM almost the same). On 4 held-out subjects: 58% accuracy,
kappa 0.27. Deep sleep is really hard to get from the wrist.

Data isn't included, you need DREAMT access on PhysioNet. Then set `DREAMT_DATA_DIR` to the `data_64Hz` folder
and `pip install -r requirements.txt`.
