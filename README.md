# President Armando - Parkinson's Disease Prediction Neural Network

## Overview

**President Armando** (P.A.) is an artificial neural network designed for Parkinson's disease prediction based on voice recording analysis. This project demonstrates the application of machine learning techniques to medical diagnosis, utilizing vocal biomarkers to distinguish between healthy individuals and those with Parkinson's disease.

## Team

This project was developed by:
- Armando Di Stasio
- Giulia Motta  
- Federico Di Bari
- Gaetano Daniele Calcina

## Dataset

The model is trained on voice recordings from 31 patients, comprising 195 total entries with the following distribution:
- **Training set**: 155 data points (80%)
- **Test set**: 40 data points (20%)

### Features

The dataset includes 22 vocal features extracted from voice recordings:

#### Fundamental Frequency Measures
- `MDVP:Fo(Hz)`: Average vocal fundamental frequency
- `MDVP:Fhi(Hz)`: Maximum vocal fundamental frequency  
- `MDVP:Flo(Hz)`: Minimum vocal fundamental frequency

#### Jitter Measures (Frequency Variation)
- `MDVP:Jitter(%)`, `MDVP:Jitter(Abs)`, `MDVP:RAP`, `MDVP:PPQ`, `Jitter:DDP`

#### Shimmer Measures (Amplitude Variation)  
- `MDVP:Shimmer`, `MDVP:Shimmer(dB)`, `Shimmer:APQ3`, `Shimmer:APQ5`, `MDVP:APQ`, `Shimmer:DDA`

#### Noise-to-Tonal Ratios
- `NHR`: Noise-to-harmonics ratio
- `HNR`: Harmonics-to-noise ratio

#### Nonlinear Dynamical Measures
- `RPDE`, `D2`: Nonlinear dynamical complexity measures
- `DFA`: Signal fractal scaling exponent
- `Spread1`, `Spread2`, `PPE`: Nonlinear measures of fundamental frequency variation

#### Target Variable
- `Status`: Health status (1 = Parkinson's disease, 0 = Healthy)

## Neural Network Architecture

After feature selection and data preprocessing, President Armando utilizes a streamlined architecture:

```
Input Layer: 9 neurons (selected relevant features)
    ↓
Hidden Layer 1: 5 neurons  
    ↓
Hidden Layer 2: 3 neurons
    ↓
Output Layer: 1 neuron (Binary classification: Parkinson's Y/N)
```

## Data Preprocessing

The preprocessing pipeline includes:

1. **Feature Selection**: 
   - Removal of features with relevance < 10%
   - Elimination of redundant features using correlation analysis
   
2. **Data Normalization**: Standardization of input features

3. **Correlation Analysis**: Multiple correlation matrices to identify:
   - Feature relationships with target variable
   - Inter-feature correlations
   - Redundant features (correlation threshold: 0.95)

## Visualization and Analysis

The project includes comprehensive data visualization:

- **Graph A**: Complete dataset correlation heatmap
- **Graph B**: Feature correlation with target variable (Status)  
- **Graph C**: Inter-feature correlation matrix (cleaned dataset)
- **Graph D**: Filtered correlation matrix (threshold < 0.95)
- **Graph E**: Training accuracy over epochs
- **Graph F**: Training loss over epochs  
- **Graph G**: Confusion matrix for model performance evaluation

## Performance Evaluation

Model performance is assessed using:
- **Confusion Matrix**: Displaying true positives, true negatives, false positives, and false negatives
- **Accuracy Metrics**: Training accuracy progression over epochs
- **Loss Function**: Error minimization tracking during training

## User Interface

The project features a user-friendly interface that accepts 9 vocal feature inputs for real-time Parkinson's disease prediction.

## Limitations and Future Work

### Current Limitations
- **Dataset Size**: Limited to 195 entries from 31 patients
- **Generalizability**: Results may not be representative of broader populations
- **Feature Extraction**: Requires specialized equipment for vocal feature analysis

### Future Improvements
- Expansion of dataset with more diverse patient populations
- Integration of additional vocal biomarkers
- Development of automated feature extraction pipeline
- Cross-validation with clinical diagnosis standards

## Academic Context

This project represents an intersection of artificial intelligence and medical diagnosis, exploring the potential of neural networks in healthcare applications. It demonstrates practical implementation of machine learning principles while acknowledging the epistemological challenges inherent in medical AI systems.

## Data Source

Dataset adapted from:
Max A. Little, Patrick E. McSharry, Eric J. Hunter, Lorraine O. Ramig (2008), 'Suitability of dysphonia measurements for telemonitoring of Parkinson's disease', IEEE Transactions on Biomedical Engineering.

---

*This project is part of graduate research in AI applications for medical diagnosis and represents ongoing work in the field of neural network-based healthcare solutions.*
