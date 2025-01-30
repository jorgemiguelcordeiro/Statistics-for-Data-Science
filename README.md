# **Gasoline Demand Analysis in Brazil**  

## **Project Overview**  
This study analyzes **gasoline demand in Brazil** using **panel data** from 27 Brazilian states over **16 years**. The dataset includes:  
- **Gasoline sales per capita**  
- **Fuel and ethanol prices**  
- **Conventional and electric vehicle motorization rates**  
- **GDP per capita**  

All variables were transformed into **natural logarithms** for consistency and ease of interpretation.

---

## **Key Research Questions**  
🔹 **How do fuel prices influence gasoline demand in Brazil?**  
🔹 **What role do ethanol prices play in shaping traditional fuel consumption?**  
🔹 **How do income levels affect the elasticity of gasoline demand across different regions?**  

---

## **Methodology**  

### **1️⃣ Multicollinearity Check**  
- **Variance Inflation Factor (VIF) test**: No variables exceeded the threshold of **5**, confirming **no multicollinearity** in our model.  

### **2️⃣ Panel Data Models Considered**  
- **Pooled OLS Model**  
- **Fixed Effects Model**  
- **Random Effects Model**  

### **3️⃣ Heteroskedasticity Assessment: Breusch-Pagan Test**  
📌 The **Breusch-Pagan test** indicated **heteroscedasticity** in all models (**p-value = 0**).  
✅ To correct for this, we **used robust standard errors** to ensure reliable inference and avoid biased results.  

### **4️⃣ Model Selection: Hausman Test**  
📌 The **Hausman test** rejected the null hypothesis (**p-value = 0.0059**), confirming that the **Fixed Effects Model** is the best fit, as it accounts for **unobserved heterogeneity** across states.  

---

## **Final Model: Robust Fixed Effects Analysis**  

### **Regression Results**
| Variable | Estimate | Std. Error | p-Value |
|----------|---------|------------|----------|
| **Fuel Prices (ln_Pg)** | **-1.3856** | 0.1172 | **< 0.001** |
| **Ethanol Prices (ln_Pe)** | **0.9992** | 0.1030 | **< 0.001** |
| **Conventional Motorization (ln_Mi_c)** | **0.7451** | 0.0732 | **< 0.001** |
| **Electric Motorization (ln_Mi_e)** | **-0.0354** | 0.0078 | **< 0.001** |
| **GDP per Capita (ln_gdp_pc)** | **0.1472** | 0.1064 | **0.167** |

📊 **Adjusted R² = 0.9056** → High explanatory power!  

### **Key Takeaways**  
🔹 **Fuel Prices**: 🚗📉 **Strong negative effect (-1.3856)** → Higher prices reduce gasoline demand.  
🔹 **Ethanol Prices**: 🌱📈 **Positive effect (0.9992)** → Higher ethanol prices increase gasoline demand (substitution effect).  
🔹 **Conventional Motorization**: 🚘📈 **Significant positive impact (0.7451)** → More gasoline-powered vehicles = higher demand.  
🔹 **Electric Vehicles**: ⚡📉 **Negative but minor effect (-0.0354)** → Early-stage adoption of EVs has a small impact on demand.  
🔹 **GDP per Capita**: 💰 **Not significant (0.167)** → Income levels have minimal effect after controlling for other variables.  

---

## **What Could Have Been Done Differently?**  

### ✅ **1️⃣ RESET Test for Functional Form Specification**  
- **Why?** To check whether the model correctly captures the **non-linearity** in gasoline demand.  
- **What it would do?** Detect potential **misspecification errors** in our regression model.  

### ✅ **2️⃣ Endogeneity Tests**  
- **Why?** Fuel prices may be **endogenous** (i.e., determined simultaneously with gasoline demand).  
- **Solution?** Use **Instrumental Variables (IV) Regression** to control for potential biases.  

### ✅ **3️⃣ Time Series Effects: Unit Root & Cointegration Tests**  
- **Why?** Panel data models assume **stationary relationships**.  
- **Tests we could have done:**  
  - **Levin-Lin-Chu (LLC) test** for unit roots.  
  - **Pedroni Cointegration Test** to check long-run equilibrium relationships.  

### ✅ **4️⃣ Dynamic Panel Models**  
- **Why?** Gasoline demand is likely influenced by past consumption levels.  
- **Solution?** Generalized Method of Moments (**GMM Estimation**) to account for dynamic effects.  

---

## **Conclusion & Future Work**  

📌 **Key Insights:**  
1️⃣ **Fuel pricing policies are critical** for demand management. 🚗⬇️  
2️⃣ **Ethanol & gasoline have strong substitution effects**. 🌱↔️⛽  
3️⃣ **Electric vehicle adoption is still too small** to significantly affect demand. ⚡🚘  

📌 **Future Work:**  
- Investigate the long-term impact of **electric vehicle growth** on fuel consumption.  
- Use **micro-level household data** to capture behavioral differences in gasoline demand.  
- Explore **regional variations** in fuel substitution effects.  

---

## **References**  

📖 **Data Sources:**  
🔹 [ANP: Fuel Prices & Sales](https://www.gov.br/anp/en/access-information/what-is-anp/what-is-anp)  
🔹 [IBGE: State Population & GDP](https://www.ibge.gov.br/en/home-eng.html?lang=en-GB)  
🔹 [Anfavea: State EV Fleet](https://anfavea.com.br/en/site/anuarios/)  
🔹 [Mendeley: Brazilian Panel Data](https://data.mendeley.com/datasets/hzpwbp7j22/1)  

---

📌 **Authors:**  
👤 **Beatriz Monteiro** - 20240591  
👤 **Jorge Cordeiro** - 20240594  
👤 **Pedro Santos** - 20240295  
👤 **Rodrigo Miranda** - 20240490  

🚀 **This project applies advanced econometric techniques to analyze gasoline demand in Brazil!** 🚀  


