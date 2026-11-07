# Literature Review

## Research Topic

Predicting Body Mass in Palmer Penguins Using Ridge Regression and Random Forest

## Research Question

Can Random Forest improve body mass prediction compared with Ridge Regression for adult Palmer Archipelago penguins?

## Source 1: Gorman et al. (2014)

**Title:** Ecological Sexual Dimorphism and Environmental Variability within a Community of Antarctic Penguins (Genus Pygoscelis)

**Authors:** Kristen B. Gorman, Tony D. Williams, and William R. Fraser

**Year:** 2014

**Link:** https://doi.org/10.1371/journal.pone.0090081

**Summary:**

Gorman et al. (2014) investigated differences in body size and foraging ecology among three Antarctic penguin species. Their findings showed differences in sexual size dimorphism among species, supporting the importance of considering species and sex when studying penguin physical characteristics. This research provides biological context for selecting predictors in the present study.

## Source 2: Horst et al. (2020)

**Title:** palmerpenguins: Palmer Archipelago (Antarctica) Penguin Data

**Authors:** Allison Marie Horst, Alison Presmanes Hill, and Kristen B. Gorman

**Year:** 2020

**Link:** https://doi.org/10.5281/zenodo.3960218

**Summary:**

Horst et al. (2020) published the palmerpenguins dataset, which contains measurements and characteristics of three penguin species from the Palmer Archipelago. The dataset provides information such as bill length, bill depth, flipper length, body mass, species, and sex. These variables make it suitable for investigating relationships between physical measurements and body mass using regression models.

## Source 3: Hoerl and Kennard (1970)

**Title:** Ridge Regression: Biased Estimation for Nonorthogonal Problems

**Authors:** Arthur E. Hoerl and Robert W. Kennard

**Year:** 1970

**Link:** https://doi.org/10.1080/00401706.1970.10488634

**Summary:**

Hoerl and Kennard (1970) introduced Ridge Regression as a method for addressing difficulties caused by correlated predictor variables in linear regression. The method introduces a penalty that can improve the stability of estimated regression coefficients. Ridge Regression is therefore a suitable model for examining relationships between penguin body mass and potentially correlated physical measurements.

## Source 4: Breiman (2001)

**Title:** Random Forests

**Author:** Leo Breiman

**Year:** 2001

**Link:** https://doi.org/10.1023/A:1010933404324

**Summary:**

Breiman (2001) introduced Random Forests, an ensemble learning method that combines predictions from multiple decision trees. The approach can model complex relationships between predictor variables while reducing some of the instability associated with individual trees. This makes Random Forest a relevant alternative to Ridge Regression when predicting penguin body mass.

## Research Gap

Previous research provides biological information about penguin characteristics and establishes statistical and machine learning methods for prediction. However, these sources do not directly establish which of Ridge Regression or Random Forest performs better for predicting body mass on the selected Palmer Penguins dataset under the same experimental conditions.

This project addresses that specific comparison by applying both regression methods to the same cleaned dataset and evaluating their performance using five-fold cross-validation and an independent holdout test set. Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) are used to compare prediction errors.

## References

Breiman, L. (2001). Random forests. *Machine Learning, 45*, 5–32. https://doi.org/10.1023/A:1010933404324

Gorman, K. B., Williams, T. D., & Fraser, W. R. (2014). Ecological sexual dimorphism and environmental variability within a community of Antarctic penguins (Genus Pygoscelis). *PLOS ONE, 9*(3), e90081. https://doi.org/10.1371/journal.pone.0090081

Hoerl, A. E., & Kennard, R. W. (1970). Ridge regression: Biased estimation for nonorthogonal problems. *Technometrics, 12*(1), 55–67. https://doi.org/10.1080/00401706.1970.10488634

Horst, A. M., Hill, A. P., & Gorman, K. B. (2020). *palmerpenguins: Palmer Archipelago (Antarctica) penguin data* (Version 0.1.0) [Dataset and R package]. https://doi.org/10.5281/zenodo.3960218
