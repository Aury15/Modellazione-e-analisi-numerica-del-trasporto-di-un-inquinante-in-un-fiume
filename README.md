# Numerical Modeling of 1D Advection-Diffusion Equation

Questo repository contiene il progetto finale sviluppato per il corso di **Calcolo Scientifico** presso la *Sapienza Università di Roma*. Il lavoro si concentra sulla modellazione, simulazione e analisi numerica del trasporto e della diffusione di un inquinante all'interno di un corso d'acqua unidimensionale.

## 👥 Autori
* **Aurora Di Giovanna**
* **Eleonora De Cicco**
* **Giada Manfredi**

---

## 📝 Descrizione del Progetto

Il fenomeno fisico dell'evoluzione della concentrazione di inquinante $u(x,t)$ è modellato a partire dalla legge di conservazione della massa, considerando due contributi principali: le componenti di avvezione (trasporto dovuto alla corrente del fiume) e di diffusione (governata dalla legge di Fick).

L'equazione differenziale parziale (PDE) risultante è:

$$u_t + a u_x = \mu u_{xx}$$

### 🛠️ Metodologia Numerica e Flusso di Analisi

Il nucleo del progetto segue un rigoroso approccio analitico e computazionale diviso nelle seguenti fasi fondamentali:

1. **Il Caso Periodico Ausiliario:** Inizialmente viene studiato un problema semplificato con condizioni al bordo periodiche. Per questa configurazione si ricava la soluzione esatta del problema continuo tramite lo sviluppo in serie di Fourier.
   
2. **Analisi di Stabilità di Von Neumann:** Sfruttando la natura del caso periodico, si applica l'analisi di Von Neumann (o del fattore di amplificazione) sullo schema discretizzato con **Differenze Finite Centrate** nello spazio (accuratezza del secondo ordine $$\mathcal{O}(h^2)$$) ed **Eulero Esplicito** nel tempo (accuratezza del primo ordine $$\mathcal{O}(\Delta t)$$). Da questa analisi si ricava la condizione restrittiva sul passo temporale:
   $$\Delta t \le \min \left( 2\mu, \frac{h^2}{2\mu} \right)$$

3. **Consistenza e Convergenza secondo Lax:** Viene dimostrata analiticamente la consistenza dello schema numerico rispetto alla PDE originale. Grazie al **Teorema di Equivalenza di Lax (Lax-Richtmyer)**, l'aver garantito la consistenza dello schema e la sua stabilità (sotto la condizione precedentemente ricavata) assicura matematicamente la *convergenza* della soluzione numerica a quella analitica.

4. **Risoluzione del Problema Reale (Dirichlet-Neumann):** Infine, la condizione di stabilità critica ricavata nel caso periodico viene ereditata e applicata per risolvere il problema fisico reale su un dominio limitato. Questo scenario finale prevede l'immissione costante di inquinante dall'estremo sinistro attraverso una condizione di **Dirichlet** ($$u(0,t)=1$$) e il deflusso libero all'estremo destro modellato con una condizione di **Neumann** ($$u_x(L,t)=0$$).

---

## 📁 Struttura della Repository

* `notebooks/`: Contiene il Jupyter Notebook (`.ipynb`) con l'implementazione interattiva del solutore e la generazione dei grafici.
* `report/`: Il report tecnico dettagliato scritto in LaTeX (`UltimaCalcolo.pdf`).
* `presentation/`: Le slide utilizzate per la discussione orale dell'esame.
* `img/`: Cartella contenente i grafici delle simulazioni, dei test di stabilità e dell'analisi d'errore.

---

## 🚀 Come Iniziare

### Prerequisiti

Il progetto richiede Python 3 e l'ambiente Jupyter. Assicurati di installare tutte le dipendenze necessarie:

```bash
pip install -r requirements.txt
