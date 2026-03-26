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
Vagyis $A_n$ igaz $\forall n \in \mathbb{N}$-re.



## 2. Szuprémum elv

**Tétel:** Bármely nem üres, felülről korlátos $H \subseteq \mathbb{R}$ halmaz felső korlátai között létezik legkisebb.

**Bizonyítás:**

Legyen $A$ a $H$ halmaz összes felső korlátjának halmaza ($A := \{a \in \mathbb{R} : a \text{ felső korlátja } H\text{-nak}\}$).

1. Mivel $H$ nem üres és felülről korlátos, ezért $A$ sem üres. A felső korlát definíciójából adódik, hogy bármely $h \in H$ és $a \in A$ elemre igaz, hogy $h \le a$.

2. A teljességi axióma értelmében ekkor létezik olyan $\xi \in \mathbb{R}$ elválasztó pont, amelyre minden $h \in H$ és $a \in A$ esetén teljesül, hogy:
$$h \le \xi \le a$$

3. Ebből az egyenlőtlenségből két dolog is következik:

* Mivel $h \le \xi$ minden $H$-beli elemre, ezért $\xi$ egy felső korlátja a $H$ halmaznak (azaz $\xi \in A$).
* Mivel $\xi \le a$ minden $A$-beli elemre (vagyis minden létező felső korlátra), ezért $\xi$ a legkisebb felső korlát (szuprémum).


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




## 9. A határérték és a rendezés kapcsolata

**Tétel:** Legyenek $(a_n)$ és $(b_n)$ konvergens sorozatok, $\lim a_n = A$ és $\lim b_n = B$. Ha egy $N$ indextől kezdve minden $n \ge N$ esetén $a_n \le b_n$, akkor $A \le B$.

**Bizonyítás (indirekt):**

1. Tegyük fel az állítás ellenkezőjét, azaz hogy $A > B$.
2. Válasszuk a két határérték távolságának a felét: $\varepsilon = \frac{A - B}{2} > 0$. 
3. A konvergencia miatt elég nagy $n$ indexekre az $(a_n)$ és $(b_n)$ is beleesik a saját határértéke $\varepsilon$ sugarú környezetébe. Így létezik olyan $n_0 \ge N$ közös küszöbindex, hogy minden $n \ge n_0$ esetén:
   $$b_n < B + \varepsilon \quad \text{és} \quad A - \varepsilon < a_n$$
4. Mivel $B + \varepsilon = \frac{A + B}{2} = A - \varepsilon$, a fenti két egyenlőtlenséget összekapcsolhatjuk:
   $$b_n < \frac{A + B}{2} < a_n$$
5. Ebből egyértelműen következik, hogy $b_n < a_n$, ami **ellentmond** a kiinduló feltételünknek ($a_n \le b_n$). 

Tehát az indirekt feltevésünk hamis volt, így biztosan **$A \le B$**.





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




## 11. Konvergens sorozatok szorzatára vonatkozó tétel

**Tétel:** Ha az $(a_n)$ és $(b_n)$ sorozatok konvergensek, és $\lim a_n = A$, valamint $\lim b_n = B$, akkor az $(a_n b_n)$ szorzatsorozat is konvergens, és $\lim (a_n b_n) = A \cdot B$.

**Bizonyítás:**

1. Írjuk fel a szorzat és a határértékek szorzatának különbségét. Alkalmazzunk egy algebrai trükköt (hozzáadunk és kivonunk $a_n B$-t), majd használjuk a háromszög-egyenlőtlenséget:
   $$|a_n b_n - A B| = |a_n b_n - a_n B + a_n B - A B| \le |a_n||b_n - B| + |B||a_n - A|$$
2. Mivel az $(a_n)$ sorozat konvergens, a korábban tanult tétel alapján **korlátos is**, tehát létezik olyan $K > 0$ szám, hogy minden $n$-re $|a_n| \le K$. Így az egyenlőtlenség:
   $$|a_n b_n - A B| \le K|b_n - B| + |B||a_n - A|$$
3. A konvergencia miatt a jobb oldalon szereplő $|b_n - B|$ és $|a_n - A|$ tényezők egy adott küszöbindex után tetszőlegesen (bármilyen $\varepsilon$-nál) kisebbé tehetők. Így a két tag összege is 0-hoz tart, amivel a tételt beláttuk.







## 12. Konvergens sorozatok hányadosára vonatkozó tétel

**Tétel:** Ha az $(a_n)$ és $(b_n)$ sorozatok konvergensek, $\lim a_n = A$, és $\lim b_n = B \neq 0$ (továbbá minden $n$-re $b_n \neq 0$), akkor az $\left(\frac{a_n}{b_n}\right)$ hányadossorozat is konvergens, és $\lim \frac{a_n}{b_n} = \frac{A}{B}$.

**Bizonyítás:**

1. Elegendő csak azt belátni, hogy az $\left(\frac{1}{b_n}\right)$ reciprok sorozat konvergens és a határértéke $\frac{1}{B}$. Ha ugyanis ez igaz, akkor a fenti **szorzatszabály (11. tétel)** alapján: $\lim \left(a_n \cdot \frac{1}{b_n}\right) = A \cdot \frac{1}{B} = \frac{A}{B}$.
2. Vizsgáljuk meg a reciprok sorozat és a várt határérték különbségét közös nevezőre hozással:
   $$\left|\frac{1}{b_n} - \frac{1}{B}\right| = \frac{|B - b_n|}{|b_n||B|}$$
3. Mivel $b_n \to B$ és $B \neq 0$, egy kellően nagy indextől kezdve a sorozat elemei elég közel kerülnek $B$-hez (például biztosan nagyobbak lesznek, mint $B$ felének az abszolút értéke), azaz: $|b_n| > \frac{|B|}{2}$.
4. Ezt az alsó becslést a nevezőbe beírva a tört értékét felülről becsülhetjük:
   $$\left|\frac{1}{b_n} - \frac{1}{B}\right| < \frac{2}{|B|^2} \cdot |b_n - B|$$
5. Mivel $\lim b_n = B$, a jobb oldalon lévő $|b_n - B|$ érték 0-hoz tart, ami magával húzza a bal oldalt is, tehát a reciprok sorozat valóban $\frac{1}{B}$-hez tart.





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




## 14. Az $a_n = \left(1 + \frac{1}{n}\right)^n$ sorozat konvergenciája

**Tétel:** Az $a_n = \left(1 + \frac{1}{n}\right)^n$ ($n \in \mathbb{N}^+$) sorozat konvergens. (A határértékét $e$-vel jelöljük).

**Bizonyítás:**
A konvergenciát a Weierstrass-tétel (ha egy sorozat monoton és korlátos, akkor konvergens) segítségével látjuk be.

1. **Monotonitás:** Alkalmazzuk a számtani és mértani közepek közötti egyenlőtlenséget $n$ darab $\left(1 + \frac{1}{n}\right)$ és $1$ darab $1$-es számra:
   $$\sqrt[n+1]{\left(1 + \frac{1}{n}\right)^n \cdot 1} < \frac{n \left(1 + \frac{1}{n}\right) + 1}{n + 1} = \frac{n + 1 + 1}{n + 1} = 1 + \frac{1}{n+1}$$
   Mindkét oldalt $(n+1)$-edik hatványra emelve kapjuk, hogy $a_n < a_{n+1}$, tehát a sorozat **szigorúan monoton nő**.
2. **Korlátosság:** Hasonlóan, az egyenlőtlenséget megfelelően alkalmazva bizonyítható, hogy a $b_n = \left(1 + \frac{1}{n}\right)^{n+1}$ sorozat szigorúan monoton csökken. Mivel minden $n$-re $a_n < b_n$, és a $(b_n)$ csökkenő, ezért bármelyik eleme (pl. $b_1 = 4$) **felső korlátja** az $(a_n)$ sorozatnak.
3. Mivel $(a_n)$ monoton nő és felülről korlátos, a sorozat konvergens.






## 15. Newton-féle iterációs eljárás $m$-edik gyökök keresésére

**Tétel:** Adott $A > 0$ valós szám és $m \ge 2$ egész szám. A tetszőleges $x_1 > 0$ kezdőértékből indított
$$x_{n+1} = \frac{1}{m} \left( (m-1)x_n + \frac{A}{x_n^{m-1}} \right)$$
rekurzív sorozat konvergens, és $\lim x_n = \sqrt[m]{A}$.

**Bizonyítás:**

1. **Alulról korlátosság:** Alkalmazzuk a számtani-mértani közép egyenlőtlenséget $(m-1)$ darab $x_n$ és $1$ darab $\frac{A}{x_n^{m-1}}$ tagra:
   $$x_{n+1} = \frac{(m-1)x_n + \frac{A}{x_n^{m-1}}}{m} \ge \sqrt[m]{x_n^{m-1} \cdot \frac{A}{x_n^{m-1}}} = \sqrt[m]{A}$$
   Tehát $n \ge 1$ esetén az elemekre igaz, hogy $x_{n+1} \ge \sqrt[m]{A}$.
2. **Monotonitás:** Mivel $x_n \ge \sqrt[m]{A}$ (ha $n \ge 2$), ezért $x_n^m \ge A$, amiből leosztva kapjuk, hogy $\frac{A}{x_n^{m-1}} \le x_n$. Ezt beírva a rekurzióba:
   $$x_{n+1} \le \frac{(m-1)x_n + x_n}{m} = \frac{m \cdot x_n}{m} = x_n$$
   A sorozat a második tagtól kezdve **monoton csökken** és **alulról korlátos**, így biztosan konvergens.
3. **Határérték:** Jelöljük a határértéket $x$-szel. Ha $n \to \infty$, akkor $x_{n+1}$ és $x_n$ is $x$-hez tart. Ezt visszaírva a képletbe: $x = \frac{1}{m} \left( (m-1)x + \frac{A}{x^{m-1}} \right)$. Ezt átrendezve az $x^m = A$ egyenletet kapjuk, amiből $x = \sqrt[m]{A}$.






## 16. A Cauchy-féle konvergenciakritérium sorozatokra

**Tétel:** Egy valós $(a_n)$ sorozat akkor és csak akkor konvergens, ha **Cauchy-sorozat**, azaz bármely $\varepsilon > 0$ esetén létezik olyan $N$ küszöbindex, hogy minden $n, m \ge N$ indexre $|a_n - a_m| < \varepsilon$.

**Bizonyítás:**

**1. irány (Ha konvergens, akkor Cauchy-sorozat):**
Tegyük fel, hogy $\lim a_n = A$. A konvergencia miatt adott $\frac{\varepsilon}{2} > 0$ értékhez létezik egy $N$ küszöbindex, amely után minden elem $\frac{\varepsilon}{2}$-nél közelebb van $A$-hoz. A háromszög-egyenlőtlenséget használva két tetszőleges $n, m \ge N$ elemre:
$$|a_n - a_m| = |a_n - A + A - a_m| \le |a_n - A| + |A - a_m| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon$$
Tehát a sorozat valóban Cauchy-tulajdonságú.

**2. irány (Ha Cauchy-sorozat, akkor konvergens):**
1. Minden Cauchy-sorozat **korlátos**, mert egy indextől kezdve az összes tag egy véges hosszúságú (például $\varepsilon=1$ sugarú) intervallumban marad.
2. A Bolzano–Weierstrass-tétel értelmében minden korlátos sorozatnak van **konvergens részsorozata**. Jelöljük a részsorozat határértékét $A$-val.
3. Mivel a Cauchy-tulajdonság miatt a végtelen felé haladva az elemek tetszőlegesen közel kerülnek *egymáshoz*, és a részsorozat révén végtelen sok elem *megközelíti $A$-t*, ezért maguknak a sorozat eredeti tagjainak is muszáj $A$-hoz tartaniuk.