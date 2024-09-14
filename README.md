# TermDiffuSum: A Term-guided Diffusion Model for Extractive Summarization of Legal Documents


[Datasets Link]().

## Train & Test

### Train

```shell
# train
nohup python run_train_sum.py --diff_steps 500 --model_arch transformer_sum --lr 1e-5 --seed 101 --noise_schedule legal_noise --in_channel 128 --modality roc --submit no --padding_mode pad --app "--predict_xstart True --training_mode e2e --roc_train legal " --notes legal --bsz 32 --epochs 10 --save_name _1 >train.log 2>&1 &
```

### Test

```python
python batch_decode_sum.py [checkpoint_path] -1.0 ema
