## 1. Teljes indukció elve (Halmazelméleti megközelítés)

**Tétel:**
Legyen $A_n$ egy állítás $\forall n \in \mathbb{N}$ esetén.
Tegyük fel, hogy:
* $A_0$ igaz
* Ha $A_n$ igaz, akkor $A_{n+1}$ is igaz ($n \in \mathbb{N}$)

Ekkor $A_n$ igaz $\forall n \in \mathbb{N}$-re.

**Bizonyítás:**
Legyen $S = \{n \in \mathbb{N} : A_n \text{ igaz} \}$, ekkor nyilvánvalóan $S \subseteq \mathbb{N}$.

$S$ egy induktív halmaz, hiszen:
1. $0 \in S$, mert $A_0$ igaz.
2. Ha $n \in S$, akkor $A_n$ igaz $\Rightarrow A_{n+1}$ igaz $\Rightarrow n + 1 \in S \Rightarrow S$ induktív.

Tudjuk, hogy $\mathbb{N}$ a legkisebb induktív halmaz. Ebből következik:
$$\mathbb{N} \subseteq S$$

Mivel eleve $S \subseteq \mathbb{N}$ volt, a kettőből együtt az következik, hogy $S = \mathbb{N}$. 
Vagyis $A_n$ igaz $\forall n \in \mathbb{N}$-re. $\square$



## 2. Szuprémum elv

**Tétel:** Bármely nem üres, felülről korlátos $H \subseteq \mathbb{R}$ halmaz felső korlátai között létezik legkisebb.

**Bizonyítás:**

Legyen $A = H$, a $B$ pedig az $A$ halmaz összes felső korlátjának halmaza ($B := \{k \in \mathbb{R} : k \text{ felső korlátja } A\text{-nak}\}$).

1. Mivel $A$ nem üres és felülről korlátos, ezért $B$ sem üres. A definícióból adódik, hogy bármely $a \in A$ és $k \in B$ elemre igaz, hogy $a \le k$.

2. A teljességi axióma értelmében ekkor létezik olyan $\xi \in \mathbb{R}$ elválasztó pont, amelyre minden $a \in A$ és $k \in B$ esetén teljesül, hogy:
$$a \le \xi \le k$$

3. Ebből az egyenlőtlenségből két dolog is következik:

* Mivel $a \le \xi$ minden $A$-beli elemre, ezért $\xi$ egy felső korlát.

* Mivel $\xi \le k$ minden $B$-beli elemre (vagyis minden létező felső korlátra), ezért $\xi$ a legkisebb felső korlát.



## 3. Az arkhimédészi tulajdonság

**Tétel:** $\forall a \in \mathbb{R}, a > 0$ és $\forall b \in \mathbb{R}$ esetén $\exists n \in \mathbb{N}$, amelyre $b < n \cdot a$.

**Bizonyítás (Indirekt módon):**

1. Tegyük fel (indirekt feltevés), hogy az állítás hamis. Ekkor: $\exists a \in \mathbb{R}, a > 0$ és $\exists b \in \mathbb{R}$, hogy $\forall n \in \mathbb{N}$ esetén $b \ge n \cdot a$.

2. Legyen $H = \{n \cdot a : n \in \mathbb{N}\}$. Az indirekt feltevés miatt $H$ felülről korlátos halmaz, hiszen $n \cdot a \le b$ minden $n \in \mathbb{N}$ esetén (azaz $b$ egy felső korlát).

3. A szuprémum elv miatt a $H$ halmaznak létezik legkisebb felső korlátja. Jelöljük ezt $\xi$-vel: $\exists \xi = \sup(H)$.

4. Mivel $\xi$ a *legkisebb* felső korlát és $a > 0$, ezért $\xi - a$ már nem felső korlát. Ebből következik, hogy a halmaznak létezik olyan eleme, amely nagyobb ennél. Tehát $\exists n \in \mathbb{N}$, amelyre:
$$n \cdot a > \xi - a$$

5. Rendezzük át az egyenlőtlenséget:
$$(n + 1) \cdot a > \xi$$

6. Ez viszont ellentmondás, hiszen $(n + 1) \in \mathbb{N}$, így $(n + 1) \cdot a$ is eleme a $H$ halmaznak. Mivel $\xi$ felső korlátja $H$-nak, teljesülnie kellene, hogy $(n + 1) \cdot a \le \xi$. Az indirekt feltevés tehát hamis, az állítás igaz.



## 4. A Cantor-tulajdonság

**Tétel:** Legyenek $[a_n, b_n] \subset \mathbb{R}$ korlátos, zárt intervallumok. Ha $[a_{n+1}, b_{n+1}] \subset [a_n, b_n]$ minden $n \in \mathbb{N}$-re (vagyis az intervallumok egymásba vannak skatulyázva), akkor a metszetük nem üres:
$$\bigcap_{n \in \mathbb{N}} [a_n, b_n] \neq \emptyset$$

**Bizonyítás:**

1. Képezzünk két halmazt a végpontokból! Legyen $A := \{a_n : n \in \mathbb{N}\}$ a bal végpontok halmaza, és $B := \{b_n : n \in \mathbb{N}\}$ a jobb végpontok halmaza.

2. Ekkor $a_n \le b_m$ teljesül $\forall n, m \in \mathbb{N}$ esetén, hiszen két eset lehetséges:
   * Ha $n \le m$: az egymásba ágyazottság miatt $a_n \le a_m \le b_m$.
   * Ha $n > m$: az egymásba ágyazottság miatt $a_n \le b_n \le b_m$.

3. A teljességi axióma értelmében ekkor létezik olyan $\xi \in \mathbb{R}$ elválasztó pont, amelyre:
$$a_n \le \xi \le b_m \quad \forall n, m \in \mathbb{N}$$

4. Ebből egyenesen következik (ha $n=m$), hogy minden $n \in \mathbb{N}$-re:
$$a_n \le \xi \le b_n$$

5. Ez pontosan azt jelenti, hogy $\xi \in [a_n, b_n]$ minden $n \in \mathbb{N}$ esetén. Tehát $\xi$ benne van az összes intervallum metszetében:
$$\xi \in \bigcap_{n \in \mathbb{N}} [a_n, b_n]$$
A metszet tehát valóban nem üres.



## 5. Sorozat határértékének egyértelműsége

**Tétel:**
Az $(a_n)$ sorozatnak létezik határértéke, ha $\exists A \in \overline{\mathbb{R}}$, hogy $\forall \varepsilon > 0$ esetén $\exists n_0 \in \mathbb{N}$, hogy $\forall n \ge n_0$ indexre: 
$$a_n \in K_\varepsilon(A)$$
Az előző $A$ szám az $(a_n)$ sorozat határértéke, és ez a szám egyértelmű.

**Bizonyítás (Indirekt módon):**
Tegyük fel indirekt módon, hogy $A_1$ és $A_2$ (ahol $A_1 \neq A_2$) is kielégíti a határérték definícióját.

1. Válasszunk egy olyan $\varepsilon$ sugarat, amelyre $\varepsilon \le \frac{|A_1 - A_2|}{2}$. Ebből következik, hogy a két pont $\varepsilon$-sugarú környezete diszjunkt (nem metszi egymást):
$$K_\varepsilon(A_1) \cap K_\varepsilon(A_2) = \emptyset$$

2. Mivel $\lim a_n = A_1$, ezért az előbb rögzített $\varepsilon$-hoz $\exists n_1 \in \mathbb{N}$ küszöbindex, hogy $\forall n \ge n_1$ esetén:
$$a_n \in K_\varepsilon(A_1)$$

3. Mivel $\lim a_n = A_2$, ezért ugyanahhoz az $\varepsilon$-hoz $\exists n_2 \in \mathbb{N}$ küszöbindex, hogy $\forall n \ge n_2$ esetén:
$$a_n \in K_\varepsilon(A_2)$$

4. Legyen a közös küszöbindex a kettő maximuma: $n_0 = \max\{n_1, n_2\}$. Ekkor $\forall n \ge n_0$ esetén a sorozat elemeinek mindkét feltételnek egyszerre kellene megfelelniük, azaz:
$$a_n \in K_\varepsilon(A_1) \cap K_\varepsilon(A_2) = \emptyset$$

5. Ez viszont ellentmondás, hiszen az $a_n$ elem nem lehet benne egy üres halmazban. Az indirekt feltevés tehát hamis, a határérték valóban egyértelmű.



### 6. A konvergencia és a korlátosság kapcsolata

**Tétel:** Minden konvergens sorozat korlátos. (De nem minden korlátos sorozat konvergens!)

**Bizonyítás:**
1. Legyen $(a_n)$ egy konvergens sorozat, és legyen a határértéke $\lim a_n = A \in \mathbb{R}$.
2. A határérték definíciója miatt $\forall \varepsilon > 0$ : $n_0 \in \mathbb{N}$ küszöbindex.
3. Ehhez az $\varepsilon$-hez létezik egy $n_0$ küszöbindex úgy, hogy minden $n \ge n_0$ esetén:
   $$|a_n - A| < \varepsilon$$
4. A háromszög-egyenlőtlenségből tudjuk, hogy $|a_n| - |A| \le |a_n - A|$. Ezt átrendezve, minden $n \ge n_0$ esetén igaz lesz:
   $$|a_n| < \varepsilon + |A|$$
5. Ez azt jelenti, hogy az $N$-edik tagtól kezdve a sorozat minden eleme korlátos az $(\varepsilon + |A|)$ érték által.
6. A sorozatnak azonban van $N-1$ darab eleme, ami a küszöbindex "előtt" van ($a_1, a_2, \dots, a_{N-1}$). Ez egy véges halmaz, így biztosan van legnagyobb eleme.
7. Legyen a közös korlát $K = \max\{|a_1|, |a_2|, \dots, |a_{N-1}|, \varepsilon + |A|\}$. Ekkor minden $n \in \mathbb{N}$ indexre $|a_n| \le K$, ami definíció szerint pontosan azt jelenti, hogy a sorozat korlátos.





### 7. Monoton részsorozatok létezésére vonatkozó tétel

**Tétel:** Bármely $(a_n)$ valós sorozatnak létezik monoton részsorozata.

**Bizonyítás (Csúcspont-módszer):**
Hívjunk egy $m \in \mathbb{N}$ indexet **"csúcspontnak"**, ha a sorozat utána következő minden tagja kisebb vagy egyenlő nála. Formalizálva: az $m$ index csúcs, ha $\forall n > m$ esetén $a_n \le a_m$.


Két eset lehetséges:

**1. eset: Végtelen sok csúcspont van.**
* Ha végtelen sok csúcs van, akkor jelöljük a csúcsok indexeit növekvő sorrendben: $m_1 < m_2 < m_3 < \dots$
* Mivel az $m_1$ egy csúcs, a nála nagyobb indexű elemek (így az $m_2$ indexű is) nem lehetnek nagyobbak nála, tehát $a_{m_1} \ge a_{m_2}$.
* Mivel $m_2$ is csúcs, $a_{m_2} \ge a_{m_3}$, és így tovább.
* Ezt folytatva az $a_{m_1} \ge a_{m_2} \ge a_{m_3} \ge \dots$ részsorozatot kapjuk, ami egy **monoton csökkenő részsorozat**.

**2. eset: Véges sok csúcspont van.**
* Ha csak véges sok csúcs van (vagy egyáltalán nincs), akkor létezik egy olyan $N \in \mathbb{N}$ index, ami után már *egyáltalán nincs* több csúcspont.
* Válasszunk egy $n_1 > N$ indexet. Mivel $n_1$ **nem csúcs**, ezért kell lennie utána egy $n_2 > n_1$ indexnek úgy, hogy $a_{n_1} < a_{n_2}$.
* Mivel $n_2 > N$, ezért $n_2$ **sem csúcs**, tehát lennie kell utána egy $n_3 > n_2$ indexnek úgy, hogy $a_{n_2} < a_{n_3}$.
* Ezt az eljárást végtelen sokszor ismételhetjük. Így kapunk egy $n_1 < n_2 < n_3 < \dots$ indexsorozatot, amelyre $a_{n_1} < a_{n_2} < a_{n_3} < \dots$ teljesül. Ez pedig egy **szigorúan monoton növekvő részsorozat**.

Mivel a két eset lefedi az összes lehetőséget, és mindkettőben találtunk monoton részsorozatot, a tételt bebizonyítottuk.





## 8. A rendőrelv (Közrefogási elv)

**Tétel:**
Legyenek $(a_n), (b_n)$ és $(c_n)$ sorozatok. Tegyük fel, hogy minden n természetes szám esetén:
$a_n \le b_n \le c_n$.

Ha $\exists \lim a_n = \lim c_n$, akkor $\exists \lim b_n$ is, és $\lim b_n = \lim a_n$.

**Bizonyítás:**
Legyen $A = \lim a_n = \lim c_n$. A határérték típusától függően három esetet különböztetünk meg:

**1. eset: $A \in \mathbb{R}$ (véges határérték)**
* Mivel $\lim a_n = A$, ezért $\forall \varepsilon > 0$ : $\exists n_1 \in \mathbb{N}$ : $\forall n \ge n_1$ : $a_n \in K_\varepsilon(A)$, azaz $A - \varepsilon < a_n < A + \varepsilon$.
* Mivel $\lim c_n = A$, ezért $\forall \varepsilon > 0$ : $\exists n_2 \in \mathbb{N}$ : $\forall n \ge n_2$ : $c_n \in K_\varepsilon(A)$, azaz $A - \varepsilon < c_n < A + \varepsilon$.
* Legyen a közös küszöbindex $n_0 = \max\{n_1, n_2, N\}$. Ekkor $\forall n \ge n_0$ esetén az összes feltétel egyszerre teljesül:
$$A - \varepsilon < a_n \le b_n \le c_n < A + \varepsilon$$
* Ebből egyértelműen következik, hogy $A - \varepsilon < b_n < A + \varepsilon$, tehát $\forall \varepsilon > 0$-hoz $\exists n_0 \in \mathbb{N}$, hogy $\forall n \ge n_0$ esetén $b_n \in K_\varepsilon(A)$.
Így $\lim b_n = A$.

**2. eset: $A = \infty$**
* Mivel $\lim a_n = \infty$, ezért a definíció szerint $\forall P > 0$ számhoz $\exists n_1 \in \mathbb{N}$ : $\forall n \ge n_1$ : $a_n > P$.
* Legyen $n_0 = \max\{n_1, N\}$. Ekkor $\forall n \ge n_0$ esetén a tétel feltételét is belevéve felírható:
$$b_n \ge a_n > P$$
* Mivel $\forall P > 0$-ra találtunk olyan $n_0$ küszöbindexet, hogy $n \ge n_0$ esetén $b_n > P$, ezért $\lim b_n = \infty$.

**3. eset: $A = -\infty$**
* Mivel $\lim c_n = -\infty$, ezért a definíció szerint $\forall P < 0$ számhoz $\exists n_1 \in \mathbb{N}$ : $\forall n \ge n_1$ : $c_n < P$.
* Legyen $n_0 = \max\{n_1, N\}$. Ekkor $\forall n \ge n_0$ esetén a tétel feltételét is belevéve felírható:
$$b_n \le c_n < P$$
* Mivel $\forall P < 0$-ra találtunk olyan $n_0$ küszöbindexet, hogy $n \ge n_0$ esetén $b_n < P$, ezért $\lim b_n = -\infty$.



## 10. Műveletek nullasorozatokkal

**Tétel:**
Tegyük fel, hogy az $(a_n)$ és $(b_n)$ sorozat is nullsorozat.
Ekkor:
1. $(a_n + b_n)$ is nullsorozat.
2. Ha $(c_n)$ korlátos, akkor az $(a_n \cdot c_n)$ is nullsorozat.
3. $(a_n \cdot b_n)$ is nullsorozat.

**Bizonyítás:**

**1. Összegük is nullsorozat.** 

Mivel $\lim a_n = 0$ és $\lim b_n = 0$:
* $\forall \varepsilon > 0$ :  $\exists n_1 \in \mathbb{N}$ : $\forall n \ge n_1$ : $|a_n| < \frac{\varepsilon}{2}$
* $\forall \varepsilon > 0$ :  $\exists n_2 \in \mathbb{N}$ : $\forall n \ge n_2$ : $|b_n| < \frac{\varepsilon}{2}$
* Ebből következik, hogy $\forall \varepsilon > 0$-hoz létezik egy közös küszöbindex, ami $n_0 = \max\{n_1, n_2\}$. Erre $\forall n \ge n_0$ esetén a háromszög-egyenlőtlenséget alkalmazva igaz, hogy:
$$|a_n + b_n| \le |a_n| + |b_n| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon$$
* Tehát $\lim(a_n + b_n) = 0$.

**2. Korlátos $\cdot$ nullsorozat = nullsorozat.** 

Mivel $(c_n)$ korlátos, ezért $\exists K \in \mathbb{R}$, hogy $\forall n \in \mathbb{N}$ esetén: $|c_n| \le K$.
* Mivel $\lim a_n = 0$, ezért a definíció alapján $\forall \varepsilon > 0$-hoz (így az $\frac{\varepsilon}{K} > 0$ számhoz is) $\exists n_0$ küszöbindex, hogy $\forall n \ge n_0$ esetén: $|a_n| < \frac{\varepsilon}{K}$.
* Ebből következik, hogy $\forall \varepsilon > 0$-hoz $\exists n_0$, hogy $\forall n \ge n_0$ esetén:
$$|a_n c_n| = |a_n| \cdot |c_n| < \frac{\varepsilon}{K} \cdot K = \varepsilon$$
* Tehát $\lim(a_n c_n) = 0$.

**3. Nullsorozatok szorzata.** 

Mivel $(b_n)$ nullsorozat, ezért konvergens. Minden konvergens sorozat korlátos, tehát $(b_n)$ is korlátos. 
* Innentől kezdve pontosan alkalmazható a fenti **2. pont**, ahol a korlátos sorozat szerepét most a $(b_n)$ tölti be. Így az $(a_n b_n)$ szorzat is nullsorozat.



## 13. Monoton növő sorozat határértéke (véges és végtelen eset)

**Tétel:**
* Ha az $(a_n)$ sorozat monoton nő és felülről korlátos, akkor konvergens is, és $\lim a_n = \sup\{a_n : n \in \mathbb{N}\}$.
* Ha az $(a_n)$ sorozat monoton nő és nem felülről korlátos, akkor $\lim a_n = \infty$.

**Bizonyítás:**

**1. eset: Az $(a_n)$ sorozat felülről korlátos (véges határérték)**
* Mivel az $(a_n)$ halmazként felülről korlátos (és nem üres), a szuprémum elv miatt létezik legkisebb felső korlátja a valós számok halmazán: $\exists \xi = \sup\{a_n : n \in \mathbb{N}\} \in \mathbb{R}$.
* Mivel $\xi$ felső korlát, ezért $\forall n \in \mathbb{N}$ esetén: $a_n \le \xi$.
* Mivel $\xi$ a *legkisebb* felső korlát, ezért bármely $\varepsilon > 0$ esetén a $\xi - \varepsilon$ szám már nem felső korlát. Ebből következik, hogy $\exists n_0 \in \mathbb{N}$ index, amelyre a sorozatelem nagyobb ennél: $\xi - \varepsilon < a_{n_0}$.
* Mivel a sorozat monoton nő, ezért $\forall n \ge n_0$ indexre $a_{n_0} \le a_n$. A fentieket egyenlőtlenségláncba fűzve:
$$\xi - \varepsilon < a_{n_0} \le a_n \le \xi$$
* Ebből látszik, hogy $\forall \varepsilon > 0$-hoz $\exists n_0 \in \mathbb{N}$, hogy $\forall n \ge n_0$ esetén az $a_n$ elemek $\varepsilon$-nál közelebb vannak $\xi$-hez. Tehát $\lim a_n = \xi$.

**2. eset: Az $(a_n)$ sorozat nem felülről korlátos (végtelen határérték)**
* Mivel $(a_n)$ felülről nem korlátos, ezért bármilyen rögzített (akár tetszőlegesen nagy) $K \in \mathbb{R}$ számhoz $\exists n_0 \in \mathbb{N}$ index, hogy a sorozatelem túllépi azt: $a_{n_0} > K$.
* Mivel a sorozat monoton nő, ezért $\forall n \ge n_0$ indexre $a_{n_0} \le a_n$. Ezt összerakva kapjuk:
$$K < a_{n_0} \le a_n$$
* Tehát $\forall K \in \mathbb{R}$-hez $\exists n_0 \in \mathbb{N}$, hogy $\forall n \ge n_0$ esetén $a_n > K$. Ez pontosan a $+\infty$-hez tartás definíciója, így $\lim a_n = \infty$.