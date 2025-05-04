# 📊 Staticka analiza projekta - Calculator Java

## 🔗 GitHub repozitorijum originalnog projekta:
[https://github.com/vladimir-dresevic/calculator-java](https://github.com/vladimir-dresevic/calculator-java)

---

## 📈 Analiza i metrika

### ✅ LOC (Lines of Code):
- `Calculator.java` – 55 linija  
- `Start.java` – 20 linija  
**Ukupno: 75 linija**

---

## 🔍 Staticka analiza i zapažanja

### 📁 1. Calculator.java
- Sadrži osnovne aritmetičke metode (sabiranje, oduzimanje, množenje, deljenje)
- Svi metodi su statički – jednostavni i pregledni

**🔴 Problemi:**
- Nema provere za deljenje nulom (može izazvati grešku u izvršavanju)
- Manjak komentara i JavaDoc dokumentacije
- Nema validacije ulaza

**✅ Preporuke:**
- Dodati proveru za deljenje nulom
- Uvesti obradu izuzetaka (try-catch)
- Dodati komentare za svaki metod

---

### 📁 2. Start.java
- Sadrži `main` metodu sa test primerima
- Testovi su hardkodirani – bez korisničkog unosa
- Ne postoji rukovanje greškama

**✅ Preporuke:**
- Uključiti unos sa tastature (Scanner)
- Dodati try-catch blokove za bezbedno izvršavanje
- Razmotriti pisanje testova pomoću JUnit-a

---

## 📌 Zaključak
Kod je funkcionalan, ali sadrži osnovne nedostatke kada je reč o validaciji i obradi grešaka.  
Uz manje izmene, može se znatno unaprediti čitljivost i robusnost aplikacije.
