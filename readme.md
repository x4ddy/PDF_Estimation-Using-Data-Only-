# Learning Probability Density Functions using GANs and Non-Linear Transformation

This project demonstrates learning an unknown probability density function directly from data using a roll-number-based non-linear transformation and a Generative Adversarial Network (GAN), without assuming any parametric form.

## Dataset
- India Air Quality Dataset  
- Feature used: NO₂ (Nitrogen Dioxide) concentration  
- Source: Kaggle  
  https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data  

Only the NO₂ column is used. Missing values are removed prior to analysis.

## Objective
- Apply a personalized non-linear transformation to NO₂ data  
- Learn the resulting unknown distribution using data only  
- Estimate the probability density function from GAN-generated samples  
- Visualize and compare learned PDF with real data distribution  

## Methodology
- Load dataset with appropriate encoding  
- Extract NO₂ values and remove missing entries  
- Normalize data for stable GAN training  
- Apply roll-number-based non-linear transformation  
  z = x + a_r sin(b_r x)  
- Compute transformation parameters using roll number  
- Train a GAN consisting of a generator and discriminator  
- Generate synthetic samples from the trained generator  
- Apply Kernel Density Estimation (KDE) on generated samples  

## Results
- Histogram of transformed real data  
- Estimated PDF learned from GAN-generated samples  
- Strong overlap between real and generated distributions  

## Observations
- The GAN captures the main modes of the transformed data  
- Generator and discriminator losses oscillate as expected but remain stable  
- The KDE-based PDF closely follows the real data histogram  

## Conclusion
The experiment demonstrates that GANs can successfully learn complex, non-linearly transformed probability distributions using data alone. The roll-number-based transformation introduces personalization while the GAN avoids any explicit distributional assumptions.
