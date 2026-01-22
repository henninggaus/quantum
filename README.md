# 🧠 Mein Quantum Computing Lerntagebuch

> *"Wenn du glaubst, Quantenmechanik verstanden zu haben, hast du sie nicht verstanden."*  
> — Richard Feynman (und ich fühle das so hart)

---

## 📑 Inhaltsverzeichnis

- [Warum dieses Repo existiert](#warum-dieses-repo-existiert)
- **Teil I: Die Basics**
  - [Das Doppelspalt-Experiment](#das-doppelspalt-experiment)
  - [Schrödingers Katze](#schrödingers-katze-armes-tier)
  - [Warum Quantencomputer überhaupt interessant sind](#warum-quantencomputer-überhaupt-interessant-sind)
- **Teil II: Die Mathematik**
  - [Lineare Algebra Crashkurs](#lineare-algebra-crashkurs)
  - [Das Skalarprodukt](#das-skalarprodukt-inneres-produkt)
  - [Matrizen und Quantengatter](#matrizen-und-quantengatter)
  - [Mehr-Qubit-Gatter](#mehr-qubit-gatter)
  - [Unitäre Matrizen](#unitäre-matrizen-wichtig)
  - [Tensorprodukt](#tensorprodukt-multi-qubit-systeme)
  - [Verschränkung](#verschränkung-entanglement)
  - [Die Messungspostulate](#die-messungspostulate)
- **Teil III: Die Algorithmen**
  - [Der Deutsch-Jozsa Algorithmus](#der-deutsch-jozsa-algorithmus)
  - [Grover's Suchalgorithmus](#grovers-suchalgorithmus)
  - [Shor's Algorithmus](#shors-algorithmus-der-große-boss)
  - [Quanten-Fehlerkorrektur](#quanten-fehlerkorrektur)
- **Teil IV: Machine Learning meets Quantum**
  - [Warum ML + Quantum?](#warum-ml--quantum)
  - [Neural-Network Quantum States](#neural-network-quantum-states-nqs)
  - [Quantum State Tomography mit CNNs](#quantum-state-tomography-mit-cnns)
- **Teil V: Hardware & Aktuelle Entwicklungen (2024/2025)**
  - [Google Willow — Der Durchbruch bei der Fehlerkorrektur](#google-willow--der-durchbruch-bei-der-fehlerkorrektur-dezember-2024)
  - [IBM's Roadmap — Condor, Heron und darüber hinaus](#ibms-roadmap--condor-heron-und-darüber-hinaus)
  - [Der Wettlauf der Giganten](#der-wettlauf-der-giganten)
  - [NISQ vs. Fault-Tolerant — Wo stehen wir wirklich?](#nisq-vs-fault-tolerant--wo-stehen-wir-wirklich)
- **Teil VI: Post-Quantum Kryptographie**
  - [Das Problem: Shor bedroht alles](#das-problem-shor-bedroht-alles)
  - [NIST's neue Standards (August 2024)](#nists-neue-standards-august-2024)
  - [Die neuen Algorithmen erklärt](#die-neuen-algorithmen-erklärt)
  - [Was bedeutet das für dich?](#was-bedeutet-das-für-dich)
- **Teil VII: Meine Projekte & Ressourcen**
  - [RCS Benchmark](#-rcs-benchmark-dieses-repo)
  - [Ressourcen die mir geholfen haben](#ressourcen-die-mir-geholfen-haben)
  - [Offene Fragen](#offene-fragen-die-mich-nachts-wachhalten)

---

## Warum dieses Repo existiert

Ich versuche seit ein paar Monaten, Quantum Computing zu verstehen. Nicht oberflächlich mit "Qubits sind 0 und 1 gleichzeitig" — sondern *richtig*. Mit der Mathematik dahinter. Mit den Algorithmen. Mit dem ganzen Wahnsinn.

Dieses Repo ist mein Lerntagebuch. Hier dokumentiere ich alles, was ich lerne, in meinen eigenen Worten. Manchmal verzweifelt, manchmal begeistert, immer ehrlich.

**Spoiler:** Es ist verdammt schwer. Aber auch verdammt cool.

---

# Teil I: Die Basics (aka "Was zur Hölle ist Quantenmechanik?")

## Das Doppelspalt-Experiment

Holy shit. Ich hab das Doppelspalt-Experiment verstanden. Naja, *"verstanden"* ist übertrieben. Ich akzeptiere es einfach.

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

## Schrödingers Katze (armes Tier)

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

## Warum Quantencomputer überhaupt interessant sind

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

## Lineare Algebra Crashkurs

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

```
|0⟩ = [ 1 ]      |1⟩ = [ 0 ]
      [ 0 ]            [ 1 ]
```

Ein allgemeiner Qubit-Zustand:

```
|ψ⟩ = α|0⟩ + β|1⟩ = [ α ]
                     [ β ]

wobei α, β ∈ ℂ (komplexe Zahlen!) und |α|² + |β|² = 1
```

**Warum komplexe Zahlen?** Weil Quantenmechanik. Ernsthaft, die Natur scheint komplexe Zahlen zu mögen. Deal with it.

### Beispiel: Normierung eines Vektors

Angenommen ich hab einen Vektor:

```
v = [ 3+4i ]
    [ 1-2i ]
```

Ist der normiert?

**Schritt 1:** Berechne |v₁|² und |v₂|²

```
|3+4i|² = 3² + 4² = 9 + 16 = 25
|1-2i|² = 1² + (-2)² = 1 + 4 = 5
```

**Schritt 2:** Summieren

```
||v||² = 25 + 5 = 30
||v|| = √30 ≠ 1
```

**Ergebnis:** Nope, nicht normiert. Kein gültiger Quantenzustand (noch nicht).

---

## Das Skalarprodukt (Inneres Produkt)

Das Skalarprodukt ist wichtig, weil es uns sagt, wie "ähnlich" zwei Zustände sind.

**Definition:** Für zwei Vektoren u und v:

```
⟨u|v⟩ = u†v = Σᵢ uᵢ* vᵢ
```

Das † (Dolch) bedeutet: Transponieren UND komplex konjugieren.

### Durchgerechnetes Beispiel

Gegeben:

```
u = [ 1+i  ]      v = [ 3-2i ]
    [ 2-i  ]          [ 4+i  ]
```

**Schritt 1:** Berechne u† (transponieren + konjugieren)

```
u† = [ (1+i)*  (2-i)* ] = [ 1-i  2+i ]
```

**Schritt 2:** Multiplizieren

```
⟨u|v⟩ = (1-i)(3-2i) + (2+i)(4+i)
```

Erstes Produkt:
```
(1-i)(3-2i) = 3 - 2i - 3i + 2i² = 3 - 5i + 2(-1) = 1 - 5i
```

Zweites Produkt:
```
(2+i)(4+i) = 8 + 2i + 4i + i² = 8 + 6i - 1 = 7 + 6i
```

**Ergebnis:**
```
⟨u|v⟩ = (1-5i) + (7+6i) = 8 + i
```

**Was bedeutet das?** Wenn ⟨u|v⟩ = 0, sind die Zustände **orthogonal** (komplett unterschiedlich). Je größer der Betrag, desto "ähnlicher" sind sie.

---

## Matrizen und Quantengatter

Quantengatter sind nichts anderes als **Matrizen**. Du willst ein Qubit transformieren? Multiplizier eine Matrix mit dem Zustandsvektor. Fertig.

### Die wichtigsten Einzel-Qubit-Gatter

**Pauli-X Gate** (Quantum NOT):

```
X = [ 0  1 ]
    [ 1  0 ]

X|0⟩ = |1⟩
X|1⟩ = |0⟩

Das ist wie klassisches NOT, aber in schick.
```

**Pauli-Y Gate:**

```
Y = [ 0  -i ]
    [ i   0 ]
```

**Pauli-Z Gate** (Phase Flip):

```
Z = [ 1   0 ]
    [ 0  -1 ]

Z|0⟩ = |0⟩
Z|1⟩ = -|1⟩

Ändert nur die Phase von |1⟩. Sieht man bei Messung nicht,
aber für Interferenz ist's wichtig.
```

**Hadamard Gate** (DAS wichtigste Gate):

```
H = 1/√2 [ 1   1 ]
         [ 1  -1 ]

H|0⟩ = (|0⟩ + |1⟩) / √2  = |+⟩
H|1⟩ = (|0⟩ - |1⟩) / √2  = |-⟩

Das erzeugt Superposition aus einem definierten Zustand!
```

### Beispiel: Hadamard auf |0⟩

```
H|0⟩ = 1/√2 [ 1   1 ] [ 1 ]
            [ 1  -1 ] [ 0 ]

     = 1/√2 [ 1·1 + 1·0 ]   = 1/√2 [ 1 ]
            [ 1·1 + (-1)·0 ]       [ 1 ]
```

Das ist `1/√2 (|0⟩ + |1⟩)` — perfekte Superposition! 50% Chance für 0, 50% für 1.

---

## Mehr-Qubit-Gatter

Hier wird's spannend! Gatter die auf mehrere Qubits gleichzeitig wirken.

### CNOT-Gate (Controlled-NOT)

Das CNOT ist ein 2-Qubit-Gatter:
- **Kontroll-Qubit:** Wenn es |1⟩ ist, wird das Ziel geflippt
- **Ziel-Qubit:** Wird geflippt (oder nicht)

```
CNOT = [ 1  0  0  0 ]
       [ 0  1  0  0 ]
       [ 0  0  0  1 ]
       [ 0  0  1  0 ]

Basis: |00⟩, |01⟩, |10⟩, |11⟩
         ↓     ↓     ↓     ↓
       |00⟩  |01⟩  |11⟩  |10⟩
```

**Schaltkreis-Symbol:**
```
Control ──●──
          │
Target  ──⊕──
```

**Beispiele:**
```
CNOT|00⟩ = |00⟩   (Kontrolle=0, nichts passiert)
CNOT|01⟩ = |01⟩   (Kontrolle=0, nichts passiert)
CNOT|10⟩ = |11⟩   (Kontrolle=1, Ziel wird geflippt!)
CNOT|11⟩ = |10⟩   (Kontrolle=1, Ziel wird geflippt!)
```

### Toffoli-Gate (CCNOT)

Das ist ein 3-Qubit-Gatter mit ZWEI Kontroll-Qubits:

```
Toffoli: Flippt Ziel nur wenn BEIDE Kontrollen = |1⟩

Control 1 ──●──
            │
Control 2 ──●──
            │
Target    ──⊕──
```

Die Matrix ist 8×8 (2³ = 8 Basiszustände):

```
Toffoli = [ 1 0 0 0 0 0 0 0 ]   |000⟩ → |000⟩
          [ 0 1 0 0 0 0 0 0 ]   |001⟩ → |001⟩
          [ 0 0 1 0 0 0 0 0 ]   |010⟩ → |010⟩
          [ 0 0 0 1 0 0 0 0 ]   |011⟩ → |011⟩
          [ 0 0 0 0 1 0 0 0 ]   |100⟩ → |100⟩
          [ 0 0 0 0 0 1 0 0 ]   |101⟩ → |101⟩
          [ 0 0 0 0 0 0 0 1 ]   |110⟩ → |111⟩  ← Flip!
          [ 0 0 0 0 0 0 1 0 ]   |111⟩ → |110⟩  ← Flip!
```

**Beispiel: Toffoli|110⟩**

```
Beide Kontroll-Qubits sind |1⟩ → Ziel wird geflippt
|110⟩ → |111⟩
```

**Fun Fact:** Das Toffoli-Gate ist **universell für klassische Berechnung**. Du kannst damit jeden klassischen Schaltkreis bauen!

### CZ-Gate (Controlled-Z)

Mein Lieblings-2-Qubit-Gate (weil's symmetrisch ist):

```
CZ = [ 1  0  0   0 ]
     [ 0  1  0   0 ]
     [ 0  0  1   0 ]
     [ 0  0  0  -1 ]

CZ|00⟩ = |00⟩
CZ|01⟩ = |01⟩
CZ|10⟩ = |10⟩
CZ|11⟩ = -|11⟩   ← Nur hier ändert sich die Phase!
```

**Schaltkreis:**
```
──●──
  │
──●──

(Beide Qubits sind gleichberechtigt!)
```

---

## Unitäre Matrizen (wichtig!)

Nicht jede Matrix ist ein gültiges Quantengatter. Nur **unitäre** Matrizen sind erlaubt.

**Definition:** Eine Matrix U ist unitär, wenn U†U = UU† = I

**Warum?** Weil Quantenmechanik Wahrscheinlichkeiten erhält. Wenn du mit einem normierten Zustand startest, muss der Output auch normiert sein.

### Check: Ist Hadamard unitär?

```
H†H = 1/√2 [ 1   1 ] · 1/√2 [ 1   1 ]
           [ 1  -1 ]        [ 1  -1 ]

    = 1/2 [ 1+1    1-1  ]   = 1/2 [ 2  0 ]   = [ 1  0 ]  = I  ✓
          [ 1-1    1+1  ]         [ 0  2 ]     [ 0  1 ]
```

Yep, Hadamard ist unitär. Alles gut.

---

## Tensorprodukt (Multi-Qubit-Systeme)

Okay, ein Qubit ist cool. Aber die echte Power kommt von **mehreren Qubits zusammen**.

**Problem:** Wie beschreibe ich zwei Qubits mathematisch?

**Lösung:** Tensorprodukt (auch Kronecker-Produkt genannt), geschrieben als ⊗

### Beispiel: Zwei Qubits

Qubit A im Zustand |0⟩, Qubit B im Zustand |1⟩:

```
|0⟩ ⊗ |1⟩ = |01⟩
```

Wie berechnet man das? Jedes Element des ersten Vektors mal den gesamten zweiten Vektor:

```
[ 1 ]     [ 0 ]       [ 1·[ 0 ] ]       [ 0 ]
[ 0 ]  ⊗  [ 1 ]   =   [   [ 1 ] ]   =   [ 1 ]
                      [ 0·[ 0 ] ]       [ 0 ]
                      [   [ 1 ] ]       [ 0 ]
```

**Die vier Basiszustände für 2 Qubits:**

```
|00⟩ = [ 1 ]    |01⟩ = [ 0 ]    |10⟩ = [ 0 ]    |11⟩ = [ 0 ]
       [ 0 ]           [ 1 ]           [ 0 ]           [ 0 ]
       [ 0 ]           [ 0 ]           [ 1 ]           [ 0 ]
       [ 0 ]           [ 0 ]           [ 0 ]           [ 1 ]
```

**Exponentielle Explosion:** n Qubits brauchen einen Vektor mit 2ⁿ Einträgen. Bei 50 Qubits sind das über 1 Billiarde komplexe Zahlen. Deshalb sind Quantencomputer so schwer zu simulieren!

---

## Verschränkung (Entanglement)

DAS ist der Moment, wo Quantenmechanik wirklich weird wird.

**Definition:** Zwei Qubits sind **verschränkt**, wenn ihr gemeinsamer Zustand sich NICHT als Tensorprodukt einzelner Zustände schreiben lässt.

### Die Bell-Zustände (maximale Verschränkung)

Der berühmteste verschränkte Zustand:

```
|Φ+⟩ = 1/√2 (|00⟩ + |11⟩)

     = 1/√2 [ 1 ]
            [ 0 ]
            [ 0 ]
            [ 1 ]
```

**Warum ist das verschränkt?** Versuch mal, das als |a⟩ ⊗ |b⟩ zu schreiben:

```
(α|0⟩ + β|1⟩) ⊗ (γ|0⟩ + δ|1⟩) = αγ|00⟩ + αδ|01⟩ + βγ|10⟩ + βδ|11⟩
```

Für |Φ+⟩ bräuchten wir: 
- αγ = 1/√2
- αδ = 0  
- βγ = 0
- βδ = 1/√2

Aber wenn αδ = 0, dann ist α = 0 ODER δ = 0.
- Falls α = 0: dann ist αγ = 0 ≠ 1/√2 ❌
- Falls δ = 0: dann ist βδ = 0 ≠ 1/√2 ❌

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

### Wie erzeugt man einen Bell-Zustand?

```
Schaltkreis:

|0⟩ ──[H]──●──  →  |Φ+⟩ = 1/√2 (|00⟩ + |11⟩)
           │
|0⟩ ───────⊕──
```

**Schritt für Schritt:**

1. Start: |00⟩

2. Hadamard auf Qubit 1:
   ```
   H|0⟩ ⊗ |0⟩ = 1/√2 (|0⟩ + |1⟩) ⊗ |0⟩ = 1/√2 (|00⟩ + |10⟩)
   ```

3. CNOT (Qubit 1 kontrolliert Qubit 2):
   ```
   CNOT · 1/√2 (|00⟩ + |10⟩) = 1/√2 (|00⟩ + |11⟩) = |Φ+⟩
   ```

Boom. Verschränkung erzeugt! 🎉

---

## Die Messungspostulate

Okay, ich hab lange um dieses Thema herumgetanzt. Aber Messung ist fundamental.

### Was passiert bei einer Messung?

**Vor der Messung:** Qubit ist in Superposition |ψ⟩ = α|0⟩ + β|1⟩

**Nach der Messung:** Qubit ist entweder |0⟩ ODER |1⟩

**Wahrscheinlichkeiten:**
- P(Ergebnis 0) = |α|²
- P(Ergebnis 1) = |β|²

### Beispiel mit echten Zahlen

```
Zustand: |ψ⟩ = 1/√3 |0⟩ + √(2/3) |1⟩
```

**Check:** Ist das normiert?

```
|1/√3|² + |√(2/3)|² = 1/3 + 2/3 = 1  ✓
```

**Messwahrscheinlichkeiten:**
- P(0) = 1/3 ≈ 33.3%
- P(1) = 2/3 ≈ 66.7%

**Nach der Messung:**
- Wenn wir 0 messen: Zustand kollabiert zu |0⟩
- Wenn wir 1 messen: Zustand kollabiert zu |1⟩

Die Superposition ist **zerstört**. Irreversibel. Das ist der "Kollaps der Wellenfunktion".

---

# Teil III: Die Algorithmen (aka "Jetzt wird's spannend")

## Der Deutsch-Jozsa Algorithmus

Mein erster "richtiger" Quantenalgorithmus! Er ist nicht praktisch nützlich, aber er zeigt perfekt, warum Quantencomputer cool sind.

### Das Problem

Du hast eine Black-Box-Funktion f: {0,1}ⁿ → {0,1}

Die Funktion ist **entweder:**
1. **Konstant:** f(x) = 0 für alle x, ODER f(x) = 1 für alle x
2. **Balanciert:** Genau die Hälfte der Inputs gibt 0, die andere Hälfte 1

**Aufgabe:** Finde heraus, welcher Typ!

### Klassisch vs. Quantum

**Klassisch:** Im schlimmsten Fall musst du 2ⁿ⁻¹ + 1 Inputs testen.

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

**Ergebnis:**
- Messung = 0 → f ist konstant
- Messung = 1 → f ist balanciert

**Eine Messung.** Das ist der Quantum Speedup.

---

## Grover's Suchalgorithmus

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

Wir suchen |11⟩ in der "Datenbank" {|00⟩, |01⟩, |10⟩, |11⟩}.

**Anzahl Iterationen:** ⌊(π/4)√4⌋ = ⌊π/2⌋ = 1

**Schritt 1: Initialisierung + Hadamard**

```
|ψ₀⟩ = H⊗H |00⟩ = 1/2 (|00⟩ + |01⟩ + |10⟩ + |11⟩)
```

Alle Amplituden sind 1/2.

**Schritt 2: Orakel (markiert |11⟩)**

Das Orakel flippt die Phase von |11⟩:

```
Uf = [ 1  0  0   0 ]
     [ 0  1  0   0 ]
     [ 0  0  1   0 ]
     [ 0  0  0  -1 ]

Uf|ψ₀⟩ = 1/2 (|00⟩ + |01⟩ + |10⟩ - |11⟩)
```

Jetzt hat |11⟩ die Amplitude -1/2.

**Schritt 3: Diffusor (Verstärkung)**

Der Diffusor ist D = 2|ψ₀⟩⟨ψ₀| - I

Das ist eine Reflexion am Durchschnitt. Effektiv:
- Berechne den Durchschnitt aller Amplituden
- Reflektiere jede Amplitude an diesem Durchschnitt

```
Durchschnitt: ā = 1/4 · (1/2 + 1/2 + 1/2 - 1/2) = 1/4

Neue Amplituden (Formel: 2ā - alte_amplitude):
  |00⟩: 2·(1/4) - 1/2  = 0
  |01⟩: 2·(1/4) - 1/2  = 0
  |10⟩: 2·(1/4) - 1/2  = 0
  |11⟩: 2·(1/4) - (-1/2) = 1
```

**Endzustand:**

```
|ψ_final⟩ = |11⟩
```

**Messung:** 100% Wahrscheinlichkeit für |11⟩! 🎯

---

## Shor's Algorithmus (der große Boss)

Das ist der Algorithmus, der RSA-Verschlüsselung brechen könnte. Deshalb investieren Regierungen Milliarden in Quantencomputer (und in Post-Quantum-Kryptographie).

### Das Problem: Faktorisierung

Gegeben: Eine große Zahl N = p · q (Produkt zweier Primzahlen)
Gesucht: Die Faktoren p und q

**Beispiel:** N = 15 → Faktoren sind 3 und 5

Klingt einfach? Bei einer 2048-Bit-Zahl (wie in RSA) wäre klassische Faktorisierung praktisch unmöglich.

### Die Grundidee

Shor hat erkannt: Faktorisierung kann auf **Periodenfindung** reduziert werden. Und Quantencomputer sind verdammt gut darin, Perioden zu finden.

**Der Trick:**

1. Wähle zufälliges a < N mit gcd(a, N) = 1
2. Finde die Periode r von f(x) = aˣ mod N
3. Wenn r gerade und a^(r/2) ≢ -1 mod N:
   - gcd(a^(r/2) - 1, N) ist ein Faktor!
   - gcd(a^(r/2) + 1, N) ist der andere!

### Durchgerechnetes Beispiel: N = 15

Wir faktorisieren N = 15. Wählen wir a = 7.

**Schritt 1: Periodenfindung**

Berechne 7ˣ mod 15 für verschiedene x:

| x | 7ˣ | 7ˣ mod 15 |
|---|-----|-----------|
| 1 | 7 | 7 |
| 2 | 49 | 4 |
| 3 | 343 | 13 |
| 4 | 2401 | 1 |
| 5 | 16807 | 7 |

Die Sequenz wiederholt sich! Periode r = 4.

**(Hier würde der Quantencomputer die Quanten-Fourier-Transformation nutzen, um r effizient zu finden)**

**Schritt 2: Faktoren berechnen**

r = 4 ist gerade ✓

```
a^(r/2) = 7² = 49

a^(r/2) - 1 = 49 - 1 = 48
a^(r/2) + 1 = 49 + 1 = 50

gcd(48, 15) = 3  ✓
gcd(50, 15) = 5  ✓
```

**Ergebnis:** 15 = 3 × 5 🎉

### Die Quanten-Fourier-Transformation (QFT)

Das Herzstück von Shor. Die QFT transformiert einen Zustand so, dass periodische Strukturen sichtbar werden.

```
QFT|x⟩ = 1/√N · Σₖ e^(2πixk/N) |k⟩
```

Das ist die Quanten-Version der diskreten Fourier-Transformation — aber exponentiell schneller berechenbar!

---

## Quanten-Fehlerkorrektur

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

### Der "Below Threshold" Durchbruch

Ein Meilenstein in der Fehlerkorrektur ist das Erreichen des **Error Correction Threshold**:

```
OBERHALB der Schwelle:
━━━━━━━━━━━━━━━━━━━━━━
Mehr Qubits → Mehr Fehler → System wird SCHLECHTER
Das war der Stand bis 2024.

UNTERHALB der Schwelle:
━━━━━━━━━━━━━━━━━━━━━━
Mehr Qubits → Mehr Korrektur → System wird BESSER!
Das ist der heilige Gral — und Google hat ihn erreicht.
```

---

# Teil IV: Machine Learning meets Quantum (🔥 Das nächste große Ding)

## Warum ML + Quantum?

Ich bin kürzlich auf ein Buch gestoßen, das mich völlig umgehauen hat: **"Machine Learning in Quantum Sciences"** von Anna Dawid et al. (Cambridge University Press, 2025). Das Buch hat 29 Autoren aus über 10 Ländern — das zeigt, wie interdisziplinär dieses Feld ist.

> *"Machine learning knowledge will be just as valuable as knowing about differential equations and linear algebra"*  
> — Jesse Thaler, MIT

Das hat mich zum Nachdenken gebracht: ML ist nicht nur ein Tool für Quantenphysiker — es wird zur **Grundsprache** der modernen Quantenforschung.

### Die Hauptanwendungsgebiete

```
┌─────────────────────────────────────────────────────────────┐
│              ML + QUANTUM: DIE 6 HAUPTFELDER                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  1. Quantum State Tomography                                │
│     → Neuronale Netze rekonstruieren Quantenzustände        │
│     → 98% Fidelity mit WENIGER Messungen!                   │
│                                                             │
│  2. Variational Quantum Algorithms (VQA)                    │
│     → ML optimiert Quantenschaltkreise                      │
│     → Löst das "Barren Plateau" Problem                     │
│                                                             │
│  3. Quantum Error Correction                                │
│     → AlphaQubit: Transformer für Fehlerkorrektur           │
│     → 30% bessere Performance als klassische Methoden       │
│                                                             │
│  4. Neural-Network Quantum States (NQS)                     │
│     → Neuronale Netze ALS Wellenfunktionen                  │
│     → Bis zu 10⁶ Parameter trainierbar!                     │
│                                                             │
│  5. Phase Classification                                    │
│     → Deep Learning erkennt Quantenphasenübergänge          │
│     → Funktioniert ohne vorherige Kenntnis des Systems      │
│                                                             │
│  6. Quantum Control                                         │
│     → Reinforcement Learning für Pulssequenzen              │
│     → Optimale Steuerung von echten Quantenprozessoren      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## Neural-Network Quantum States (NQS)

Das ist für mich das mind-blowing Konzept: **Was wenn das neuronale Netz selbst die Wellenfunktion IST?**

```
Klassische Simulation:
|ψ⟩ = Vektor mit 2ⁿ komplexen Zahlen  →  Exponentieller Speicher!

NQS Ansatz:
|ψ⟩ ≈ f_θ(x)  →  Neuronales Netz mit θ Parametern

Vorteil: θ kann VIEL kleiner sein als 2ⁿ
         und trotzdem physikalisch relevante Zustände beschreiben!
```

Giuseppe Carleo (EPFL, einer der Buchautoren) hat das Feld quasi erfunden. Der neueste Durchbruch: **Foundation Neural-Network Quantum States (FNQS)** — inspiriert von Large Language Models, aber für Quantenzustände. Ein einziges vortrainiertes Modell kann verschiedene Hamiltonians verarbeiten!

## Quantum State Tomography mit CNNs

**Das Problem:** Um einen Quantenzustand vollständig zu rekonstruieren, brauchst du exponentiell viele Messungen.

**ML-Lösung:** Convolutional Neural Networks können aus WENIGER Messungen den Zustand rekonstruieren:

```
Traditionell:                    Mit ML:
─────────────                    ────────
2ⁿ Messungen                     Polynomiell viele Messungen
     ↓                                ↓
Statistische                     CNN lernt die Struktur
Rekonstruktion                        ↓
     ↓                           Rekonstruiert fehlende Info
Langsam, ungenau                      ↓
                                 98% Fidelity!
```

### Warum das für NISQ wichtig ist

NISQ = Noisy Intermediate-Scale Quantum — das sind die 50-100+ Qubit Prozessoren die wir HEUTE haben (Google Willow, IBM Heron).

**Das Problem:** Diese Geräte sind verrauscht. Klassische Fehlerkorrektur braucht zu viele Qubits.

**Die Hoffnung:** ML kann mit dem Rauschen umgehen:
- Lernt Noise-Patterns
- Kompensiert systematische Fehler  
- Ermöglicht nützliche Berechnungen BEVOR wir fault-tolerante QCs haben

---

# Teil V: Hardware & Aktuelle Entwicklungen (2024/2025)

## Google Willow — Der Durchbruch bei der Fehlerkorrektur (Dezember 2024)

Am 9. Dezember 2024 hat Google seinen **Willow-Chip** vorgestellt, und die Quantum Computing Welt ist ausgeflippt. Zurecht.

### Die zwei großen Achievements

**1. Below-Threshold Error Correction** 🏆

Das ist der heilige Gral seit Peter Shor 1995 die Fehlerkorrektur eingeführt hat:

```
Willow's Durchbruch:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Surface Code Größe:     3×3  →  5×5  →  7×7
Fehlerrate:             ████    ██     █
                        hoch    halb   viertel

Bei jeder Verdopplung der Gittergröße: Fehlerrate HALBIERT sich!

Das ist EXPONENTIELLES Fehlersuppression — genau das,
was wir für skalierbare Quantencomputer brauchen.
```

**2. Random Circuit Sampling Benchmark**

Willow hat eine RCS-Berechnung in unter 5 Minuten durchgeführt, die auf dem schnellsten Supercomputer der Welt (Frontier) **10²⁵ Jahre** dauern würde.

Zum Vergleich: Das Universum ist ~1.4 × 10¹⁰ Jahre alt.

### Willow Specs

| Metrik | Wert |
|--------|------|
| Qubits | 105 |
| T1 Kohärenzzeit | ~100 µs (5× besser als Sycamore) |
| 2-Qubit Gate Error | 0.33% ± 0.18% |
| Error Correction Cycles/sec | 909.000 |
| Connectivity | 3.47 (4-way typical) |

### Was das bedeutet (und was nicht)

**Was es bedeutet:**
- ✅ Skalierbare Fehlerkorrektur ist MÖGLICH
- ✅ Die Roadmap zu fault-toleranten QCs ist realistisch
- ✅ Google liegt bei Surface Codes vorne

**Was es NICHT bedeutet:**
- ❌ Wir haben jetzt "nützliche" Quantencomputer
- ❌ RSA ist geknackt (Google sagt selbst: noch ~10 Jahre)
- ❌ Praktische Algorithmen laufen schon

> **Hartmut Neven (Google Quantum AI):** "Willow lends credence to the notion that quantum computation occurs in many parallel universes..."

Das hat für einige Kontroverse gesorgt. Multiverse-Hype oder nicht — der technische Durchbruch ist real.

---

## IBM's Roadmap — Condor, Heron und darüber hinaus

IBM verfolgt einen anderen Ansatz als Google: **Modularität und klassische Integration**.

### Die aktuelle Fleet (Januar 2025)

| Prozessor | Qubits | Status |
|-----------|--------|--------|
| Eagle | 127 | Produktion |
| Heron r1 | 133 | Produktion (ibm_torino) |
| Heron r2 | 156 | Produktion (ibm_fez) |
| Condor | 1.121 | Demo/Forschung |

### Die Roadmap bis 2033

```
2024  ────────────────────────────────────────────────────►
      Heron (133-156 Qubits)
      └── 5.000 Gates möglich
      └── Tunable Couplers (kein Crosstalk!)

2025  ────────────────────────────────────────────────────►
      Flamingo (462 Qubits) + Kookaburra (1.386 Qubits)
      └── Quantum Communication Links
      └── 3× Kookaburra = 4.158 Qubits!

2029  ────────────────────────────────────────────────────►
      Starling
      └── 100 MILLIONEN Gates
      └── 200+ Qubits mit Fehlerkorrektur
      └── Gross Code (neuer Error Correction Ansatz)

2033  ────────────────────────────────────────────────────►
      Blue Jay
      └── 1 MILLIARDE Gates
      └── 2.000+ Qubits
      └── Echte Fault Tolerance
```

### IBM's Philosophie: Quantum-Centric Supercomputing

IBM will Quantenprozessoren nicht als standalone-Geräte, sondern als **Beschleuniger in klassischen Supercomputern** einsetzen:

```
┌──────────────────────────────────────────────────────────┐
│                  QUANTUM-CENTRIC SUPERCOMPUTER           │
├──────────────────────────────────────────────────────────┤
│                                                          │
│   ┌─────────┐    ┌─────────┐    ┌─────────┐             │
│   │  CPU    │────│  GPU    │────│  QPU    │             │
│   │ Cluster │    │ Cluster │    │ Cluster │             │
│   └─────────┘    └─────────┘    └─────────┘             │
│        │              │              │                   │
│        └──────────────┴──────────────┘                   │
│                       │                                  │
│              [ Qiskit Runtime ]                          │
│                       │                                  │
│        Automatische Workload-Verteilung                  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

## Der Wettlauf der Giganten

Nicht nur Google und IBM sind im Rennen:

| Company | Technologie | Qubits (2025) | Besonderheit |
|---------|-------------|---------------|--------------|
| **Google** | Superconducting | 105 (Willow) | Below-threshold QEC |
| **IBM** | Superconducting | 1.121 (Condor) | Modular, Production-ready |
| **IonQ** | Trapped Ions | 32 (Forte) | Höchste Gate Fidelity |
| **Quantinuum** | Trapped Ions | 56 (H2) | Niedrigste Fehlerrate |
| **Microsoft** | Topological (geplant) | 0 (noch) | Theoretisch fehlerresistent |
| **Amazon** | Diverse (Braket) | - | Cloud-Plattform für alle |
| **China** | Superconducting + Photonic | 66+ (Zuchongzhi) | Staatlich gefördert |

### Ionenfallen vs. Supraleitende Qubits

```
Supraleitende Qubits (Google, IBM):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
+ Schnelle Gates (~10-100 ns)
+ Gut skalierbar (mehr Qubits)
+ Etablierte Fab-Prozesse
- Kurze Kohärenzzeiten (~100 µs)
- Braucht Millikelvin-Kühlung
- Crosstalk-Probleme

Ionenfallen (IonQ, Quantinuum):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
+ Lange Kohärenzzeiten (~Sekunden!)
+ Höchste Gate-Fidelity (>99.9%)
+ All-to-All Connectivity
- Langsame Gates (~10-100 µs)
- Schwerer zu skalieren
- Komplexe Lasersteuerung
```

---

## NISQ vs. Fault-Tolerant — Wo stehen wir wirklich?

Lass mich ehrlich sein: Es gibt viel Hype. Hier ist die Realität:

### Die NISQ-Ära (jetzt)

**NISQ** = Noisy Intermediate-Scale Quantum

```
Charakteristik:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• 50-1000+ physische Qubits
• Fehlerraten: ~0.1-1% pro Gate
• Keine vollständige Fehlerkorrektur
• Begrenzte Schaltkreistiefe (~100-1000 Gates)
• Experimentell, nicht produktiv
```

**Was NISQ kann:**
- Quantum Machine Learning Experimente
- Variational Algorithms (VQE, QAOA)
- Quantum Simulation (kleine Moleküle)
- Benchmarking & Forschung

**Was NISQ NICHT kann:**
- Shor's Algorithmus auf RSA-Zahlen
- Grover auf große Datenbanken
- Praktisch relevante Optimierung
- Alles was viele Gates braucht

### Fault-Tolerant Quantum Computing (Ziel)

```
Anforderungen:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
• Millionen logische Gates
• Fehlerrate < 10⁻¹² pro Gate
• ~1000-10000 physische Qubits pro logischem Qubit
• Real-time Fehlerkorrektur

Timeline (optimistisch):
• 2029: Erste Demos (IBM Starling)
• 2033: Produktionssysteme (IBM Blue Jay)
• 2035+: Praktischer Nutzen
```

### Die ehrliche Einschätzung

| Anwendung | NISQ möglich? | Wann produktiv? |
|-----------|---------------|-----------------|
| RSA knacken | ❌ | 2035-2040+ |
| Medikamentenentwicklung | 🟡 Begrenzt | 2030+ |
| Finanzen/Optimierung | 🟡 Hybride Ansätze | 2028+ |
| ML-Beschleunigung | 🟡 Experimentell | 2027+ |
| Kryptographie | ✅ QKD funktioniert | Jetzt |

---

# Teil VI: Post-Quantum Kryptographie

## Das Problem: Shor bedroht alles

Okay, das ist wichtig. Shor's Algorithmus kann:
- RSA brechen
- Elliptic Curve Cryptography (ECC) brechen
- Diffie-Hellman Key Exchange brechen

Das ist quasi **alles** was wir heute für sichere Kommunikation nutzen.

```
Aktuelle Verschlüsselung:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Du  ──[RSA/ECC]──▶  Bank  ──[RSA/ECC]──▶  Server

          │                    │
          ▼                    ▼
    Basiert auf:          Basiert auf:
    - Faktorisierung      - Diskrete Logarithmen
    - Elliptic Curves     - Elliptic Curves

          │                    │
          └────────┬───────────┘
                   │
                   ▼
           SHOR KANN DAS KNACKEN
```

**"Harvest Now, Decrypt Later":** Geheimdienste könnten JETZT verschlüsselte Daten sammeln und SPÄTER (wenn QCs existieren) entschlüsseln. Das ist keine Paranoia, das ist dokumentiert.

---

## NIST's neue Standards (August 2024)

Nach 8 Jahren Evaluation hat NIST am 13. August 2024 die ersten **Post-Quantum Cryptography Standards** veröffentlicht:

| Standard | Algorithmus | Typ | Basiert auf |
|----------|-------------|-----|-------------|
| **FIPS 203** | ML-KEM (ex Kyber) | Key Encapsulation | Lattices |
| **FIPS 204** | ML-DSA (ex Dilithium) | Digital Signature | Lattices |
| **FIPS 205** | SLH-DSA (ex SPHINCS+) | Digital Signature | Hashes |
| FIPS 206 (Draft) | FN-DSA (ex FALCON) | Digital Signature | Lattices |

**Plus Backup (März 2025):**
- **HQC** — Code-basierter KEM als Alternative zu ML-KEM

---

## Die neuen Algorithmen erklärt

### ML-KEM (Module-Lattice-Based Key-Encapsulation Mechanism)

Der neue Standard für **Schlüsselaustausch**.

```
Das Lattice-Problem (vereinfacht):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Stell dir ein Gitter in vielen Dimensionen vor:

    •     •     •     •     •
      •     •     •     •
    •     •     •     •     •
      •     •     •     •
    •     •     •     •     •

Problem: Finde den kürzesten Vektor
         oder den nächsten Gitterpunkt zu einem Punkt.

In 2D: Einfach
In 1000D: Selbst für Quantencomputer SCHWER!
```

**Warum Lattices?**
- Mathematisch gut verstanden
- Effizient zu implementieren
- Keine bekannten Quantum-Angriffe

### ML-DSA (Module-Lattice-Based Digital Signature)

Für **digitale Signaturen** — beweist, dass eine Nachricht wirklich von dir kommt.

```
Klassisch (RSA):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Signatur = Nachricht^d mod n
           └── Basiert auf Faktorisierung

Post-Quantum (ML-DSA):
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Signatur = f(Nachricht, Lattice-Secret)
           └── Basiert auf Lattice-Probleme
```

### SLH-DSA (Stateless Hash-Based Digital Signature)

Ein **Backup** für ML-DSA, falls Lattice-Kryptographie doch gebrochen wird:

- Basiert NUR auf Hash-Funktionen
- Mathematisch sehr konservativ
- Größere Signaturen, aber maximale Sicherheit

---

## Was bedeutet das für dich?

### Als Entwickler

```
JETZT:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
1. Inventarisiere wo du Krypto nutzt
2. Priorisiere nach Datensensitivität
3. Plane Migration auf PQC

TIMELINE:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
2024-2025: Standards finalisiert ✅
2025-2027: Libraries werden reif
2027-2030: Breite Adoption erwartet
2030+:     Alte Algorithmen deprecated
```

### Konkrete Schritte

1. **TLS 1.3 mit Hybrid-Mode:** Kombiniert klassisch + PQC
2. **Libraries updaten:** OpenSSL 3.x unterstützt bereits PQC
3. **Key Sizes anpassen:** ML-KEM Keys sind größer
4. **Performance testen:** PQC ist schneller als klassische Krypto!

### Fun Fact

> ML-KEM ist tatsächlich **effizienter** als RSA oder ECC! Die Lattice-Operationen sind schneller als modulare Exponentation.

---

# Teil VII: Meine Projekte & Ressourcen

## 🔬 RCS Benchmark (dieses Repo!)

Ich baue einen **Random Circuit Sampling** Simulator in Rust. Das ist genau die Aufgabe, mit der Google 2019 "Quantum Supremacy" demonstriert hat.

**Was der Simulator macht:**
1. Generiert zufällige Quantenschaltkreise
2. Simuliert sie klassisch (State Vector)
3. Berechnet den XEB-Score (Cross-Entropy Benchmark)

**Warum?** Um zu verstehen, wie man Quantencomputer benchmarkt. Und um Rust zu üben. Win-Win.

[→ Zum RCS Benchmark Code](/src)

---

## Ressourcen, die mir geholfen haben

### Bücher

1. **"Quantum Computation and Quantum Information"** — Nielsen & Chuang
   - DAS Standardwerk. Dick. Mathematisch. Aber gut.

2. **"Quantum Computing: An Applied Approach"** — Hidary
   - Moderner, mehr Code-Beispiele. Empfehlenswert!

3. **"Programming Quantum Computers"** — Gimeno-Segovia et al.
   - Praktischer Fokus. Gut für den Einstieg.

4. **"Machine Learning in Quantum Sciences"** — Dawid, Arnold, Requena, Gresch et al. (Cambridge, 2025) 🆕
   - DAS Buch für ML + Quantum. 29 Autoren, 9 Kapitel, 330 Seiten.
   - Deckt ab: Deep Learning, Kernel Methods, Reinforcement Learning für Quantensysteme
   - Lead-Autorin Anna Dawid (Leiden University) hat auch mit Yann LeCun publiziert!
   - Senior-Autoren: Maciej Lewenstein (ICFO, 800+ Papers), Giuseppe Carleo (EPFL, NQS-Pionier)
   - **Bewertung:** *"A fantastic overview of an emerging research landscape"* — Maria Schuld (Xanadu)
   - [Cambridge Link](https://www.cambridge.org/core/books/machine-learning-in-quantum-sciences/B8CD17DBEC814E98C522532BECF60BE7)

### Online-Kurse

- [IBM Qiskit Textbook](https://qiskit.org/textbook/) — Kostenlos, interaktiv, sehr gut!
- [Brilliant.org Quantum Computing](https://brilliant.org/) — Für Visualisierungen
- [edX: Quantum Computing Fundamentals](https://www.edx.org/) — MIT-Kurs, anspruchsvoll

### YouTube-Kanäle

- **3Blue1Brown** — Für lineare Algebra Intuition
- **Looking Glass Universe** — Quantenmechanik erklärt
- **Qiskit** — Offizielle Tutorials

### Papers (aktualisiert 2025)

- [Google Willow Nature Paper (2024)](https://www.nature.com/articles/s41586-024-08448-z) — Below-threshold QEC
- [Google Quantum Supremacy Paper (Nature 2019)](https://www.nature.com/articles/s41586-019-1666-5)
- [Shor's Original Paper](https://arxiv.org/abs/quant-ph/9508027)
- [Grover's Original Paper](https://arxiv.org/abs/quant-ph/9605043)
- [AlphaQubit: ML für Quantum Error Correction (Nature 2024)](https://www.nature.com/articles/s41586-024-08148-8)
- [Modern applications of ML in quantum sciences (arXiv:2204.04198)](https://arxiv.org/abs/2204.04198) — Preprint zum Buch
- [NIST Post-Quantum Cryptography Standards (2024)](https://csrc.nist.gov/projects/post-quantum-cryptography)

---

## Offene Fragen (die mich nachts wachhalten)

1. **Was IST Messung eigentlich?** Warum kollabiert die Wellenfunktion? Ist es wirklich zufällig?

2. **Many-Worlds vs. Copenhagen:** Sind das nur Interpretationen oder gibt's einen Unterschied?

3. **Wo ist die Grenze?** Ab wann ist ein System "klassisch"? Warum sehen wir keine Superpositionen im Alltag?

4. **Quantum Computing Hype:** Werden wir jemals *praktisch nützliche* Quantencomputer haben? Willow ist ein Meilenstein, aber wann kommt der Durchbruch für echte Anwendungen?

5. **ML + Quantum:** Werden neuronale Netze die klassische Simulation von Quantensystemen obsolet machen? Oder ist das nur ein Hype?

6. **Post-Quantum Migration:** Werden wir rechtzeitig fertig bevor "Harvest Now, Decrypt Later" zum Problem wird?

7. **Was macht Bewusstsein?** (Okay, das ist Philosophie, aber die Quantenleute haben mich angesteckt...)

---

## Timeline: Wichtige Meilensteine

```
1994  ─── Shor's Algorithmus veröffentlicht
1995  ─── Erste Fehlerkorrektur-Codes (Shor, Steane)
1996  ─── Grover's Suchalgorithmus
2001  ─── Erste Demonstration: Shor auf 15 (7 Qubits, IBM)
2016  ─── IBM Quantum Experience (5 Qubits öffentlich)
2019  ─── Google "Quantum Supremacy" (Sycamore, 53 Qubits)
2023  ─── IBM Condor (1.121 Qubits)
2024  ─── Google Willow: Below-threshold QEC! ← WE ARE HERE
2024  ─── NIST Post-Quantum Standards finalisiert
2029  ─── IBM Starling: 100M Gates (geplant)
2033  ─── IBM Blue Jay: 1B Gates (geplant)
????  ─── Praktischer Quantenvorteil für reale Probleme
```

---

*"The universe is not only queerer than we suppose, but queerer than we CAN suppose."*  
— J.B.S. Haldane

---

**Lizenz:** MIT (für den Code) / CC BY-SA (für den Text)

**Letztes Update:** Januar 2025