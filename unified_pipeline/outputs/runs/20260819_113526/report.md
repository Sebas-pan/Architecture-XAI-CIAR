# Instancia explicativa

## Muestra (index 1226)
- True: 214000.0 | Pred: 204239.22
- Top features LIME:
    - BsmtCond_Po <= 0.00 -> -40906.9489
    - HeatingQC_Po <= 0.00 -> -40058.3660
    - GrLivArea > 0.50 -> 37964.5686
    - MiscFeature_TenC <= 0.00 -> 30605.5025
    - Utilities_NoSeWa <= 0.00 -> 26682.5894
    - GarageQual_Po <= 0.00 -> 26436.8059
    - Exterior2nd_AsphShn <= 0.00 -> 20435.0607
    - SaleType_ConLw <= 0.00 -> 17206.8827
    - SaleType_ConLI <= 0.00 -> 14454.5958
    - Condition2_RRAe <= 0.00 -> 10818.0207
- Top SHAP:
    - GrLivArea -> 22304.5472
    - OverallQual -> -19440.0835
    - BsmtFinSF1 -> -5622.5012
    - GarageFinish_Unf -> 4308.1204
    - LotArea -> 3770.1511
    - GarageCars -> 3623.0264
    - YearBuilt -> 3198.8695
    - 2ndFlrSF -> 3194.1046

## Muestra (index 44)
- True: 141000.0 | Pred: 137670.875
- Top features LIME:
    - OverallQual <= -0.82 -> -37344.2355
    - Exterior1st_AsphShn <= 0.00 -> 30849.8684
    - Utilities_NoSeWa <= 0.00 -> 27056.3863
    - SaleType_ConLI <= 0.00 -> 26348.6339
    - RoofMatl_WdShngl <= 0.00 -> -22370.8494
    - SaleType_Oth <= 0.00 -> -22329.4227
    - Condition2_RRAn <= 0.00 -> 21900.2326
    - -0.73 < GrLivArea <= -0.10 -> -20792.7128
    - Condition2_Artery <= 0.00 -> -20188.1401
    - Condition2_RRAe <= 0.00 -> 16986.7634
- Top SHAP:
    - OverallQual -> -27398.3005
    - GrLivArea -> -11887.6141
    - TotalBsmtSF -> 5611.1027
    - GarageCars -> -2729.0972
    - GarageFinish_Unf -> 2305.5902
    - BsmtFinSF1 -> -2280.1959
    - GarageArea -> -1986.9276
    - YearRemodAdd -> -1780.4998

## Muestra (index 179)
- True: 100000.0 | Pred: 122216.07
- Top features LIME:
    - OverallQual <= -0.82 -> -37139.0179
    - GrLivArea <= -0.73 -> -29503.2936
    - Neighborhood_Blueste <= 0.00 -> -25778.2100
    - MiscFeature_Gar2 <= 0.00 -> 24901.8010
    - SaleType_ConLD <= 0.00 -> -16050.5584
    - ExterCond_Po <= 0.00 -> 14628.5356
    - Exterior2nd_Other <= 0.00 -> 13914.4227
    - Condition2_RRAe <= 0.00 -> -11322.3015
    - MiscFeature_TenC <= 0.00 -> 10779.7019
    - RoofMatl_ClyTile <= 0.00 -> 5691.9061
- Top SHAP:
    - OverallQual -> -28448.8215
    - GrLivArea -> -14113.9907
    - YearBuilt -> -4393.4368
    - BsmtFinSF1 -> -3828.1520
    - YearRemodAdd -> 2548.5773
    - GarageFinish_Unf -> -1732.1455
    - 1stFlrSF -> -1501.1966
    - Fireplaces -> -1255.0649
