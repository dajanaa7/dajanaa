# 🧪 TEST-RESULTS – Sistematsko testiranje kalkulatora

## 📦 Tip testiranja: Black Box (testiranje crne kutije)

---

## ✅ Test slučajevi i očekivani rezultati:

| Ulazni izraz      | Očekivani rezultat | Dobijen rezultat | Status     |
|-------------------|--------------------|------------------|------------|
| `2+2`             | `4`                | `4`              | ✅ Prolaz   |
| `2+3*4`           | `14`               | `14`             | ✅ Prolaz   |
| `10/2+5`          | `10`               | `10`             | ✅ Prolaz   |
| `10/0`            | Greška (deljenje nulom) | Izuzetak/Crash | ❌ Greška |
| `abc+1`           | Greška (nevažeći karakteri) | Izuzetak/Crash | ❌ Greška |
| `2++2`            | Greška (nevalidan izraz) | Izuzetak        | ❌ Greška |
| `3-5`             | `-2`               | `-2`             | ✅ Prolaz   |
| ` 4 +   5`        | `9`                | `9`              | ✅ Prolaz   |
| `5 * -2`          | `-10`              | `-10`            | ✅ Prolaz   |
| `(2+3)*4`         | `20`               | `20`             | ✅ Prolaz   |
| `2+(3*4)`         | `14`               | `14`             | ✅ Prolaz   |

---

## ❗ Detektovani problemi i propusti:

1. **Deljenje nulom (`10/0`) izaziva izuzetak (exception)**  
   → Potrebna je validacija i poruka korisniku umesto rušenja programa.

2. **Nevažeći karakteri (`abc+1`) izazivaju grešku**  
   → Nema validacije za unos – trebalo bi odbiti nebrojčane vrednosti.

3. **Sintaksne greške (`2++2`) nisu prepoznate na vreme**  
   → Program bi trebalo da pre verifikacije izraza proveri ispravnost sintakse.

4. **Nema poruka o greškama korisniku**  
   → Program se ruši bez korisnog objašnjenja (nema try-catch ili fallback poruka).

---

## 🧪 Jedinični test: JUnit test za metodu `calculate(String expression)`

```java
import org.junit.Test;
import static org.junit.Assert.*;

public class CalculatorTest {

    @Test
    public void testCalculateSimpleExpression() {
        String expression = "2+3*4";
        double expected = 14.0;

        double result = Calculator.calculate(expression);

        assertEquals(expected, result, 0.0001);
    }
}
```

---

## ✅ Preporuke:

- Uvesti **validaciju izraza** pre slanja na računanje.
- Dodati **try-catch** blokove za detekciju i obradu grešaka.
- Omogućiti jasne **poruke korisniku** o pogrešnim unosima.
- Implementirati dodatne jedinične testove za rubne slučajeve.
- Razmotriti korišćenje parsera (npr. `ScriptEngine` ili `exp4j`) za sigurnije i tačnije parsiranje izraza.
