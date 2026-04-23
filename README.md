# Zero to Hero - learning LLM foundations

Learn with Karpathy Youtube channel

## env setup
```
# WSL install miniconda
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

```
# Create python env
conda create -n karpathy-gpt python=3.10 -y
conda activate karpathy-gpt
```

## training in vast.ai
```
git clone https://github.com/benyue1978/zero-to-hero.git
cd zero-to-hero
pip install -r requirements.txt

# test the environment
cd build-nanogpt
torchrun --standalone --nproc_per_node=2 train_gpt2.py

# download and process the training data
python fineweb.py

# download and run hellaswag
python hellaswag.py

# run real training on 8*A100 GPU
torchrun --standalone --nproc_per_node=8 train_gpt2.py
```