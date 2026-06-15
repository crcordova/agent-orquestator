# ML Project

## Architecture Patterns
- Data pipeline: ingestion → cleaning → feature engineering → training → evaluation
- Model serving: REST API, gRPC, or batch inference
- Experiment tracking: MLflow, Weights & Biases, Neptune
- Feature store: for reusable feature computation
- Model registry: versioned model artifacts

## Key Decisions
- [ ] Framework (PyTorch, TensorFlow, JAX, scikit-learn)
- [ ] Experiment tracking tool
- [ ] Data format (Parquet, CSV, TFRecord, Arrow)
- [ ] Model serving (FastAPI, TorchServe, TF Serving, Triton)
- [ ] Training infrastructure (local, cloud GPU, managed platform)
- [ ] Feature store (Feast, custom)
- [ ] Deployment target (edge, cloud API, batch)

## Standard Slices
1. Project structure and environment setup
2. Data ingestion pipeline
3. Data exploration and cleaning
4. Feature engineering
5. Model definition and training loop
6. Evaluation metrics and validation
7. Experiment tracking integration
8. Model serialization and registry
9. Inference API or batch pipeline
10. Monitoring and drift detection
11. CI/CD for model retraining

## Testing Strategy
- Unit tests for data transformations
- Data validation tests (Great Expectations, Pandera)
- Model performance regression tests
- Inference latency tests
- Data pipeline integration tests

## Project Structure
```
project/
├── data/
│   ├── raw/
│   ├── processed/
│   └── features/
├── notebooks/
├── src/
│   ├── data/
│   ├── features/
│   ├── models/
│   ├── training/
│   └── inference/
├── configs/
├── experiments/
├── tests/
└── docker/
```

## Key Practices
- Reproducible experiments: seed everything, version data and code
- Config-driven training: YAML/JSON configs for hyperparameters
- Data versioning: DVC, LakeFS, or cloud storage versioning
- Model cards: document model purpose, limitations, and metrics
- A/B testing framework for model comparison
