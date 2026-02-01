# Deploy and Run 

# 1) Create virtual environment with Python 3.11
# (adjust the python path if needed)
uv venv --python ~/.pyenv/versions/3.11.11/bin/python .venv

# 2) Install dependencies from pyproject.toml and create uv.lock
uv sync

# 3) Activate the virtual environment (for current shell)
source .venv/bin/activate

# 4) Verify that the correct Python is used
python -V
which python

# 5) Register Jupyter kernel from this environment
python -m ipykernel install \
  --user \
  --name ner-characters-graph \
  --display-name "Python (ner-characters-graph)"

# 6) Smoke test imports
python -c "import natasha, razdel, navec, slovnet; print('nlp ok')"
python -c "import pandas, sklearn, rapidfuzz; print('data ok')"