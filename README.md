# Quantenmechanik - Mein Gehirn schmilzt

## 1. März - Das Doppelspalt-Experiment

Holy shit. Ich hab heute das Doppelspalt-Experiment verstanden. Naja, *"verstanden"* ist übertrieben. Ich akzeptiere es einfach.

> **Idee:** Elektronen verhalten sich wie Wellen... bis man hinschaut. Dann sind sie Teilchen. WTF?!

```
Elektronenquelle → Doppelspalt → Schirm
     [e⁻]            ‖ ‖         Interferenzmuster!
                   (Wellen)
```

Aber jetzt kommt's: Wenn man einen Detektor hinpackt...

```
Elektronenquelle → Doppelspalt → Detektor → Schirm  
     [e⁻]            ‖ ‖         👁️         Nur 2 Streifen!
                  (Teilchen)
```

Das Elektron *"weiß"* dass wir hinschauen und benimmt sich anders! 🤯

## 3. März - Schrödingers Katze (armes Tier)

Die berühmte Katze! Endlich verstehe ich worum's geht:

> **Notiz:** Katze in Box + Giftflasche + Quantentrigger = Katze ist tot UND lebendig
> Erst wenn man nachschaut, "entscheidet" sich das Universum

```
Schrödingers Box:
[☢ 50% Zerfall] → [Hammer] → [☠ Gift] → [🐱 = |🐱⟩ + |💀⟩]
```

# Mathematik des Quantum Computing

## 1. Einführung

Quantencomputing ist ein aufstrebendes Paradigma, das die Prinzipien der Quantenmechanik nutzt, um Berechnungen auf eine Weise durchzuführen, die über die Fähigkeiten klassischer Computer hinausgeht. Während klassische Computer Informationen als Bits speichern, die entweder 0 oder 1 sein können, verwenden Quantencomputer Qubits, die gleichzeitig 0, 1 oder eine Superposition von beidem sein können. Diese einzigartige Eigenschaft, zusammen mit Phänomenen wie Superposition und Verschränkung, ermöglicht es Quantencomputern, bestimmte komplexe Probleme exponentiell schneller zu lösen als ihre klassischen Gegenstücke.

Die zugrunde liegende Leistungsfähigkeit des Quantencomputings ist tief in der Mathematik verwurzelt. Ohne ein solides Verständnis der mathematischen Konzepte, die die Quantenmechanik und das Quantencomputing untermauern, ist es nahezu unmöglich, die Funktionsweise dieser revolutionären Technologie vollständig zu erfassen. Insbesondere die lineare Algebra bildet das Rückgrat der Quanteninformationstheorie und ist unerlässlich, um die Zustände von Qubits, die Operationen von Quantengattern und die Dynamik von Quantenalgorithmen zu beschreiben und zu manipulieren. Dieses Kapitel wird eine detaillierte Einführung in die mathematischen Grundlagen des Quantencomputings geben, angereichert mit zahlreichen rechnerischen Beispielen, um das Verständnis zu vertiefen und die praktische Anwendung der Konzepte zu veranschaulichen.



## 2. Mathematische Grundlagen

### 2.1 Lineare Algebra

Die lineare Algebra ist die Sprache des Quantencomputings. Sie bietet den notwendigen Rahmen, um die Zustände von Quantensystemen und die Operationen, die auf ihnen ausgeführt werden, zu beschreiben. Im Kern des Quantencomputings stehen Vektoren und Matrizen, die komplexe Zahlen enthalten können.

#### Vektoren und Matrizen

Ein **Vektor** in der linearen Algebra kann als eine geordnete Liste von Zahlen betrachtet werden. Im Kontext des Quantencomputings repräsentieren Vektoren die Zustände von Qubits. Ein Spaltenvektor $v$ der Dimension $n$ ist eine Sammlung von $n$ komplexen Zahlen $(v_1, v_2, \dots, v_n)$, die als Spalte angeordnet sind:

$$v = \begin{pmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{pmatrix}$$

Die **Norm** eines Vektors $v$ ist definiert als $\sqrt{\sum_i |v_i|^2}$. Ein Vektor wird als **Einheitsvektor** bezeichnet, wenn seine Norm 1 ist. Dies ist besonders wichtig im Quantencomputing, da Quantenzustände immer durch Einheitsvektoren repräsentiert werden.

Das **Adjunkt** (oder konjugiert Transponierte) eines Spaltenvektors $v$ ist ein Zeilenvektor, der als $v^\dagger$ bezeichnet wird und als die konjugierte Transponierte von $v$ definiert ist. Für einen Spaltenvektor $v$ der Dimension $n$ ist das Adjunkt ein Zeilenvektor der Dimension $1 \times n$:

$$v^\dagger = \begin{pmatrix} v_1^* & v_2^* & \dots & v_n^* \end{pmatrix}$$

wobei $v_i^*$ die komplex Konjugierte von $v_i$ bezeichnet.

**Beispiel 2.1.1: Norm eines Vektors**

Betrachten Sie den Vektor $v = \begin{pmatrix} 3+4i \\ 1-2i \end{pmatrix}$.

Die Norm von $v$ ist:

$$||v|| = \sqrt{|3+4i|^2 + |1-2i|^2}$$

$$|3+4i|^2 = 3^2 + 4^2 = 9 + 16 = 25$$

$$|1-2i|^2 = 1^2 + (-2)^2 = 1 + 4 = 5$$

$$||v|| = \sqrt{25 + 5} = \sqrt{30}$$

Eine **Matrix** der Größe $m \times n$ ist eine Sammlung von $m \cdot n$ komplexen Zahlen, die in $m$ Zeilen und $n$ Spalten angeordnet sind:

$$M = \begin{pmatrix} M_{11} & M_{12} & \dots & M_{1n} \\ M_{21} & M_{22} & \dots & M_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ M_{m1} & M_{m2} & \dots & M_{mn} \end{pmatrix}$$

Im Quantencomputing werden Quantenoperationen durch **quadratische Matrizen** dargestellt, d.h. die Anzahl der Zeilen und Spalten ist gleich. Zum Beispiel werden Einzel-Qubit-Operationen durch $2 \times 2$-Matrizen dargestellt.

#### Skalarprodukt

Zwei Vektoren können durch das **Skalarprodukt** (auch Punktprodukt oder inneres Produkt genannt) miteinander multipliziert werden. Das Ergebnis des Skalarprodukts zweier Vektoren ist ein Skalar. Das Skalarprodukt zwischen zwei Spaltenvektoren $u$ und $v$ wird als $\langle u,v \rangle = u^\dagger v$ bezeichnet und ist definiert als:

$$\langle u,v \rangle = u^\dagger v = \begin{pmatrix} u_1^* & \dots & u_n^* \end{pmatrix} \begin{pmatrix} v_1 \\ \vdots \\ v_n \end{pmatrix} = u_1^*v_1 + \dots + u_n^*v_n$$

Mit dem Skalarprodukt kann die Norm eines Vektors $v$ als $\sqrt{\langle v,v \rangle}$ geschrieben werden.

**Beispiel 2.1.2: Skalarprodukt**

Betrachten Sie die Vektoren $u = \begin{pmatrix} 1+i \\ 2-i \end{pmatrix}$ und $v = \begin{pmatrix} 3-2i \\ 4+i \end{pmatrix}$.

Zuerst berechnen wir $u^\dagger$:

$$u^\dagger = \begin{pmatrix} 1-i & 2+i \end{pmatrix}$$

Nun das Skalarprodukt:

$$\langle u,v \rangle = (1-i)(3-2i) + (2+i)(4+i)$$

$$= (3 - 2i - 3i + 2i^2) + (8 + 2i + 4i + i^2)$$

$$= (3 - 5i - 2) + (8 + 6i - 1)$$

$$= (1 - 5i) + (7 + 6i)$$

$$= 8 + i$$

#### Matrixmultiplikation

Eine Matrix $M$ der Dimension $m \times n$ und eine Matrix $N$ der Dimension $n \times p$ können multipliziert werden, um eine neue Matrix $P$ der Dimension $m \times p$ zu erhalten. Die Einträge von $P$ sind $P_{ik} = \sum_j M_{ij}N_{jk}$.

**Beispiel 2.1.3: Matrixmultiplikation**

Betrachten Sie die Matrizen $A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}$ und $B = \begin{pmatrix} 5 & 6 \\ 7 & 8 \end{pmatrix}$.

$$A \cdot B = \begin{pmatrix} (1)(5)+(2)(7) & (1)(6)+(2)(8) \\ (3)(5)+(4)(7) & (3)(6)+(4)(8) \end{pmatrix}$$

$$= \begin{pmatrix} 5+14 & 6+16 \\ 15+28 & 18+32 \end{pmatrix}$$

$$= \begin{pmatrix} 19 & 22 \\ 43 & 50 \end{pmatrix}$$

#### Spezielle Matrizen

Die **Identitätsmatrix** $I$ ist eine quadratische Matrix, deren Diagonalelemente 1 sind und alle anderen Elemente 0. Sie verhält sich wie die Zahl 1 in der Multiplikation:

$$I = \begin{pmatrix} 1 & 0 & \dots & 0 \\ 0 & 1 & \dots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \dots & 1 \end{pmatrix}$$

Eine Matrix $U$ ist **unitär**, wenn $UU^\dagger = U^\dagger U = I$ ist, oder äquivalent $U^{-1} = U^\dagger$. Unitäre Matrizen sind von entscheidender Bedeutung im Quantencomputing, da sie die Norm eines Vektors erhalten, was bedeutet, dass sie die Wahrscheinlichkeiten in einem Quantensystem nicht verändern. Quantenoperationen werden durch unitäre Matrizen dargestellt.

Eine Matrix $M$ wird als **Hermitesch** bezeichnet, wenn $M = M^\dagger$ ist. Hermitesche Matrizen sind wichtig für die Beschreibung von Messungen in der Quantenmechanik.

**Beispiel 2.1.4: Unitäre Matrix**

Das Hadamard-Gatter ist ein wichtiges Einzel-Qubit-Gatter, das durch die Matrix $H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$ dargestellt wird. Überprüfen wir, ob es unitär ist.

$$H^\dagger = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}^\dagger = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

$$H H^\dagger = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

$$= \frac{1}{2}\begin{pmatrix} (1)(1)+(1)(1) & (1)(1)+(1)(-1) \\ (1)(1)+(-1)(1) & (1)(1)+(-1)(-1) \end{pmatrix}$$

$$= \frac{1}{2}\begin{pmatrix} 1+1 & 1-1 \\ 1-1 & 1+1 \end{pmatrix}$$

$$= \frac{1}{2}\begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}$$

$$= \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$$

Da $H H^\dagger = I$ ist, ist das Hadamard-Gatter eine unitäre Matrix.



### 2.2 Hilbertraum

Der **Hilbertraum** ist ein zentrales mathematisches Konzept in der Quantenmechanik und damit auch im Quantencomputing. Formal ist ein Hilbertraum ein vollständiger innerer Produktraum, d.h. ein Vektorraum mit einem Skalarprodukt, der bezüglich der durch das Skalarprodukt induzierten Norm vollständig ist. Im Kontext des Quantencomputings repräsentiert der Hilbertraum den Zustandsraum eines Quantensystems.

Für ein einzelnes Qubit ist der Zustandsraum ein zweidimensionaler komplexer Hilbertraum, oft als $\mathbb{C}^2$ bezeichnet. Die Basisvektoren dieses Raumes sind die orthogonalen Zustände $|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ und $|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$. Jeder mögliche Zustand eines Qubits ist eine Linearkombination dieser Basisvektoren, also ein Vektor der Form $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$, wobei $\alpha$ und $\beta$ komplexe Zahlen sind und die Normierungsbedingung $|\alpha|^2 + |\beta|^2 = 1$ erfüllen müssen. Diese Bedingung stellt sicher, dass die Gesamtwahrscheinlichkeit, das Qubit in einem der Basiszustände zu finden, 1 ist.

Für ein System von $n$ Qubits ist der Zustandsraum ein $2^n$-dimensionaler komplexer Hilbertraum. Die Basisvektoren dieses Raumes sind die Tensorprodukte der Einzel-Qubit-Basiszustände. Zum Beispiel für zwei Qubits sind die Basiszustände $|00\rangle, |01\rangle, |10\rangle, |11\rangle$, die den Vektoren $\begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}$, $\begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}$, $\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}$, $\begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}$ entsprechen.

**Beispiel 2.2.1: Zustandsvektor im Hilbertraum**

Betrachten Sie ein Qubit im Zustand $|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{i}{\sqrt{2}}|1\rangle$. Dieser Zustand kann als Vektor im Hilbertraum $\mathbb{C}^2$ dargestellt werden:

$$|\psi\rangle = \begin{pmatrix} 1/\sqrt{2} \\ i/\sqrt{2} \end{pmatrix}$$

Überprüfen wir die Normierungsbedingung:

$$|\alpha|^2 + |\beta|^2 = |1/\sqrt{2}|^2 + |i/\sqrt{2}|^2 = (1/2) + (1/2) = 1$$

Dies bestätigt, dass $|\psi\rangle$ ein gültiger Quantenzustand ist. Die Koeffizienten $\alpha$ und $\beta$ repräsentieren die Wahrscheinlichkeitsamplituden, das Qubit im Zustand $|0\rangle$ bzw. $|1\rangle$ zu finden. Die Quadrate ihrer Beträge, $|\alpha|^2$ und $|\beta|^2$, geben die tatsächlichen Wahrscheinlichkeiten an. Im obigen Beispiel beträgt die Wahrscheinlichkeit, $|0\rangle$ zu messen, $1/2$, und die Wahrscheinlichkeit, $|1\rangle$ zu messen, ebenfalls $1/2$.



### 2.3 Dirac-Notation (Bra-Ket-Notation)

Die **Dirac-Notation**, auch bekannt als Bra-Ket-Notation, ist eine prägnante und leistungsstarke Methode zur Beschreibung von Quantenzuständen und -operationen. Sie wurde von Paul Dirac entwickelt und ist in der Quantenmechanik und im Quantencomputing weit verbreitet.

Es gibt zwei Arten von Vektoren in der Dirac-Notation:

*   **Ket-Vektor** ($|\psi\rangle$): Entspricht einem Spaltenvektor. Wenn $\psi$ ein Spaltenvektor ist, kann er in der Dirac-Notation als $|\psi\rangle$ geschrieben werden, wobei $|\cdot\rangle$ anzeigt, dass es sich um einen Ket-Vektor handelt.

    **Beispiel 2.3.1: Ket-Vektoren**

    Die Basiszustände eines Qubits, $|0\rangle$ und $|1\rangle$, werden als Ket-Vektoren dargestellt:

    $$|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$

    $$|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$$

    Ein allgemeiner Zustand eines Qubits, $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$, kann als Ket-Vektor geschrieben werden:

    $$|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$$

*   **Bra-Vektor** ($\langle\psi|$): Entspricht einem Zeilenvektor und ist das Adjunkt (konjugiert Transponierte) eines Ket-Vektors. Wenn $|\psi\rangle$ ein Ket-Vektor ist, dann ist $\langle\psi| = (|\psi\rangle)^\dagger$.

    **Beispiel 2.3.2: Bra-Vektoren**

    Für die Basiszustände:

    $$\langle 0| = \begin{pmatrix} 1 & 0 \end{pmatrix}$$

    $$\langle 1| = \begin{pmatrix} 0 & 1 \end{pmatrix}$$

    Für einen allgemeinen Zustand $|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$ ist der Bra-Vektor:

    $$\langle\psi| = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix}$$

#### Skalarprodukt (Inneres Produkt)

Das **Skalarprodukt** zweier Quantenzustände $|\phi\rangle$ und $|\psi\rangle$ wird als $\langle\phi|\psi\rangle$ geschrieben. Es ist das Produkt des Bra-Vektors $\langle\phi|$ und des Ket-Vektors $|\psi\rangle$. Das Ergebnis ist ein Skalar. Das Skalarprodukt ist definiert als:

$$\langle\phi|\psi\rangle = \phi^\dagger \psi$$

Das Skalarprodukt $\langle\psi|\psi\rangle$ ist die Norm des Vektors $|\psi\rangle$ zum Quadrat, und für normierte Zustände ist $\langle\psi|\psi\rangle = 1$. Die Wahrscheinlichkeit, den Zustand $|\psi\rangle$ im Zustand $|\phi\rangle$ zu messen, ist $|\langle\phi|\psi\rangle|^2$.

**Beispiel 2.3.3: Skalarprodukt in Dirac-Notation**

Betrachten Sie die Zustände $|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{i}{\sqrt{2}}|1\rangle$ und $|\phi\rangle = \frac{1}{\sqrt{2}}|0\rangle - \frac{1}{\sqrt{2}}|1\rangle$.

In Vektorform:

$$|\psi\rangle = \begin{pmatrix} 1/\sqrt{2} \\ i/\sqrt{2} \end{pmatrix}$$

$$|\phi\rangle = \begin{pmatrix} 1/\sqrt{2} \\ -1/\sqrt{2} \end{pmatrix}$$

Die Bra-Vektoren sind:

$$\langle\psi| = \begin{pmatrix} 1/\sqrt{2} & -i/\sqrt{2} \end{pmatrix}$$

$$\langle\phi| = \begin{pmatrix} 1/\sqrt{2} & -1/\sqrt{2} \end{pmatrix}$$

Das Skalarprodukt $\langle\phi|\psi\rangle$ ist:

$$\langle\phi|\psi\rangle = \begin{pmatrix} 1/\sqrt{2} & -1/\sqrt{2} \end{pmatrix} \begin{pmatrix} 1/\sqrt{2} \\ i/\sqrt{2} \end{pmatrix}$$

$$= (1/\sqrt{2})(1/\sqrt{2}) + (-1/\sqrt{2})(i/\sqrt{2})$$

$$= 1/2 - i/2$$

Die Wahrscheinlichkeit, $|\psi\rangle$ im Zustand $|\phi\rangle$ zu messen, ist:

$$|\langle\phi|\psi\rangle|^2 = |1/2 - i/2|^2 = (1/2)^2 + (-1/2)^2 = 1/4 + 1/4 = 1/2$$

#### Outer Product (Äußeres Produkt oder Ketbra)

Das **äußere Produkt** zweier Vektoren $|\psi\rangle$ und $\langle\phi|$ wird als $|\psi\rangle\langle\phi|$ geschrieben und ist eine Matrix. Es ist definiert als die Matrixmultiplikation von Ket-Vektor $|\psi\rangle$ und Bra-Vektor $\langle\phi|$:

$$|\psi\rangle\langle\phi| = \psi \phi^\dagger$$

Äußere Produkte werden oft als **Projektionsoperatoren** bezeichnet, da sie einen Quantenzustand auf einen bestimmten Wert projizieren können.

**Beispiel 2.3.4: Outer Product**

Betrachten Sie die Basiszustände $|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ und $|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$.

Das äußere Produkt $|0\rangle\langle 0|$ ist:

$$|0\rangle\langle 0| = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \begin{pmatrix} 1 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$$

Dies ist der Projektionsoperator auf den Zustand $|0\rangle$. Entsprechend ist der Projektionsoperator auf den Zustand $|1\rangle$:

$$|1\rangle\langle 1| = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}$$



## 3. Qubits und Quantenzustände

### Das Qubit

Das **Qubit** (Quantum Bit) ist die grundlegende Informationseinheit im Quantencomputing, analog zum Bit im klassischen Computing. Im Gegensatz zu einem klassischen Bit, das entweder den Zustand 0 oder 1 annehmen kann, kann ein Qubit auch eine **Superposition** von 0 und 1 sein. Mathematisch wird der Zustand eines einzelnen Qubits durch einen Vektor in einem zweidimensionalen komplexen Hilbertraum dargestellt. Dieser Vektor ist ein Einheitsvektor, d.h. seine Länge ist 1.

Der allgemeine Zustand eines Qubits wird als $|\psi\rangle$ geschrieben und ist eine Linearkombination der Basiszustände $|0\rangle$ und $|1\rangle$:

$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$

wobei $\alpha$ und $\beta$ komplexe Zahlen sind, die als **Wahrscheinlichkeitsamplituden** bezeichnet werden. Die Quadrate ihrer Beträge, $|\alpha|^2$ und $|\beta|^2$, geben die Wahrscheinlichkeiten an, das Qubit bei einer Messung im Zustand $|0\rangle$ bzw. $|1\rangle$ zu finden. Die Normierungsbedingung besagt, dass die Summe dieser Wahrscheinlichkeiten 1 sein muss:

$$|\alpha|^2 + |\beta|^2 = 1$$

**Beispiel 3.1.1: Superposition eines Qubits**

Betrachten Sie ein Qubit im Zustand $|\psi\rangle = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle$. Hier sind $\alpha = \frac{1}{\sqrt{2}}$ und $\beta = \frac{1}{\sqrt{2}}$.

Die Wahrscheinlichkeit, $|0\rangle$ zu messen, ist $|\alpha|^2 = |\frac{1}{\sqrt{2}}|^2 = \frac{1}{2}$.

Die Wahrscheinlichkeit, $|1\rangle$ zu messen, ist $|\beta|^2 = |\frac{1}{\sqrt{2}}|^2 = \frac{1}{2}$.

Die Summe der Wahrscheinlichkeiten ist $\frac{1}{2} + \frac{1}{2} = 1$.

Dieser Zustand wird oft als $|+\rangle$ bezeichnet und ist ein Beispiel für eine gleichgewichtete Superposition.

#### Bloch-Kugel

Die **Bloch-Kugel** ist eine geometrische Darstellung des Zustandsraums eines einzelnen Qubits. Jeder Punkt auf der Oberfläche der Kugel repräsentiert einen reinen Zustand eines Qubits. Die Pole der Kugel entsprechen den Basiszuständen $|0\rangle$ (Nordpol) und $|1\rangle$ (Südpol). Ein allgemeiner Zustand $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ kann auf der Bloch-Kugel durch zwei Winkel $(\theta, \phi)$ dargestellt werden:

$$|\psi\rangle = \cos(\frac{\theta}{2})|0\rangle + e^{i\phi}\sin(\frac{\theta}{2})|1\rangle$$

wobei $\theta$ der Polarwinkel (von der positiven z-Achse) und $\phi$ der Azimutwinkel (von der positiven x-Achse in der xy-Ebene) ist. Die Bloch-Kugel ist ein nützliches Visualisierungswerkzeug, obwohl sie nur für einzelne Qubits gilt.

### Mehrere Qubits

Die wahre Leistungsfähigkeit des Quantencomputings zeigt sich, wenn mehrere Qubits miteinander interagieren. Der Zustand eines Systems aus mehreren Qubits wird durch das **Tensorprodukt** der einzelnen Qubit-Zustände beschrieben. Für $n$ Qubits ist der Zustandsraum ein $2^n$-dimensionaler Hilbertraum.

Das Tensorprodukt zweier Vektoren $v = \begin{pmatrix} a \\ b \end{pmatrix}$ und $u = \begin{pmatrix} c \\ d \end{pmatrix}$ ist definiert als:

$$v \otimes u = \begin{pmatrix} a \begin{pmatrix} c \\ d \end{pmatrix} \\ b \begin{pmatrix} c \\ d \end{pmatrix} \end{pmatrix} = \begin{pmatrix} ac \\ ad \\ bc \\ bd \end{pmatrix}$$

Im Dirac-Notation wird das Tensorprodukt von $|\psi\rangle$ und $|\phi\rangle$ als $|\psi\rangle \otimes |\phi\rangle$ oder vereinfacht als $|\psi\phi\rangle$ geschrieben.

**Beispiel 3.2.1: Zustand von zwei Qubits**

Betrachten Sie zwei Qubits, die beide im Zustand $|0\rangle$ sind. Der kombinierte Zustand ist:

$$|0\rangle \otimes |0\rangle = |00\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \cdot 1 \\ 1 \cdot 0 \\ 0 \cdot 1 \\ 0 \cdot 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}$$

Wenn das erste Qubit im Zustand $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$ und das zweite Qubit im Zustand $|0\rangle$ ist, dann ist der kombinierte Zustand:

$$|+\rangle \otimes |0\rangle = (\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle) \otimes |0\rangle$$

$$= \frac{1}{\sqrt{2}}(|0\rangle \otimes |0\rangle) + \frac{1}{\sqrt{2}}(|1\rangle \otimes |0\rangle)$$

$$= \frac{1}{\sqrt{2}}|00\rangle + \frac{1}{\sqrt{2}}|10\rangle$$

In Vektorform:

$$= \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} + \frac{1}{\sqrt{2}} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1/\sqrt{2} \\ 0 \\ 1/\sqrt{2} \\ 0 \end{pmatrix}$$



## 4. Quantengatter

**Quantengatter** sind die elementaren Operationen, die auf Qubits angewendet werden, um ihren Zustand zu manipulieren. Sie sind analog zu den Logikgattern in klassischen Computern, aber mit dem entscheidenden Unterschied, dass Quantengatter reversibel und unitär sein müssen. Jedes Quantengatter kann durch eine unitäre Matrix dargestellt werden, die auf den Zustandsvektor des Qubits (oder der Qubits) wirkt.

### Wichtige Einzel-Qubit-Gatter

Einzel-Qubit-Gatter wirken auf den Zustand eines einzelnen Qubits. Sie werden durch $2 \times 2$-unitäre Matrizen dargestellt.

*   **Pauli-X-Gatter (NOT-Gatter)**: Das Pauli-X-Gatter ist das Quantenäquivalent des klassischen NOT-Gatters. Es vertauscht die Amplituden von $|0\rangle$ und $|1\rangle$.

    Mathematische Darstellung:

    $$X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$

    **Beispiel 4.1.1: Anwendung des Pauli-X-Gatters**

    Anwendung auf den Zustand $|0\rangle$:

    $$X|0\rangle = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix} = |1\rangle$$

    Anwendung auf den Zustand $|1\rangle$:

    $$X|1\rangle = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} = |0\rangle$$

    Anwendung auf eine Superposition $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$:

    $$X|\psi\rangle = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} \alpha \\ \beta \end{pmatrix} = \begin{pmatrix} \beta \\ \alpha \end{pmatrix} = \beta|0\rangle + \alpha|1\rangle$$

*   **Pauli-Y-Gatter**:

    Mathematische Darstellung:

    $$Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}$$

    **Beispiel 4.1.2: Anwendung des Pauli-Y-Gatters**

    Anwendung auf den Zustand $|0\rangle$:

    $$Y|0\rangle = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ i \end{pmatrix} = i|1\rangle$$

*   **Pauli-Z-Gatter**:

    Mathematische Darstellung:

    $$Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

    **Beispiel 4.1.3: Anwendung des Pauli-Z-Gatters**

    Anwendung auf den Zustand $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$:

    $$Z|+\rangle = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = |-\rangle$$

*   **Hadamard-Gatter (H)**: Das Hadamard-Gatter ist von zentraler Bedeutung, da es ein Qubit aus einem Basiszustand in eine Superposition versetzt und umgekehrt. Es erzeugt eine gleichgewichtete Superposition der Basiszustände.

    Mathematische Darstellung:

    $$H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

    **Beispiel 4.1.4: Anwendung des Hadamard-Gatters**

    Anwendung auf den Zustand $|0\rangle$:

    $$H|0\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = |+\rangle$$

    Anwendung auf den Zustand $|1\rangle$:

    $$H|1\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = |-\rangle$$

### Wichtige Mehr-Qubit-Gatter

Mehr-Qubit-Gatter wirken auf den Zustand von zwei oder mehr Qubits. Sie werden durch $2^n \times 2^n$-unitäre Matrizen dargestellt, wobei $n$ die Anzahl der Qubits ist, auf die das Gatter wirkt.

*   **CNOT-Gatter (Controlled-NOT)**: Das CNOT-Gatter ist ein Zwei-Qubit-Gatter, das aus einem Kontroll-Qubit und einem Ziel-Qubit besteht. Wenn das Kontroll-Qubit im Zustand $|1\rangle$ ist, wird das Ziel-Qubit umgedreht (NOT-Operation). Ist das Kontroll-Qubit im Zustand $|0\rangle$, bleibt das Ziel-Qubit unverändert.

    Mathematische Darstellung (Kontroll-Qubit ist das erste Qubit):

    $$CNOT = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix}$$

    **Beispiel 4.2.1: Anwendung des CNOT-Gatters**

    Anwendung auf den Zustand $|00\rangle$:

    $$CNOT|00\rangle = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix} = |00\rangle$$

    Anwendung auf den Zustand $|01\rangle$:

    $$CNOT|01\rangle = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} = |01\rangle$$

    Anwendung auf den Zustand $|10\rangle$:

    $$CNOT|10\rangle = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} = |11\rangle$$

    Anwendung auf den Zustand $|11\rangle$:

    $$CNOT|11\rangle = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} = |10\rangle$$

*   **Toffoli-Gatter (CCNOT)**: Das Toffoli-Gatter ist ein Drei-Qubit-Gatter mit zwei Kontroll-Qubits und einem Ziel-Qubit. Das Ziel-Qubit wird nur dann umgedreht, wenn beide Kontroll-Qubits im Zustand $|1\rangle$ sind. Es ist ein universelles Gatter für klassische Berechnungen.

    Mathematische Darstellung (Kontroll-Qubits sind die ersten beiden Qubits):

    $$Toffoli = \begin{pmatrix} 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \end{pmatrix}$$

    **Beispiel 4.2.2: Anwendung des Toffoli-Gatters**

    Anwendung auf den Zustand $|110\rangle$:

    $$Toffoli|110\rangle = \begin{pmatrix} 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 0 \\ 0 \\ 0 \\ 0 \\ 0 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 0 \\ 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} = |111\rangle$$

    Das Ziel-Qubit (das dritte Qubit) wurde von $|0\rangle$ auf $|1\rangle$ umgedreht, da beide Kontroll-Qubits im Zustand $|1\rangle$ waren.



## 5. Quantenphänomene

### 5.1 Superposition

**Superposition** ist eines der fundamentalsten Prinzipien der Quantenmechanik und ermöglicht es einem Qubit, sich gleichzeitig in mehreren Zuständen zu befinden. Im Gegensatz zu einem klassischen Bit, das entweder 0 oder 1 ist, kann ein Qubit eine Linearkombination von $|0\rangle$ und $|1\rangle$ sein. Mathematisch wird dies durch den Zustandsvektor $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ ausgedrückt, wobei $\alpha$ und $\beta$ komplexe Wahrscheinlichkeitsamplituden sind und $|\alpha|^2 + |\beta|^2 = 1$ gilt.

Die Superposition ist der Schlüssel zur Parallelität im Quantencomputing. Ein System von $n$ Qubits kann sich in einer Superposition von $2^n$ klassischen Zuständen befinden. Dies bedeutet, dass ein Quantencomputer potenziell $2^n$ Berechnungen gleichzeitig durchführen kann, was zu einer exponentiellen Beschleunigung für bestimmte Problemklassen führt.

**Beispiel 5.1.1: Erzeugung einer Superposition mit dem Hadamard-Gatter**

Wir haben bereits gesehen, dass das Hadamard-Gatter (H) ein Qubit in eine Superposition versetzt. Wenn wir ein Qubit, das sich im Zustand $|0\rangle$ befindet, durch ein Hadamard-Gatter schicken, erhalten wir den Zustand $|+\rangle$:

$$H|0\rangle = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle$$

Dieser Zustand $|+\rangle$ ist eine gleichgewichtete Superposition von $|0\rangle$ und $|1\rangle$. Bei einer Messung hat man eine 50%ige Chance, $|0\rangle$ zu messen, und eine 50%ige Chance, $|1\rangle$ zu messen.

**Beispiel 5.1.2: Superposition von zwei Qubits**

Betrachten wir ein System von zwei Qubits, die beide im Zustand $|0\rangle$ initialisiert sind, also $|00\rangle$. Wenn wir auf jedes Qubit ein Hadamard-Gatter anwenden, erhalten wir:

$$(H \otimes H)|00\rangle = (H|0\rangle) \otimes (H|0\rangle)$$

$$= (\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle) \otimes (\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle)$$

$$= \frac{1}{2}(|0\rangle \otimes |0\rangle + |0\rangle \otimes |1\rangle + |1\rangle \otimes |0\rangle + |1\rangle \otimes |1\rangle)$$

$$= \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$$

In Vektorform:

$$= \frac{1}{2}\begin{pmatrix} 1 \\ 1 \\ 1 \\ 1 \end{pmatrix}$$

Dieser Zustand ist eine gleichgewichtete Superposition aller $2^2 = 4$ möglichen Basiszustände für zwei Qubits. Bei einer Messung dieses Systems hat jeder der vier Basiszustände ($|00\rangle, |01\rangle, |10\rangle, |11\rangle$) eine Wahrscheinlichkeit von $|1/2|^2 = 1/4$ gemessen zu werden. Dies demonstriert die Fähigkeit von Quantencomputern, eine große Anzahl von Zuständen gleichzeitig zu 


repräsentieren und zu verarbeiten.

### 5.2 Verschränkung (Entanglement)

**Quantenverschränkung** ist ein Phänomen, bei dem zwei oder mehr Qubits so miteinander verbunden sind, dass der Zustand eines Qubits nicht unabhängig von den Zuständen der anderen beschrieben werden kann, selbst wenn sie räumlich getrennt sind. Eine Messung an einem verschränkten Qubit beeinflusst sofort den Zustand der anderen verschränkten Qubits, unabhängig von der Entfernung. Dies ist eine der nicht-intuitiven Eigenschaften der Quantenmechanik und eine entscheidende Ressource für viele Quantenalgorithmen.

Mathematisch gesehen ist ein verschränkter Zustand ein Zustand von mehreren Qubits, der nicht als Tensorprodukt der einzelnen Qubit-Zustände faktorisiert werden kann. Solche Zustände werden als **nicht-separierbar** bezeichnet.

**Beispiel 5.2.1: Bell-Zustände (maximale Verschränkung)**

Die bekanntesten Beispiele für verschränkte Zustände sind die **Bell-Zustände**. Es gibt vier Bell-Zustände, die eine maximale Verschränkung zwischen zwei Qubits darstellen. Sie werden oft durch die Anwendung eines Hadamard-Gatters auf das erste Qubit und eines CNOT-Gatters auf beide Qubits erzeugt.

Betrachten wir die Erzeugung des ersten Bell-Zustands, des $|\Phi^+\rangle$-Zustands, beginnend mit dem Zustand $|00\rangle$:

1.  **Hadamard auf das erste Qubit:**

    $$(H \otimes I)|00\rangle = (H|0\rangle) \otimes (I|0\rangle)$$

    $$= (\frac{1}{\sqrt{2}}|0\rangle + \frac{1}{\sqrt{2}}|1\rangle) \otimes |0\rangle$$

    $$= \frac{1}{\sqrt{2}}(|00\rangle + |10\rangle)$$

    In Vektorform:

    $$= \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 1 \\ 0 \end{pmatrix}$$

2.  **CNOT-Gatter auf die beiden Qubits (Kontroll-Qubit ist das erste, Ziel-Qubit ist das zweite):**

    $$CNOT \left( \frac{1}{\sqrt{2}}(|00\rangle + |10\rangle) \right)$$

    $$= \frac{1}{\sqrt{2}}(CNOT|00\rangle + CNOT|10\rangle)$$

    Wir wissen von den CNOT-Beispielen:

    $$CNOT|00\rangle = |00\rangle$$

    $$CNOT|10\rangle = |11\rangle$$

    Also erhalten wir:

    $$= \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$$

    In Vektorform:

    $$= \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix}$$

Dieser Zustand $|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$ ist ein verschränkter Zustand. Man kann ihn nicht als Produkt zweier Einzel-Qubit-Zustände schreiben. Wenn man das erste Qubit misst und es im Zustand $|0\rangle$ findet, weiß man sofort, dass das zweite Qubit ebenfalls im Zustand $|0\rangle$ ist, ohne es messen zu müssen. Ebenso, wenn das erste Qubit im Zustand $|1\rangle$ gefunden wird, ist das zweite Qubit auch im Zustand $|1\rangle$. Diese Korrelationen sind stärker als alles, was in der klassischen Physik möglich ist, und sind die Grundlage für Quantenkommunikation und bestimmte Quantenalgorithmen.



## 6. Quantenmessung

Die **Quantenmessung** ist der Prozess, bei dem Informationen aus einem Quantensystem extrahiert werden. Im Gegensatz zur klassischen Messung, die den Zustand eines Systems nicht wesentlich verändert, führt die Quantenmessung zu einer irreversiblen Veränderung des Quantenzustands. Dies wird oft als **Kollaps der Wellenfunktion** bezeichnet.

Das **Messpostulat** der Quantenmechanik besagt, dass bei der Messung einer Observablen (einer messbaren physikalischen Größe) das System in einen Eigenzustand dieser Observablen springt, und das Messergebnis ist der entsprechende Eigenwert. Die Wahrscheinlichkeit, ein bestimmtes Messergebnis zu erhalten, ist durch die Wahrscheinlichkeitsamplituden des Quantenzustands gegeben.

Mathematisch werden Observablen durch **Hermitesche Operatoren** dargestellt. Die möglichen Messergebnisse sind die Eigenwerte dieses Operators, und die Zustände, in die das System nach der Messung kollabiert, sind die entsprechenden Eigenvektoren.

#### Projektionsoperatoren

**Projektionsoperatoren** sind ein nützliches Werkzeug, um den Messprozess zu beschreiben. Für einen Basiszustand $|k\rangle$ ist der Projektionsoperator $P_k = |k\rangle\langle k|$. Wenn ein Quantensystem im Zustand $|\psi\rangle$ gemessen wird, ist die Wahrscheinlichkeit, das Ergebnis $k$ zu erhalten, gegeben durch:

$$P(k) = |\langle k|\psi\rangle|^2 = \langle\psi|P_k|\psi\rangle$$

Nach der Messung, wenn das Ergebnis $k$ ist, kollabiert der Zustand des Systems zu:

$$|\psi'\rangle = \frac{P_k|\psi\rangle}{\sqrt{\langle\psi|P_k|\psi\rangle}}$$

**Beispiel 6.1.1: Messung eines Qubits**

Betrachten Sie ein Qubit im Zustand $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$. Wir möchten die Wahrscheinlichkeit berechnen, bei einer Messung im Standardbasis ($|0\rangle, |1\rangle$) den Zustand $|0\rangle$ zu erhalten.

Der Projektionsoperator für den Zustand $|0\rangle$ ist $P_0 = |0\rangle\langle 0| = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$.

Die Wahrscheinlichkeit, $|0\rangle$ zu messen, ist:

$$P(0) = |\langle 0|\psi\rangle|^2$$

Wir wissen, dass $\langle 0|\psi\rangle = \langle 0|(\alpha|0\rangle + \beta|1\rangle) = \alpha\langle 0|0\rangle + \beta\langle 0|1\rangle = \alpha(1) + \beta(0) = \alpha$.

Also ist $P(0) = |\alpha|^2$.

Alternativ mit dem Projektionsoperator:

$$P(0) = \langle\psi|P_0|\psi\rangle = \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$$

$$= \begin{pmatrix} \alpha^* & \beta^* \end{pmatrix} \begin{pmatrix} \alpha \\ 0 \end{pmatrix} = \alpha^*\alpha + \beta^*(0) = |\alpha|^2$$

Wenn wir $|0\rangle$ messen, kollabiert der Zustand zu:

$$|\psi'\rangle = \frac{P_0|\psi\rangle}{\sqrt{\langle\psi|P_0|\psi\rangle}} = \frac{|0\rangle\langle 0|(\alpha|0\rangle + \beta|1\rangle)}{\sqrt{|\alpha|^2}}$$

$$= \frac{|0\rangle(\alpha\langle 0|0\rangle + \beta\langle 0|1\rangle)}{|\alpha|} = \frac{|0\rangle\alpha}{|\alpha|} = e^{i\delta}|0\rangle$$

wobei $e^{i\delta}$ eine globale Phase ist, die physikalisch nicht relevant ist. Der Zustand ist also nach der Messung definitiv $|0\rangle$.



## 7. Quantenalgorithmen (mit rechnerischen Beispielen)

**Quantenalgorithmen** sind Algorithmen, die auf einem Quantencomputer ausgeführt werden, um bestimmte Probleme effizienter zu lösen als klassische Algorithmen. Die Effizienzgewinne ergeben sich aus der Nutzung von Quantenphänomenen wie Superposition und Verschränkung. Hier werden wir einige der bekanntesten Quantenalgorithmen und ihre mathematischen Grundlagen untersuchen.

### 7.1 Deutsch-Jozsa-Algorithmus

Der **Deutsch-Jozsa-Algorithmus** ist einer der ersten Quantenalgorithmen, der einen exponentiellen Geschwindigkeitsvorteil gegenüber jedem klassischen deterministischen Algorithmus für ein bestimmtes Problem demonstriert. Das Problem besteht darin, zu bestimmen, ob eine gegebene Funktion $f: \{0,1\}^n \to \{0,1\}$ entweder **konstant** (d.h. $f(x)$ ist für alle $x$ entweder 0 oder 1) oder **balanciert** (d.h. $f(x)$ ist für die Hälfte der Eingaben 0 und für die andere Hälfte 1) ist. Ein klassischer deterministischer Algorithmus müsste im schlimmsten Fall $2^{n-1} + 1$ Funktionsauswertungen durchführen, während der Deutsch-Jozsa-Algorithmus nur eine einzige Funktionsauswertung benötigt.

Der Algorithmus verwendet ein Quantenschaltkreis, der aus Hadamard-Gattern und einem Orakel für die Funktion $f$ besteht. Das Orakel ist eine unitäre Operation $U_f$, die den Zustand $|x\rangle|y\rangle$ in $|x\rangle|y \oplus f(x)\rangle$ transformiert, wobei $\oplus$ die Addition modulo 2 ist.

**Schritte des Deutsch-Jozsa-Algorithmus für $n=1$:**

1.  **Initialisierung:** Beginnen Sie mit dem Zustand $|0\rangle|1\rangle$.

2.  **Anwendung von Hadamard-Gattern:** Wenden Sie ein Hadamard-Gatter auf jedes Qubit an.

    $$H|0\rangle = |+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$$

    $$H|1\rangle = |-\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$$

    Der Zustand wird zu:

    $$|\psi_1\rangle = H|0\rangle \otimes H|1\rangle = |+\rangle|-\rangle = \frac{1}{2}(|0\rangle + |1\rangle)(|0\rangle - |1\rangle)$$

    $$= \frac{1}{2}(|00\rangle - |01\rangle + |10\rangle - |11\rangle)$$

3.  **Anwendung des Orakels $U_f$:** Das Orakel transformiert $|x\rangle|y\rangle$ in $|x\rangle|y \oplus f(x)\rangle$. Eine wichtige Eigenschaft des Orakels ist, dass wenn das zweite Qubit im Zustand $|-\rangle$ ist, die Transformation zu $|x\rangle|f(x)\rangle$ wird:

    $$U_f|x\rangle|-\rangle = |x\rangle|f(x)\rangle$$

    Daher wird der Zustand nach Anwendung des Orakels:

    $$|\psi_2\rangle = U_f |+\rangle|-\rangle = \frac{1}{\sqrt{2}} \sum_{x \in \{0,1\}} |x\rangle (-1)^{f(x)} |-\rangle$$ 

    $$= \frac{1}{\sqrt{2}} ((-1)^{f(0)}|0\rangle + (-1)^{f(1)}|1\rangle) |-\rangle$$

4.  **Anwendung von Hadamard auf das erste Qubit:** Wenden Sie ein Hadamard-Gatter auf das erste Qubit an.

    $$|\psi_3\rangle = (H \otimes I)|\psi_2\rangle = H \left( \frac{1}{\sqrt{2}} ((-1)^{f(0)}|0\rangle + (-1)^{f(1)}|1\rangle) \right) |-\rangle$$

    Wir wissen, dass $H|0\rangle = |+\rangle$ und $H|1\rangle = |-\rangle$. Daher:

    $$H ((-1)^{f(0)}|0\rangle + (-1)^{f(1)}|1\rangle) = (-1)^{f(0)} H|0\rangle + (-1)^{f(1)} H|1\rangle$$

    $$= (-1)^{f(0)} \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle) + (-1)^{f(1)} \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$$

    $$= \frac{1}{\sqrt{2}} [ ((-1)^{f(0)} + (-1)^{f(1)})|0\rangle + ((-1)^{f(0)} - (-1)^{f(1)})|1\rangle ]$$

    Setzen wir dies zurück in $|\psi_3\rangle$:

    $$|\psi_3\rangle = \frac{1}{2} [ ((-1)^{f(0)} + (-1)^{f(1)})|0\rangle + ((-1)^{f(0)} - (-1)^{f(1)})|1\rangle ] |-\rangle$$

5.  **Messung des ersten Qubits:** Messen Sie das erste Qubit. Wenn das Ergebnis $|0\rangle$ ist, ist die Funktion konstant. Wenn das Ergebnis $|1\rangle$ ist, ist die Funktion balanciert.

    *   **Fall 1: $f(x)$ ist konstant.**
        *   Wenn $f(x) = 0$ für alle $x$, dann $f(0)=0, f(1)=0$. Der Koeffizient von $|0\rangle$ ist $((-1)^0 + (-1)^0) = 1+1=2$. Der Koeffizient von $|1\rangle$ ist $((-1)^0 - (-1)^0) = 1-1=0$.
        *   Der Zustand des ersten Qubits ist $|0\rangle$.
        *   Messung ergibt $|0\rangle$.
        *   Wenn $f(x) = 1$ für alle $x$, dann $f(0)=1, f(1)=1$. Der Koeffizient von $|0\rangle$ ist $((-1)^1 + (-1)^1) = -1-1=-2$. Der Koeffizient von $|1\rangle$ ist $((-1)^1 - (-1)^1) = -1-(-1)=0$.
        *   Der Zustand des ersten Qubits ist $|0\rangle$ (bis auf eine globale Phase).
        *   Messung ergibt $|0\rangle$.

    *   **Fall 2: $f(x)$ ist balanciert.**
        *   Wenn $f(0)=0, f(1)=1$. Der Koeffizient von $|0\rangle$ ist $((-1)^0 + (-1)^1) = 1-1=0$. Der Koeffizient von $|1\rangle$ ist $((-1)^0 - (-1)^1) = 1-(-1)=2$.
        *   Der Zustand des ersten Qubits ist $|1\rangle$.
        *   Messung ergibt $|1\rangle$.
        *   Wenn $f(0)=1, f(1)=0$. Der Koeffizient von $|0\rangle$ ist $((-1)^1 + (-1)^0) = -1+1=0$. Der Koeffizient von $|1\rangle$ ist $((-1)^1 - (-1)^0) = -1-1=-2$.
        *   Der Zustand des ersten Qubits ist $|1\rangle$ (bis auf eine globale Phase).
        *   Messung ergibt $|1\rangle$.

Der Deutsch-Jozsa-Algorithmus zeigt, wie Quantenüberlagerung und Interferenz genutzt werden können, um eine globale Eigenschaft einer Funktion mit nur einer einzigen Abfrage zu bestimmen, was klassisch nicht möglich wäre.

### 7.2 Grover-Algorithmus

Der **Grover-Algorithmus** ist ein Quantenalgorithmus zur Suche in einer unsortierten Datenbank. Für eine Datenbank mit $N$ Einträgen, von denen genau einer der gesuchte Eintrag ist, benötigt ein klassischer Algorithmus im Durchschnitt $N/2$ Abfragen und im schlimmsten Fall $N$ Abfragen. Der Grover-Algorithmus hingegen benötigt nur $O(\sqrt{N})$ Abfragen. Dies ist ein quadratischer Geschwindigkeitsvorteil.

Der Algorithmus basiert auf der Idee der **Amplitudenverstärkung**, bei der die Amplitude des gesuchten Zustands iterativ erhöht und die Amplituden der anderen Zustände verringert werden.

**Schritte des Grover-Algorithmus:**

1.  **Initialisierung:** Beginnen Sie mit $n$ Qubits im Zustand $|0\rangle^{\otimes n}$.

2.  **Anwendung von Hadamard-Gattern:** Wenden Sie ein Hadamard-Gatter auf jedes Qubit an, um eine gleichmäßige Superposition aller $2^n = N$ Basiszustände zu erzeugen:

    $$|\psi_0\rangle = H^{\otimes n}|0\rangle^{\otimes n} = \frac{1}{\sqrt{N}} \sum_{x=0}^{N-1} |x\rangle$$

3.  **Iterative Anwendung des Grover-Orakels und des Grover-Diffusors:** Dies ist der Kern des Algorithmus. Diese Schritte werden $R = \lfloor \frac{\pi}{4}\sqrt{N} \rfloor$ Mal wiederholt.

    *   **Orakel ($U_f$):** Das Orakel markiert den gesuchten Zustand $|x_0\rangle$ durch Invertierung seiner Phase. Es transformiert $|x\rangle$ in $(-1)^{f(x)}|x\rangle$, wobei $f(x)=1$ für den gesuchten Eintrag und $f(x)=0$ sonst.

        $$U_f = I - 2|x_0\rangle\langle x_0|$$

    *   **Grover-Diffusor ($D$):** Der Diffusor invertiert die Amplituden um den Durchschnitt. Er ist definiert als $D = 2|\psi_0\rangle\langle\psi_0| - I$.

        $$D = 2 H^{\otimes n}|0\rangle^{\otimes n}\langle 0|^{\otimes n}H^{\otimes n} - I$$

    Eine Iteration des Grover-Algorithmus ist $G = D U_f$.

4.  **Messung:** Nach $R$ Iterationen wird das System gemessen. Mit hoher Wahrscheinlichkeit wird der gesuchte Zustand $|x_0\rangle$ gefunden.

**Beispiel 7.2.1: Grover-Algorithmus für $N=4$ (2 Qubits)**

Angenommen, wir suchen den Zustand $|11\rangle$ in einer Datenbank von 4 Einträgen ($|00\rangle, |01\rangle, |10\rangle, |11\rangle$). Hier ist $N=4$, also $n=2$. Die Anzahl der Iterationen ist $R = \lfloor \frac{\pi}{4}\sqrt{4} \rfloor = \lfloor \frac{\pi}{2} \rfloor = 1$.

1.  **Initialisierung:** $|00\rangle$.

2.  **Hadamard auf beide Qubits:**

    $$|\psi_0\rangle = H^{\otimes 2}|00\rangle = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle + |11\rangle)$$

3.  **Eine Iteration des Grover-Operators $G = D U_f$:**

    *   **Orakel $U_f$ für $|11\rangle$:**

        $$U_f = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}$$

        Anwendung auf $|\psi_0\rangle$:

        $$U_f|\psi_0\rangle = \frac{1}{2}(|00\rangle + |01\rangle + |10\rangle - |11\rangle)$$

    *   **Grover-Diffusor $D$:**

        Der Diffusor $D = 2|\psi_0\rangle\langle\psi_0| - I$. In Matrixform ist $|\psi_0\rangle\langle\psi_0|$:

        $$|\psi_0\rangle\langle\psi_0| = \frac{1}{4} \begin{pmatrix} 1 \\ 1 \\ 1 \\ 1 \end{pmatrix} \begin{pmatrix} 1 & 1 & 1 & 1 \end{pmatrix} = \frac{1}{4} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \end{pmatrix}$$

        $$D = 2 \cdot \frac{1}{4} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \end{pmatrix} - \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}$$

        $$D = \frac{1}{2} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \\ 1 & 1 & 1 & 1 \end{pmatrix} - \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix} = \begin{pmatrix} -1/2 & 1/2 & 1/2 & 1/2 \\ 1/2 & -1/2 & 1/2 & 1/2 \\ 1/2 & 1/2 & -1/2 & 1/2 \\ 1/2 & 1/2 & 1/2 & -1/2 \end{pmatrix}$$

        Anwendung von $D$ auf $U_f|\psi_0\rangle$:

        $$D U_f|\psi_0\rangle = \begin{pmatrix} -1/2 & 1/2 & 1/2 & 1/2 \\ 1/2 & -1/2 & 1/2 & 1/2 \\ 1/2 & 1/2 & -1/2 & 1/2 \\ 1/2 & 1/2 & 1/2 & -1/2 \end{pmatrix} \frac{1}{2} \begin{pmatrix} 1 \\ 1 \\ 1 \\ -1 \end{pmatrix}$$

        $$= \frac{1}{2} \begin{pmatrix} (-1/2)(1) + (1/2)(1) + (1/2)(1) + (1/2)(-1) \\ (1/2)(1) + (-1/2)(1) + (1/2)(1) + (1/2)(-1) \\ (1/2)(1) + (1/2)(1) + (-1/2)(1) + (1/2)(-1) \\ (1/2)(1) + (1/2)(1) + (1/2)(1) + (-1/2)(-1) \end{pmatrix}$$

        $$= \frac{1}{2} \begin{pmatrix} -1/2 + 1/2 + 1/2 - 1/2 \\ 1/2 - 1/2 + 1/2 - 1/2 \\ 1/2 + 1/2 - 1/2 - 1/2 \\ 1/2 + 1/2 + 1/2 + 1/2 \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 0 \\ 0 \\ 0 \\ 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} = |11\rangle$$

4.  **Messung:** Nach einer Iteration ist der Zustand exakt $|11\rangle$. Eine Messung ergibt mit 100%iger Wahrscheinlichkeit den gesuchten Zustand.

### 7.3 Shor-Algorithmus

Der **Shor-Algorithmus** ist ein Quantenalgorithmus zur Faktorisierung großer Zahlen in ihre Primfaktoren. Er ist exponentiell schneller als der beste bekannte klassische Faktorisierungsalgorithmus (General Number Field Sieve). Die Fähigkeit des Shor-Algorithmus, große Zahlen effizient zu faktorisieren, hat weitreichende Implikationen für die Kryptographie, insbesondere für die Sicherheit von Public-Key-Verschlüsselungssystemen wie RSA, die auf der Schwierigkeit der Faktorisierung großer Zahlen beruhen.

Der Shor-Algorithmus besteht aus zwei Hauptteilen:

1.  **Klassischer Teil:** Reduziert das Faktorisierungsproblem auf das Problem der Periodenfindung einer modularen Exponentialfunktion.
2.  **Quantenteil:** Verwendet die Quanten-Fourier-Transformation (QFT), um die Periode der Funktion effizient zu finden.

**Problem der Periodenfindung:** Gegeben eine Funktion $f(x) = a^x \pmod N$, finde die Periode $r$, d.h. die kleinste positive ganze Zahl, für die $a^{x+r} \equiv a^x \pmod N$ gilt.

**Schritte des Quantenteils des Shor-Algorithmus (Periodenfindung):**

1.  **Initialisierung:** Erstellen Sie zwei Register. Das erste Register (Eingaberegister) mit $n$ Qubits im Zustand $|0\rangle^{\otimes n}$ und das zweite Register (Ausgaberegister) mit $m$ Qubits im Zustand $|0\rangle^{\otimes m}$. Der Anfangszustand ist $|0\rangle^{\otimes n}|0\rangle^{\otimes m}$.

2.  **Anwendung von Hadamard-Gattern auf das Eingaberegister:** Wenden Sie ein Hadamard-Gatter auf jedes Qubit des ersten Registers an, um eine gleichmäßige Superposition aller möglichen Eingabewerte zu erzeugen.

    $$|\psi_1\rangle = (H^{\otimes n} \otimes I^{\otimes m}) |0\rangle^{\otimes n}|0\rangle^{\otimes m} = \frac{1}{\sqrt{2^n}} \sum_{x=0}^{2^n-1} |x\rangle|0\rangle^{\otimes m}$$

3.  **Anwendung des modularen Exponentialorakels:** Wenden Sie die unitäre Operation $U_f$ an, die $|x\rangle|0\rangle$ in $|x\rangle|f(x)\rangle = |x\rangle|a^x \pmod N\rangle$ transformiert.

    $$|\psi_2\rangle = \frac{1}{\sqrt{2^n}} \sum_{x=0}^{2^n-1} |x\rangle|a^x \pmod N\rangle$$

4.  **Messung des Ausgaberegisters:** Messen Sie das zweite Register. Das Ergebnis ist ein Wert $y_0 = a^{x_0} \pmod N$ für ein zufälliges $x_0$. Nach der Messung kollabiert das erste Register in eine Superposition von Zuständen, die $x$ Werte enthalten, für die $a^x \pmod N = y_0$ ist. Diese $x$ Werte sind $x_0, x_0+r, x_0+2r, \dots$.

    $$|\psi_3\rangle = \frac{1}{\sqrt{K}} \sum_{k} |x_0 + kr\rangle |y_0\rangle$$

    wobei $K$ die Anzahl der Terme in der Summe ist.

5.  **Anwendung der Quanten-Fourier-Transformation (QFT) auf das erste Register:** Die QFT ist eine unitäre Transformation, die die diskrete Fourier-Transformation in Quantenform implementiert. Sie ist entscheidend für die Periodenfindung.

    $$QFT|x\rangle = \frac{1}{\sqrt{2^n}} \sum_{k=0}^{2^n-1} e^{2\pi i x k / 2^n} |k\rangle$$

    Wenn die QFT auf den Zustand $|\psi_3\rangle$ angewendet wird, werden die Amplituden der Zustände, deren $k$ Werte Vielfache von $2^n/r$ sind, verstärkt. Dies ermöglicht es, $r$ zu bestimmen.

6.  **Messung des ersten Registers:** Messen Sie das erste Register. Das Ergebnis $k$ wird mit hoher Wahrscheinlichkeit nahe einem Vielfachen von $2^n/r$ sein. Durch Wiederholung des Algorithmus und Anwendung von Kettenbruchalgorithmen kann $r$ mit hoher Wahrscheinlichkeit bestimmt werden.

**Beispiel 7.3.1: Faktorisierung von $N=15$ mit Shor-Algorithmus (vereinfacht)**

Wir wollen $N=15$ faktorisieren. Wählen wir $a=7$. Wir suchen die Periode $r$ von $f(x) = 7^x \pmod{15}$.

$7^1 \pmod{15} = 7$
$7^2 \pmod{15} = 49 \pmod{15} = 4$
$7^3 \pmod{15} = 7 \cdot 4 = 28 \pmod{15} = 13$
$7^4 \pmod{15} = 7 \cdot 13 = 91 \pmod{15} = 1$

Die Periode ist $r=4$.

Im Quantenteil würde die QFT dazu führen, dass die Messung des ersten Registers Werte liefert, die Vielfache von $2^n/4$ sind. Angenommen, wir verwenden $n=8$ Qubits für das Eingaberegister, dann ist $2^n = 256$. Die Vielfachen von $256/4 = 64$ sind $0, 64, 128, 192$. Die Messung des ersten Registers würde mit hoher Wahrscheinlichkeit einen dieser Werte ergeben.

Wenn wir beispielsweise $k=64$ messen, dann ist $k/2^n = 64/256 = 1/4$. Da $k/2^n \approx c/r$, können wir $r$ als $r \approx c \cdot 2^n/k$ schätzen. Hier ist $c=1$, also $r \approx 4$. Mit dem Kettenbruchalgorithmus kann man aus $1/4$ direkt $r=4$ erhalten.

Sobald $r$ gefunden ist, können wir die Faktoren von $N$ finden. Wenn $r$ gerade ist, berechnen wir $\text{ggT}(a^{r/2}-1, N)$ und $\text{ggT}(a^{r/2}+1, N)$.

Für $a=7, r=4, N=15$:

$a^{r/2}-1 = 7^{4/2}-1 = 7^2-1 = 49-1 = 48$
$a^{r/2}+1 = 7^{4/2}+1 = 7^2+1 = 49+1 = 50$

$\text{ggT}(48, 15) = 3$
$\text{ggT}(50, 15) = 5$

Die Faktoren von 15 sind 3 und 5. Dies zeigt die Leistungsfähigkeit des Shor-Algorithmus zur Faktorisierung großer Zahlen.



## 8. Fazit und Ausblick

Die Mathematik ist das Herzstück des Quantencomputings. Von den grundlegenden Konzepten der linearen Algebra, die die Zustände von Qubits und die Operationen von Quantengattern beschreiben, über die abstrakten Hilberträume, die den Zustandsraum von Quantensystemen definieren, bis hin zur prägnanten Dirac-Notation, die die Manipulation dieser Zustände vereinfacht – all diese mathematischen Werkzeuge sind unerlässlich, um die Funktionsweise und das Potenzial von Quantencomputern zu verstehen.

Phänomene wie Superposition und Verschränkung, die mathematisch durch Linearkombinationen und Tensorprodukte ausgedrückt werden, sind nicht nur faszinierende Aspekte der Quantenmechanik, sondern auch die treibenden Kräfte hinter den exponentiellen Geschwindigkeitsvorteilen, die Quantenalgorithmen wie der Deutsch-Jozsa-, Grover- und Shor-Algorithmus bieten. Die detaillierten rechnerischen Beispiele in diesem Kapitel sollten dazu beigetragen haben, diese komplexen Konzepte greifbarer zu machen und ein tieferes Verständnis für ihre Anwendung im Quantencomputing zu entwickeln.

Obwohl das Quantencomputing noch in den Kinderschuhen steckt, schreitet die Forschung rasant voran. Die Entwicklung robusterer Quantenhardware und die Entdeckung neuer Quantenalgorithmen werden weiterhin von einem tiefen mathematischen Verständnis abhängen. Die hier vorgestellten Grundlagen bilden eine solide Basis für jeden, der sich weiter in dieses spannende und zukunftsweisende Feld vertiefen möchte. Die Synergie zwischen Mathematik und Quantenphysik verspricht, die Grenzen des Möglichen in der Berechnung neu zu definieren und Lösungen für Probleme zu finden, die heute noch unlösbar erscheinen.

