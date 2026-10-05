# Feature Store Analysis

## 1. Elimination of Training-Serving Skew

Feast provides the same registered feature definitions for both offline
historical retrieval and online feature retrieval.

The `iris_engineered_features` feature view is defined once and can be
used during training through historical retrieval and during inference
through online retrieval.

This helps maintain consistency between training and serving.

## 2. Feature Reusability

The registered Iris features can be reused by different models without
re-implementing the feature engineering logic.

In Step 8, the same registered features were reused through the
`iris_feature_service` for another model workflow.

This demonstrates that features can be shared across different
machine learning models.

## 3. Centralized Governance

The `features.py` file acts as the central definition of the Iris
features.

It contains the entity, data source, feature views, schemas, TTL, and
feature service definitions.

This provides a single source of truth for models consuming these
features and makes feature definitions easier to maintain.