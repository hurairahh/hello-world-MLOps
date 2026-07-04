# Hello-World MLOps 

A minimal, reproducible MLOps workflow to train and serve a model.

## Setup
```bash
pip install -r requirements.txt
```

## Usage

1. **Train the Model**:
   ```bash
   python train.py
   ```
   Generates `artifacts/model.pkl` and `artifacts/metrics.json`.

2. **Command Line Prediction**:
   ```bash
   python run_model.py --input "[5.1, 3.5, 1.4, 0.2]"
   ```

3. **Start the API Server**:
   ```bash
   python app.py
   ```
   Test with:
   ```bash
   curl -X POST "http://127.0.0.1:5001/predict" -H "Content-Type: application/json" -d '{"features":[5.1, 3.5, 1.4, 0.2]}'
   ```

## Docker
Build and run the API service inside a container:
```bash
docker build -t hello-mlops .
docker run -p 5001:5001 hello-mlops
```

