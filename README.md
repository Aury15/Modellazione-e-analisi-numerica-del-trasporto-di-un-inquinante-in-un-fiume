# Modellazione-e-analisi-numerica-del-trasporto-di-un-inquinante-in-un-fiume
# Numerical Modeling of 1D Advection-Diffusion Equation

Questo repository contiene il progetto finale sviluppato per il corso di **Calcolo Scientifico** presso la *Sapienza Università di Roma*. Il lavoro si concentra sulla modellazione, simulazione e analisi numerica del trasporto e della diffusione di un inquinante all'interno di un corso d'acqua unidimensionale.

## 📝 Descrizione del Progetto

Il fenomeno fisico dell'evoluzione della concentrazione di inquinante $u(x,t)$ è modellato a partire dalla legge di conservazione della massa, considerando due contributi principali:
1.**Avvezione (Trasporto):** dovuto alla corrente del fiume, con velocità costante $a = 1 \, m/s$.
2.**Diffusione:** governata dalla legge di Fick con un coefficiente di diffusione $\mu > 0$.

L'equazione differenziale parziale (PDE) risultante è:

$$u_t + a u_x = \mu u_{xx}$$

### Metodologia Numerica
* **Discretizzazione Spaziale:** Metodo delle Linee (MoL) con **Differenze Finite Centrate** (accuratezza del secondo ordine: $\mathcal{O}(h^2)$).
* **Discretizzazione Temporale:** **Eulero Esplicito** (accuratezza del primo ordine: $\mathcal{O}(\Delta t)$).
* **Analisi di Stabilità:** Condotta tramite l'analisi di **Von Neumann** nel caso ausiliario con condizioni periodiche, ricavando la condizione restrittiva sul passo temporale:

$$\Delta t \le \min \left( 2\mu, \frac{h^2}{2\mu} \right)$$

---

## 📁 Struttura della Repository

* `notebooks/`: Contiene il Jupyter Notebook (`.ipynb`) con l'implementazione interattiva del solutore e la generazione dei grafici.
* `report/`: Il report tecnico dettagliato scritto in LaTeX (analisi di consistenza, stabilità e convergenza di Lax-Richtmyer).
* `presentation/`: Le slide utilizzate per la discussione orale dell'esame.
* `img/`: Cartella contenente i grafici delle simulazioni e dell'analisi d'errore.

---
