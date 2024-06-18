# Component based architecture
Architektura komponentów to podejście do projektowania oprogramowania, w którym system jest podzielony na niezależne, wymienne moduły zwane komponentami. Każdy komponent odpowiada za określoną funkcjonalność i komunikuje się z innymi komponentami za pomocą dobrze zdefiniowanych interfejsów.

## Zalety architektury komponentów:

- **Modularność:** System jest łatwiejszy w zarządzaniu, ponieważ zmiany w jednym komponencie nie wpływają na inne.
- **Reużywalność:** Komponenty mogą być używane w różnych projektach, co przyspiesza rozwój i zmniejsza koszty.
- **Testowalność:** Komponenty można testować niezależnie, co ułatwia wykrywanie błędów i zapewnia wyższą jakość oprogramowania.
- **Skalowalność:** System można łatwo rozbudowywać, dodając nowe komponenty lub zastępując istniejące.
- **Zrozumiałość:** Architektura komponentów ułatwia zrozumienie struktury i działania systemu.

## Cohesion (Spójność)

Wysoka spójność oznacza, że komponent jest skupiony na jednej odpowiedzialności, co ułatwia jego zrozumienie, testowanie i modyfikację.

## Coupling (Sprzężenie)

Coupling (sprzężenie) opisuje stopień zależności między komponentami. Niskie sprzężenie oznacza, że komponenty są luźno powiązane i komunikują się za pomocą prostych, dobrze zdefiniowanych interfejsów. Wysokie sprzężenie oznacza, że komponenty są silnie zależne od siebie, co utrudnia ich modyfikację i testowanie.

## Relacja między cohesion i coupling

W idealnej architekturze komponentów dążymy do wysokiej spójności i niskiego sprzężenia. Oznacza to, że każdy komponent powinien być odpowiedzialny za jedną, dobrze zdefiniowaną funkcjonalność (wysoka spójność) i komunikować się z innymi komponentami za pomocą prostych, dobrze zdefiniowanych interfejsów (niskie sprzężenie).

## Przykłady w praktyce

Architektura komponentów jest szeroko stosowana w różnych technologiach i dziedzinach. Oto kilka przykładów:

- **React:** Biblioteka JavaScript do tworzenia interfejsów użytkownika, w której aplikacje są budowane z komponentów.
- **Angular:** Framework JavaScript do tworzenia aplikacji internetowych, który również opiera się na architekturze komponentów.
- **Mikrousługi:** Podejście do architektury oprogramowania, w którym aplikacja jest zbudowana z małych, niezależnych usług, które komunikują się ze sobą za pomocą API.

### Przykład w Javie
Oto krótkie przykłady w Javie ilustrujące spójność (cohesion) i sprzężenie (coupling):

**Wysoka spójność (High Cohesion):**

```java
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    // ... (inne metody arytmetyczne)
}
```

W tym przykładzie klasa `Calculator` ma wysoką spójność, ponieważ wszystkie jej metody są związane z jednym, dobrze zdefiniowanym zadaniem: wykonywaniem obliczeń arytmetycznych.

**Niskie sprzężenie (Low Coupling):**

```java
interface Logger {
    void log(String message);
}

class FileLogger implements Logger {
    // ... (implementacja logowania do pliku)
}

class ConsoleLogger implements Logger {
    // ... (implementacja logowania do konsoli)
}

class Application {
    private Logger logger;

    public Application(Logger logger) {
        this.logger = logger;
    }

    public void doSomething() {
        // ... (jakaś logika)
        logger.log("Coś się wydarzyło");
    }
}
```

W tym przykładzie klasa `Application` ma niskie sprzężenie z konkretnymi implementacjami logowania (`FileLogger`, `ConsoleLogger`). Zamiast tego, klasa `Application` zależy od interfejsu `Logger`, co pozwala na łatwą zmianę sposobu logowania bez konieczności modyfikacji samej klasy `Application`.

**Niska spójność (Low Cohesion):**

```java
class GodClass {
    public void calculateSalary() { /* ... */ }
    public void sendEmail() { /* ... */ }
    public void connectToDatabase() { /* ... */ }
    // ... (wiele innych, niepowiązanych metod)
}
```

Klasa `GodClass` ma niską spójność, ponieważ zawiera wiele metod, które nie są ze sobą powiązane i wykonują różne, niezależne zadania.

**Wysokie sprzężenie (High Coupling):**

```java
class Order {
    private DatabaseConnection db;

    public Order() {
        db = new DatabaseConnection(); // Bezpośrednie utworzenie obiektu
    }

    public void save() {
        db.connect(); // Bezpośrednie wywołanie metody
        // ... (logika zapisu do bazy danych)
    }
}
```

Klasa `Order` ma wysokie sprzężenie z klasą `DatabaseConnection`, ponieważ bezpośrednio tworzy jej obiekt i wywołuje jej metody. To utrudnia testowanie klasy `Order` i wprowadzanie zmian w sposobie łączenia się z bazą danych.


#it #widmo