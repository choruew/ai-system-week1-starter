# Week 1 Evidence

學號：7115029019
姓名：彭景榆

## 1. Dataset 在哪裡？

`data/customer_intent_demo.csv`

本次實驗使用客服問題意圖分類資料集，共有 100 筆資料，
包含 4 種意圖類別，每個類別各 25 筆。

---

## 2. Baseline 在哪裡？

`src/rule_baseline.py`

本次使用 Rule-based Baseline，
透過預先設定的文字規則判斷客服訊息所屬的問題類別。

---

## 3. 本次 Accuracy

Accuracy = 0.950

代表 100 筆資料中，有 95 筆被 Baseline 正確分類，
另外有 5 筆分類錯誤。

---

## 4. Failure Case

Input：

`退貨物流已收走但沒有更新`

Ground Truth：

`refund_return`

Baseline Prediction：

`order_delivery`

---

## 5. 為什麼 Baseline 會錯？

因為這筆訊息同時出現「退貨」和「物流」兩種關鍵資訊，而目前的規則可能優先依照「物流」進行判斷，因此將原本屬於退貨問題的訊息錯誤分類為 order_delivery。

---

## 6. 這是否代表現在一定要使用更複雜的 AI？為什麼？

不一定，因為目前 Baseline 已能正確分類 95% 的資料，可以先分析剩下的錯誤案例，嘗試調整關鍵字、規則優先順序或加入多個關鍵字的判斷，再評估是否有必要使用更複雜的 AI 模型。