# Regularization: Ridge & Lasso — Diabetes Dataset

نوتبوك واحد منفّذ بالكامل يغطّي الأجزاء 1-5: فهم Regularization، Ridge، Lasso،
منحنى تأثير alpha، والمقارنة النهائية الشاملة. كل النتائج والرسومات ظاهرة داخل النوتبوك.

## الملفات
- `regularization_ridge_lasso.ipynb` — النوتبوك الكامل (منفّذ).
- `regularization_ridge_lasso.html` — نسخة HTML للعرض المباشر.

## أبرز النتائج (متحقّق منها على نفس بيانات الاختبار)
| النموذج | MAE | MSE | RMSE | R² |
|---------|-----|-----|------|-----|
| Linear (كل المتغيرات) | 42.79 | 2900.19 | 53.85 | 0.453 |
| Polynomial (bmi، درجة 2) | 52.38 | 4085.03 | 63.91 | 0.229 |
| **Ridge (alpha=0.1)** | 43.00 | **2856.49** | **53.45** | **0.461** |
| Lasso (alpha=1.0) | 49.73 | 3403.58 | 58.34 | 0.358 |

## أهم الاستنتاجات
- **معاملات Ridge أصغر** من Linear (أثر عقوبة L2)، و**Lasso يصفّر** معاملات
  (7 أصفار عند alpha=1) = اختيار ميزات تلقائي.
- **منحنى alpha:** أفضل قيمة ≈ **0.1**؛ وعند alpha كبير جدًا (100–1000) ينهار
  الأداء (Underfitting بسبب العقوبة المفرطة).
- **الأفضل = Ridge (alpha=0.1):** أدنى خطأ وأعلى R² (0.461)، لأنه صغّر المعاملات
  بلطف فحسّن التعميم دون إلغاء متغيرات مفيدة (عكس Lasso) ودون إهمال متغيرات (عكس
  Polynomial على bmi وحده).

## التشغيل
```bash
pip install scikit-learn pandas numpy matplotlib jupyter
jupyter notebook regularization_ridge_lasso.ipynb
```
