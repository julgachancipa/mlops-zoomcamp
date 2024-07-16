## Data
[NYC taxi dataset](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page),

```bash
mlflow ui --backend-store-uri sqlite:///mlflow.db
```

## What’s experiment tracking?

Experiment tracking is the process of keeping track of all the relevant information
from an ML experiment, which includes:
- Source code
- Environment
- Data
- Model
- Hyperparameters
- Metrics
___
## Why is experiment tracking so important?

In general, because of these 3 main reasons:
- Reproducibility
- Organization
- Optimization
___
## MLflow

Definition: “An open source platform for the machine learning lifecycle” *
In practice, it’s just a Python package that can be installed with pip, and it contains
four main modules:
- Tracking
- Models
- Model Registry
- Projects
---
### Tracking experiments with MLflow

The MLflow Tracking module allows you to organize your experiments into runs, and to keep track of:
- Parameters
- Metrics
- Metadata
- Artifacts
- Models

Along with this information, MLflow automatically logs extra information about the run:
- Source code
- Version of the code (git commit)
- Start and end time

![MLOps cycle and machine learning experiment tracking](https://i0.wp.com/neptune.ai/wp-content/uploads/2023/10/Experiment-tracking.png?resize=1020%2C534&ssl=1)

---
### Model management in MLflow

The Model Registry component is a centralized model store, set of APIs, and a UI,
to collaboratively manage the full lifecycle of an MLflow Model.
It provides:
- Model lineage,
- Model versioning,
- Stage transitions, and
- Annotations

---
### Remote tracking server

The tracking server can be easily
deployed to the cloud
Some benefits:
- Share experiments with other data scientists
- Collaborate with others to build and deploy models
- Give more visibility of the data science efforts

---

### Issues with running a remote (shared) MLflow server

- Security
    - Restrict access to the server (e.g. access through VPN)
- Scalability
    - Check Deploy MLflow on AWS Fargate
    - Check MLflow at Company Scale by Jean-Denis Lesage
- Isolation
    - Define standard for naming experiments, models and a set of default tags
    - Restrict access to artifacts (e.g. use s3 buckets living in different AWS accounts)

---

### MLflow limitations (and when not to use it)

- Authentication & Users: The open source version of MLflow doesn’t provide any sort of authentication
- Data versioning: to ensure full reproducibility we need to version the data used to train the model. MLflow doesn’t provide a built-in solution for that but there are a few ways to deal with this limitation
- Model/Data Monitoring & Alerting: this is outside of the scope of MLflow and currently there are more suitable tools for doing this

---

### MLflow alternatives

There are some paid alternatives to MLflow:
- Neptune
- Comet
- Weights & Biases
- and many more