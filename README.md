# 🧠 Mein Quantum Computing Lerntagebuch

> *"Wenn du glaubst, Quantenmechanik verstanden zu haben, hast du sie nicht verstanden."*  
> — Richard Feynman (und ich fühle das so hart)

---

## Warum dieses Repo existiert

Ich versuche seit ein paar Monaten, Quantum Computing zu verstehen. Nicht oberflächlich mit "Qubits sind 0 und 1 gleichzeitig" — sondern *richtig*. Mit der Mathematik dahinter. Mit den Algorithmen. Mit dem ganzen Wahnsinn.

Dieses Repo ist mein Lerntagebuch. Hier dokumentiere ich alles, was ich lerne, in meinen eigenen Worten. Manchmal verzweifelt, manchmal begeistert, immer ehrlich.

**Spoiler:** Es ist verdammt schwer. Aber auch verdammt cool.

---

# Teil I: Die Basics (aka "Was zur Hölle ist Quantenmechanik?")

## 📅 1. März — Das Doppelspalt-Experiment

Holy shit. Ich hab heute das Doppelspalt-Experiment verstanden. Naja, *"verstanden"* ist übertrieben. Ich akzeptiere es einfach.

> **Die Idee:** Elektronen verhalten sich wie Wellen... bis man hinschaut. Dann sind sie plötzlich Teilchen. WTF?!

```
Szenario 1: Niemand schaut hin
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Elektronenquelle  →  Doppelspalt  →  Schirm
      [e⁻]              ‖ ‖         ░░█░░█░░█░░
                     (Wellen)       Interferenzmuster!

Das Elektron geht irgendwie durch BEIDE Spalte gleichzeitig
und interferiert mit sich selbst. Wie eine Welle im Wasser.
```

Aber jetzt kommt der Mindfuck:

```
Szenario 2: Wir schauen hin (Detektor am Spalt)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Elektronenquelle  →  Doppelspalt  →  Detektor  →  Schirm
      [e⁻]              ‖ ‖           👁️          █   █
                     (Teilchen)                  Nur 2 Streifen!

Sobald wir MESSEN durch welchen Spalt es geht,
verhält es sich wie ein normales Teilchen.
```

Das Elektron *"weiß"* irgendwie, dass wir hinschauen, und benimmt sich anders! 🤯

**Mein Takeaway:** Die Messung selbst verändert das System. Das ist keine Esoterik, das ist Physik. Ich hasse es und liebe es gleichzeitig.

---

## 📅 3. März — Schrödingers Katze (armes Tier)

Endlich verstehe ich, worum's bei der berühmten Katze geht. Und nein, es geht nicht um Tierquälerei.

> **Das Gedankenexperiment:** Eine Katze in einer Box mit einer Giftflasche, die durch einen Quantenprozess (z.B. radioaktiver Zerfall) ausgelöst werden könnte. Solange niemand nachschaut, ist die Katze in einer **Superposition** — gleichzeitig tot UND lebendig.

```
Schrödingers Box
┌─────────────────────────────────────────────────────┐
│                                                     │
│  [☢️ Atom]  ──50%──▶  [⚙️ Trigger]  ──▶  [☠️ Gift]  │
│      │                                              │
│      └── 50% kein Zerfall ──▶ Katze lebt           │
│                                                     │
│         Zustand: |🐱⟩ = α|lebendig⟩ + β|tot⟩       │
│                                                     │
└─────────────────────────────────────────────────────┘

Erst wenn wir die Box öffnen, "entscheidet" sich das Universum.
```

**Wichtig:** Schrödinger wollte damit zeigen, wie *absurd* die Kopenhagener Interpretation ist, wenn man sie auf makroskopische Objekte anwendet. Es war als Kritik gemeint! Aber die Physiker haben nur gesagt "Ja, genau so funktioniert's" und sind weitergegangen. Absolute Madlads.

**Die eigentliche Frage:** Wo ist die Grenze zwischen Quanten- und klassischer Welt? Das ist das sogenannte **Messproblem**, und niemand hat eine befriedigende Antwort darauf. Ich auch nicht. Sorry.

---

## 📅 5. März — Warum Quantencomputer überhaupt interessant sind

Okay, bevor ich in die Mathematik eintauche, muss ich mir klarmachen, *warum* das alles wichtig ist.

**Das Problem mit klassischen Computern:**

Manche Probleme sind einfach *zu groß*. Beispiel: Du willst eine Zahl wie `12345678901234567890123` in ihre Primfaktoren zerlegen. Klassisch? Dauert länger als das Universum alt ist.

**Was Quantencomputer können:**

| Problem | Klassisch | Quantencomputer |
|---------|-----------|-----------------|
| Faktorisierung (RSA knacken) | ~10.000 Jahre | ~Minuten (Shor) |
| Datenbanksuche (unsortiert) | O(N) | O(√N) (Grover) |
| Molekülsimulation | Unmöglich ab ~50 Atome | Machbar |
| Optimierungsprobleme | Brute Force | Quantenannealing |

**Der Haken:** Quantencomputer sind *nicht* einfach "schnellere Computer". Sie sind gut für ganz spezifische Probleme. Für Netflix schauen sind sie komplett nutzlos.

---

# Teil II: Die Mathematik (aka "Jetzt wird's ernst")

## 📅 8. März — Lineare Algebra Crashkurs

Ich dachte, ich kann Mathe. Dann hab ich Quantum Computing angefangen.

**Die brutale Wahrheit:** Ohne lineare Algebra versteht man gar nichts. Nicht ein bisschen. Null. Also hab ich meine alten Uni-Bücher rausgeholt...

### Vektoren — Die Sprache der Quantenzustände

Ein Qubit ist mathematisch gesehen einfach ein **Vektor**. Ein 2D-Vektor, um genau zu sein.

```
Klassisches Bit:        Qubit:
                        
    0 oder 1            |ψ⟩ = α|0⟩ + β|1⟩
                        
                        wobei |α|² + |β|² = 1
```

In Vektorschreibweise:

$$|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad |1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$$

Ein allgemeiner Qubit-Zustand:

$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$$

wobei $\alpha, \beta \in \mathbb{C}$ (komplexe Zahlen!) und $|\alpha|^2 + |\beta|^2 = 1$.

**Warum komplexe Zahlen?** Weil Quantenmechanik. Ernsthaft, die Natur scheint komplexe Zahlen zu mögen. Deal with it.

### Beispiel: Normierung eines Vektors

Angenommen ich hab einen Vektor $v = \begin{pmatrix} 3+4i \\ 1-2i \end{pmatrix}$. Ist der normiert?

**Schritt 1:** Berechne $|v_1|^2$ und $|v_2|^2$

$$|3+4i|^2 = 3^2 + 4^2 = 9 + 16 = 25$$

$$|1-2i|^2 = 1^2 + (-2)^2 = 1 + 4 = 5$$

**Schritt 2:** Summieren

$$||v||^2 = 25 + 5 = 30$$

$$||v|| = \sqrt{30} \neq 1$$

**Ergebnis:** Nope, nicht normiert. Kein gültiger Quantenzustand (noch nicht).

---

## 📅 10. März — Das Skalarprodukt (Inneres Produkt)

Das Skalarprodukt ist wichtig, weil es uns sagt, wie "ähnlich" zwei Zustände sind.

**Definition:** Für zwei Vektoren $u$ und $v$:

$$\langle u | v \rangle = u^\dagger v = \sum_i u_i^* v_i$$

Das $\dagger$ (Dolch) bedeutet: Transponieren UND komplex konjugieren.

### Durchgerechnetes Beispiel

Gegeben: $u = \begin{pmatrix} 1+i \\ 2-i \end{pmatrix}$ und $v = \begin{pmatrix} 3-2i \\ 4+i \end{pmatrix}$

**Schritt 1:** Berechne $u^\dagger$ (transponieren + konjugieren)

$$u^\dagger = \begin{pmatrix} (1+i)^* & (2-i)^* \end{pmatrix} = \begin{pmatrix} 1-i & 2+i \end{pmatrix}$$

**Schritt 2:** Multiplizieren

$$\langle u | v \rangle = (1-i)(3-2i) + (2+i)(4+i)$$

Erstes Produkt:
$$(1-i)(3-2i) = 3 - 2i - 3i + 2i^2 = 3 - 5i + 2(-1) = 1 - 5i$$

Zweites Produkt:
$$(2+i)(4+i) = 8 + 2i + 4i + i^2 = 8 + 6i - 1 = 7 + 6i$$

**Ergebnis:**
$$\langle u | v \rangle = (1-5i) + (7+6i) = 8 + i$$

**Was bedeutet das?** Wenn $\langle u | v \rangle = 0$, sind die Zustände **orthogonal** (komplett unterschiedlich). Je größer der Betrag, desto "ähnlicher" sind sie.

---

## 📅 12. März — Matrizen und Quantengatter

Quantengatter sind nichts anderes als **Matrizen**. Du willst ein Qubit transformieren? Multiplizier eine Matrix mit dem Zustandsvektor. Fertig.

### Die wichtigsten Gatter

**Pauli-X Gate** (Quantum NOT):
$$X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$

```
X|0⟩ = |1⟩
X|1⟩ = |0⟩

Das ist wie klassisches NOT, aber in schick.
```

**Hadamard Gate** (DAS wichtigste Gate):
$$H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

```
H|0⟩ = (|0⟩ + |1⟩) / √2  = |+⟩
H|1⟩ = (|0⟩ - |1⟩) / √2  = |-⟩

Das erzeugt Superposition aus einem definierten Zustand!
```

**Pauli-Z Gate** (Phase Flip):
$$Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

```
Z|0⟩ = |0⟩
Z|1⟩ = -|1⟩

Ändert nur die Phase von |1⟩. Sieht man bei Messung nicht,
aber für Interferenz ist's wichtig.
```

### Beispiel: Hadamard auf |0⟩

$$H|0\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$

$$= \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \cdot 1 + 1 \cdot 0 \\ 1 \cdot 1 + (-1) \cdot 0 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

Das ist $\frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$ — perfekte Superposition! 50% Chance für 0, 50% für 1.

---

## 📅 15. März — Unitäre Matrizen (wichtig!)

Nicht jede Matrix ist ein gültiges Quantengatter. Nur **unitäre** Matrizen sind erlaubt.

**Definition:** Eine Matrix $U$ ist unitär, wenn $U^\dagger U = UU^\dagger = I$

**Warum?** Weil Quantenmechanik Wahrscheinlichkeiten erhält. Wenn du mit einem normierten Zustand startest, muss der Output auch normiert sein.

### Check: Ist Hadamard unitär?

$$H^\dagger H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \cdot \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

$$= \frac{1}{2} \begin{pmatrix} 1+1 & 1-1 \\ 1-1 & 1+1 \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark$$

Yep, Hadamard ist unitär. Alles gut.

---

## 📅 18. März — Tensorprodukt (Multi-Qubit-Systeme)

Okay, ein Qubit ist cool. Aber die echte Power kommt von **mehreren Qubits zusammen**.

**Problem:** Wie beschreibe ich zwei Qubits mathematisch?

**Lösung:** Tensorprodukt (auch Kronecker-Produkt genannt), geschrieben als $\otimes$

### Beispiel: Zwei Qubits

Qubit A im Zustand $|0\rangle$, Qubit B im Zustand $|1\rangle$:

$$|0\rangle \otimes |1\rangle = |01\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix}$$

Wie berechnet man das? Jedes Element des ersten Vektors mal den gesamten zweiten Vektor:

$$= \begin{pmatrix} 1 \cdot \begin{pmatrix} 0 \\ 1 \end{pmatrix} \\ 0 \cdot \begin{pmatrix} 0 \\ 1 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}$$

**Die vier Basiszustände für 2 Qubits:**

$$|00\rangle = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}, \quad |01\rangle = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}, \quad |10\rangle = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}, \quad |11\rangle = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}$$

**Exponentielle Explosion:** n Qubits brauchen einen Vektor mit $2^n$ Einträgen. Bei 50 Qubits sind das über 1 Billiarde komplexe Zahlen. Deshalb sind Quantencomputer so schwer zu simulieren!

---

## 📅 20. März — Verschränkung (Entanglement)

DAS ist der Moment, wo Quantenmechanik wirklich weird wird.

**Definition:** Zwei Qubits sind **verschränkt**, wenn ihr gemeinsamer Zustand sich NICHT als Tensorprodukt einzelner Zustände schreiben lässt.

### Die Bell-Zustände (maximale Verschränkung)

Der berühmteste verschränkte Zustand:

$$|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$$

**Warum ist das verschränkt?** Versuch mal, das als $|a\rangle \otimes |b\rangle$ zu schreiben:

$$(\alpha|0\rangle + \beta|1\rangle) \otimes (\gamma|0\rangle + \delta|1\rangle) = \alpha\gamma|00\rangle + \alpha\delta|01\rangle + \beta\gamma|10\rangle + \beta\delta|11\rangle$$

Für $|\Phi^+\rangle$ bräuchten wir: $\alpha\gamma = \frac{1}{\sqrt{2}}$, $\alpha\delta = 0$, $\beta\gamma = 0$, $\beta\delta = \frac{1}{\sqrt{2}}$

Aber wenn $\alpha\delta = 0$, dann ist $\alpha = 0$ ODER $\delta = 0$.
- Falls $\alpha = 0$: dann ist $\alpha\gamma = 0 \neq \frac{1}{\sqrt{2}}$ ❌
- Falls $\delta = 0$: dann ist $\beta\delta = 0 \neq \frac{1}{\sqrt{2}}$ ❌

**Unmöglich!** Der Zustand ist echt verschränkt.

### Was bedeutet das physikalisch?

```
Situation: Alice und Bob haben je ein Qubit von |Φ+⟩
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

    Alice                              Bob
      🧑‍🔬                                👨‍🔬
      ↓                                 ↓
    Qubit A ~~~~~~~~verschränkt~~~~~~~~ Qubit B
      
Wenn Alice misst und |0⟩ bekommt → Bob's Qubit ist SOFORT |0⟩
Wenn Alice misst und |1⟩ bekommt → Bob's Qubit ist SOFORT |1⟩

Egal wie weit sie voneinander entfernt sind!
```

**Einstein nannte das "spukhafte Fernwirkung"** und hasste es. Aber Experimente haben gezeigt: Es ist real. Die Natur ist einfach so.

**Wichtig:** Man kann damit KEINE Information übertragen! Alice's Messergebnis ist zufällig. Bob weiß nicht, was Alice gemessen hat, bis sie ihm (klassisch) mitteilt.

---

## 📅 25. März — Die Messungspostulate

Okay, ich hab lange um dieses Thema herumgetanzt. Aber Messung ist fundamental.

### Was passiert bei einer Messung?

**Vor der Messung:** Qubit ist in Superposition $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$

**Nach der Messung:** Qubit ist entweder $|0\rangle$ ODER $|1\rangle$

**Wahrscheinlichkeiten:**
- P(Ergebnis 0) = $|\alpha|^2$
- P(Ergebnis 1) = $|\beta|^2$

### Beispiel mit echten Zahlen

Zustand: $|\psi\rangle = \frac{1}{\sqrt{3}}|0\rangle + \sqrt{\frac{2}{3}}|1\rangle$

**Check:** Ist das normiert?

$$\left|\frac{1}{\sqrt{3}}\right|^2 + \left|\sqrt{\frac{2}{3}}\right|^2 = \frac{1}{3} + \frac{2}{3} = 1 \quad \checkmark$$

**Messwahrscheinlichkeiten:**
- P(0) = $\frac{1}{3}$ ≈ 33.3%
- P(1) = $\frac{2}{3}$ ≈ 66.7%

**Nach der Messung:**
- Wenn wir 0 messen: Zustand kollabiert zu $|0\rangle$
- Wenn wir 1 messen: Zustand kollabiert zu $|1\rangle$

Die Superposition ist **zerstört**. Irreversibel. Das ist der "Kollaps der Wellenfunktion".

---

# Teil III: Die Algorithmen (aka "Jetzt wird's spannend")

## 📅 1. April — Der Deutsch-Jozsa Algorithmus

Mein erster "richtiger" Quantenalgorithmus! Er ist nicht praktisch nützlich, aber er zeigt perfekt, warum Quantencomputer cool sind.

### Das Problem

Du hast eine Black-Box-Funktion $f: \{0,1\}^n \to \{0,1\}$

Die Funktion ist **entweder:**
1. **Konstant:** $f(x) = 0$ für alle x, ODER $f(x) = 1$ für alle x
2. **Balanciert:** Genau die Hälfte der Inputs gibt 0, die andere Hälfte 1

**Aufgabe:** Finde heraus, welcher Typ!

### Klassisch vs. Quantum

**Klassisch:** Im schlimmsten Fall musst du $2^{n-1} + 1$ Inputs testen. Bei n=100 sind das... viel zu viele.

**Quantum:** EIN einziger Query! 🤯

### Der Algorithmus (für n=1, einfachster Fall)

```
Schaltkreis:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

|0⟩ ──[H]──┬──[H]──[Messung]
           │
|1⟩ ──[H]──┴──────────────────

         ↑
       Orakel Uf
```

**Schritt für Schritt:**

1. **Start:** $|01\rangle$

2. **Hadamard auf beide:**
   $$H|0\rangle \otimes H|1\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) \otimes \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$$
   
   $$= \frac{1}{2}(|0\rangle + |1\rangle)(|0\rangle - |1\rangle)$$

3. **Orakel anwenden:** Das Orakel flippt das zweite Qubit wenn $f(x)=1$
   
   Nach etwas Mathe (die ich hier spare) kommt raus:
   
   - Wenn f konstant: erstes Qubit ist $\pm|0\rangle$
   - Wenn f balanciert: erstes Qubit ist $\pm|1\rangle$

4. **Hadamard auf erstes Qubit und messen:**
   - Messung = 0 → f ist konstant
   - Messung = 1 → f ist balanciert

**Eine Messung.** Das ist der Quantum Speedup.

---

## 📅 10. April — Grover's Suchalgorithmus

DAS ist der Algorithmus, der mich am meisten beeindruckt hat. Quadratischer Speedup für Suche!

### Das Problem

Du hast eine unsortierte Datenbank mit N Einträgen. Du suchst einen bestimmten Eintrag.

- **Klassisch:** O(N) — im Schnitt N/2 Versuche
- **Quantum (Grover):** O(√N) — nur ~√N Versuche

Bei N = 1.000.000: Klassisch ~500.000 vs Quantum ~1.000 Versuche!

### Die Idee

Grover funktioniert durch **Amplitudenverstärkung**:

1. Starte mit gleichmäßiger Superposition aller Zustände
2. Markiere den gesuchten Zustand (negative Phase)
3. Verstärke die Amplitude des markierten Zustands
4. Wiederhole 2-3 etwa √N mal
5. Miss — du bekommst den gesuchten Zustand mit hoher Wahrscheinlichkeit

### Durchgerechnetes Beispiel: N=4 (2 Qubits)

Wir suchen $|11\rangle$ in der "Datenbank" $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$.

**Anzahl Iterationen:** $\lfloor \frac{\pi}{4}\sqrt{4} \rfloor = \lfloor \frac{\pi}{2} \rfloor = 1$

**Schritt 1: Initialisierung + Hadamard**

$$|\psi_0\rangle = H^{\otimes 2}|00\rangle = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$$

Alle Amplituden sind $\frac{1}{2}$.

**Schritt 2: Orakel (markiert $|11\rangle$)**

Das Orakel flippt die Phase von $|11\rangle$:

$$U_f = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$$

$$U_f|\psi_0\rangle = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle - |11\rangle)$$

Jetzt hat $|11\rangle$ die Amplitude $-\frac{1}{2}$.

**Schritt 3: Diffusor (Verstärkung)**

Der Diffusor ist $D = 2|\psi_0\rangle\langle\psi_0| - I$

Das ist eine Reflexion am Durchschnitt. Effektiv:
- Berechne den Durchschnitt aller Amplituden
- Reflektiere jede Amplitude an diesem Durchschnitt

Durchschnitt: $\bar{a} = \frac{1}{4}\left(\frac{1}{2} + \frac{1}{2} + \frac{1}{2} - \frac{1}{2}\right) = \frac{1}{4}$

Neue Amplituden:
- $|00\rangle$: $2 \cdot \frac{1}{4} - \frac{1}{2} = 0$
- $|01\rangle$: $2 \cdot \frac{1}{4} - \frac{1}{2} = 0$
- $|10\rangle$: $2 \cdot \frac{1}{4} - \frac{1}{2} = 0$
- $|11\rangle$: $2 \cdot \frac{1}{4} - (-\frac{1}{2}) = 1$

**Endzustand:**

$$|\psi_{final}\rangle = |11\rangle$$

**Messung:** 100% Wahrscheinlichkeit für $|11\rangle$! 🎯

---

## 📅 20. April — Shor's Algorithmus (der große Boss)

Das ist der Algorithmus, der RSA-Verschlüsselung brechen könnte. Deshalb investieren Regierungen Milliarden in Quantencomputer (und in Post-Quantum-Kryptographie).

### Das Problem: Faktorisierung

Gegeben: Eine große Zahl $N = p \cdot q$ (Produkt zweier Primzahlen)
Gesucht: Die Faktoren $p$ und $q$

**Beispiel:** $N = 15$ → Faktoren sind 3 und 5

Klingt einfach? Bei einer 2048-Bit-Zahl (wie in RSA) wäre klassische Faktorisierung praktisch unmöglich.

### Die Grundidee

Shor hat erkannt: Faktorisierung kann auf **Periodenfindung** reduziert werden. Und Quantencomputer sind verdammt gut darin, Perioden zu finden.

**Der Trick:**

1. Wähle zufälliges $a < N$ mit $\gcd(a, N) = 1$
2. Finde die Periode $r$ von $f(x) = a^x \mod N$
3. Wenn $r$ gerade und $a^{r/2} \not\equiv -1 \mod N$:
   - $\gcd(a^{r/2} - 1, N)$ ist ein Faktor!
   - $\gcd(a^{r/2} + 1, N)$ ist der andere!

### Durchgerechnetes Beispiel: N = 15

Wir faktorisieren $N = 15$. Wählen wir $a = 7$.

**Schritt 1: Periodenfindung**

Berechne $7^x \mod 15$ für verschiedene x:

| x | $7^x$ | $7^x \mod 15$ |
|---|-------|---------------|
| 1 | 7 | 7 |
| 2 | 49 | 4 |
| 3 | 343 | 13 |
| 4 | 2401 | 1 |
| 5 | 16807 | 7 |

Die Sequenz wiederholt sich! Periode $r = 4$.

**(Hier würde der Quantencomputer die Quanten-Fourier-Transformation nutzen, um r effizient zu finden)**

**Schritt 2: Faktoren berechnen**

$r = 4$ ist gerade ✓

$$a^{r/2} = 7^2 = 49$$

$$a^{r/2} - 1 = 49 - 1 = 48$$
$$a^{r/2} + 1 = 49 + 1 = 50$$

$$\gcd(48, 15) = 3 \quad \checkmark$$
$$\gcd(50, 15) = 5 \quad \checkmark$$

**Ergebnis:** $15 = 3 \times 5$ 🎉

### Die Quanten-Fourier-Transformation (QFT)

Das Herzstück von Shor. Die QFT transformiert einen Zustand so, dass periodische Strukturen sichtbar werden.

$$QFT|x\rangle = \frac{1}{\sqrt{N}} \sum_{k=0}^{N-1} e^{2\pi i xk/N} |k\rangle$$

Das ist die Quanten-Version der diskreten Fourier-Transformation — aber exponentiell schneller berechenbar!

---

## 📅 1. Mai — Quanten-Fehlerkorrektur (kurzer Ausflug)

Real Talk: Echte Quantencomputer sind EXTREM fehleranfällig. Qubits dekohärieren, Gatter sind ungenau, Messungen sind fehlerhaft.

**Das Problem:** Du kannst einen Quantenzustand nicht einfach kopieren (No-Cloning-Theorem!) und du kannst ihn nicht messen ohne ihn zu zerstören. Wie korrigierst du dann Fehler?

**Die Lösung:** Verteile ein logisches Qubit über mehrere physische Qubits. Miss "Syndrome" statt den Zustand direkt.

```
Klassisch:                     Quantum:
───────────                    ─────────
Bit → Kopie → Kopie            |ψ⟩ → verschränkt über viele Qubits
                                    → Miss Syndrome
Vergleiche Kopien                   → Korrigiere Fehler
                                    → Logisches Qubit intakt!
```

**Der Shor-Code** (nicht der Algorithmus!): 9 physische Qubits für 1 logisches Qubit. Kann beliebige Einzelqubit-Fehler korrigieren.

**Surface Codes:** Aktuell der vielversprechendste Ansatz. Google und IBM arbeiten intensiv daran.

---

# Teil IV: Meine aktuellen Projekte

## 🔬 RCS Benchmark (dieses Repo!)

Ich baue einen **Random Circuit Sampling** Simulator in Rust. Das ist genau die Aufgabe, mit der Google 2019 "Quantum Supremacy" demonstriert hat.

**Was der Simulator macht:**
1. Generiert zufällige Quantenschaltkreise
2. Simuliert sie klassisch (State Vector)
3. Berechnet den XEB-Score (Cross-Entropy Benchmark)

**Warum?** Um zu verstehen, wie man Quantencomputer benchmarkt. Und um Rust zu üben. Win-Win.

[→ Zum RCS Benchmark Code](/src)

---

# Ressourcen, die mir geholfen haben

## Bücher (die ich wirklich gelesen habe)

1. **"Quantum Computation and Quantum Information"** — Nielsen & Chuang
   - DAS Standardwerk. Dick. Mathematisch. Aber gut.

2. **"Quantum Computing: An Applied Approach"** — Hidary
   - Moderner, mehr Code-Beispiele. Empfehlenswert!

3. **"Programming Quantum Computers"** — Gimeno-Segovia et al.
   - Praktischer Fokus. Gut für den Einstieg.

## Online-Kurse

- [IBM Qiskit Textbook](https://qiskit.org/textbook/) — Kostenlos, interaktiv, sehr gut!
- [Brilliant.org Quantum Computing](https://brilliant.org/) — Für Visualisierungen
- [edX: Quantum Computing Fundamentals](https://www.edx.org/) — MIT-Kurs, anspruchsvoll

## YouTube-Kanäle

- **3Blue1Brown** — Für lineare Algebra Intuition
- **Looking Glass Universe** — Quantenmechanik erklärt
- **Qiskit** — Offizielle Tutorials

## Papers (wenn du Masochist bist)

- [Google Quantum Supremacy Paper (2019)](https://www.nature.com/articles/s41586-019-1666-5)
- [Shor's Original Paper](https://arxiv.org/abs/quant-ph/9508027)
- [Grover's Original Paper](https://arxiv.org/abs/quant-ph/9605043)

---

# Offene Fragen (die mich nachts wachhalten)

1. **Was IST Messung eigentlich?** Warum kollabiert die Wellenfunktion? Ist es wirklich zufällig?

2. **Many-Worlds vs. Copenhagen:** Sind das nur Interpretationen oder gibt's einen Unterschied?

3. **Wo ist die Grenze?** Ab wann ist ein System "klassisch"? Warum sehen wir keine Superpositionen im Alltag?

4. **Quantum Computing Hype:** Werden wir jemals nützliche Quantencomputer haben? Oder bleibt's bei 100-Qubit-Spielzeug?

5. **Was macht Bewusstsein?** (Okay, das ist Philosophie, aber die Quantenleute haben mich angesteckt...)

---

## 📅 Letzte Aktualisierung: Heute

Ich update dieses Dokument regelmäßig, wenn ich was Neues lerne. Feedback willkommen!

---

*"The universe is not only queerer than we suppose, but queerer than we CAN suppose."*  
— J.B.S. Haldane

---

**Autor:** Ein verwirrter Informatiker, der zu viel Zeit mit Quantenmechanik verbringt

**Lizenz:** MIT (für den Code) / CC BY-SA (für den Text)