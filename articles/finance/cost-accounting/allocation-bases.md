---
title: Basi di allocazione
description: Vengono fornite le informazioni sulle basi di allocazione. Le basi di allocazione sono componenti chiave della contabilità industriale che vengono utilizzati principalmente per allocare i costi generali.
author: AndersGirke
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMAllocationBaseDetail, CAMFormulaAllocationBaseDetail, CAMAllocationBasePreview, CAMAllocationBase, CAMCostAllocationRule, CAMPredefinedMemberAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 223174
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4b6d4e7fae1df977a5db311d3ea662a5eb3ffd30
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260831"
---
# <a name="allocation-bases"></a>Basi di allocazione 

[!include [banner](../includes/banner.md)]

La base di allocazione è la base su cui la contabilità industriale assegna i costi generali. La base di allocazione può essere una quantità, ad esempio le ore-macchina utilizzate, i kilowattora (kWh) consumati o la metratura occupata. Le basi di allocazione vengono utilizzate principalmente per allocare i costi generali alle scorte prodotte. Ad esempio, un reparto IT alloca le spese sostenute in base al numero di computer utilizzati in ciascun reparto.

Sono disponibili tre tipi di base di allocazione nella contabilità industriale:

- Basi di allocazione membro di dimensione predefinita
- Basi di allocazione gerarchia
- Basi di allocazione formula

## <a name="predefined-dimension-member-allocation-bases"></a>Basi di allocazione membro di dimensione predefinita

Le basi di allocazione del membro di dimensione predefinite vengono create automaticamente quando un membro di dimensione di uno dei seguenti tipi viene creato:

- Membri di dimensione statistica
- Membri di dimensione elemento di costo

> [!NOTE]
> Le basi di allocazione di membri di dimensione predefinite basate su un membro di dimensione elemento di costo considerano solo i valori del fornitore dell'origine dati, quali contabilità generale oppure budget.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>Esempio 1: Utilizzare un membro di dimensione elemento di costo come base di allocazione
In questo esempio viene illustrato come creare una regola di allocazione costi per allocare l'elemento di costo 10002 (assicurazione dipendente) al saldo registrato nell'elemento di costo 10001 (retribuzioni). La regola di allocazione è definita in base al rapporto delle retribuzioni di ciascun reparto con gli stipendi totali. (Revisione necessaria)

Nella contabilità generale, il piano dei conti è definito come indicato di seguito.

| Piano dei conti | Conto principale | Descrizione        | Tipo di conto principale |
|------------------|--------------|--------------------|-------------------|
| Condiviso           | 10001        | Stipendi           | Gestione spese           |
| Condiviso           | 10002        | Assicurazione dipendente | Gestione spese           |

Definire una dimensione elemento di costo e configurare il connettore dati. Dopo che i dati vengono importati, le seguenti voci vengono create nella contabilità industriale.

**Membri di dimensione elemento di costo**

| Nome dimensione elemento di costo | Elemento di costo |  Descrizione       | Tipo    |
|-----------------------------|--------------|--------------------|---------|
| Elementi di costo               | 10001        | Stipendi           | Primario |
| Elementi di costo               | 10002        | Assicurazione dipendente | Primario |

**Basi di allocazione membro di dimensione predefinita** 

| Nome  | Descrizione        | Dimensione elemento di costo |
|-------|--------------------|------------------------|
| 10001 | Stipendi           | Elementi di costo          |
| 10002 | Assicurazione dipendente | Elementi di costo          |

Nella contabilità generale, le seguenti voci sono state registrate:

- Le voci che indicano il conto principale Stipendi provengono dal sistema di gestione delle retribuzioni e vengono registrate nei centri di costo.
- Le spese per l'assicurazione dipendente vengono registrate manualmente in un centro di costo predefinito.

| Data di registrazione | Centro di costo |  Descrizione        | Conto principale |  Descrizione       | Importo nella valuta di contabilizzazione |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | Risorse umane                  | 10001        | Stipendi           | 2.000,00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | Stipendi           | 5.000,00                      |
| 03-01-2017      | CC003       | TS                  | 10001        | Stipendi           | 3.000,00                      |
| 03-01-2017      | CC099       | Centro di costo predefinito | 10002        | Assicurazione dipendente | 1.000,00                      |

Dopo l'elaborazione dei dati di origine della contabilità generale, le seguenti voci vengono create nella contabilità industriale.

**Voci di costo**

| Oggetto di costo |  Descrizione        | Elemento di costo  |  Descrizione       | Comportamento costo   |Importo|Data di registrazione|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | Risorse umane                  | 10001         | Stipendi           | Non classificato    |2.000,00|  03-01-2017    |
| CC002       | FI                  | 10001         | Stipendi           | Non classificato    |5.000,00|     03-01-2017         |
| CC003       | TS                  | 10001         | Stipendi           | Non classificato    |3.000,00|      03-01-2017        |
| CC099       | Centro di costo predefinito | 10002         | Assicurazione dipendente | Non classificato    |1.000,00|      03-01-2017       |

In questo esempio semplificato viene creata una regola di allocazione costi per allocare l'elemento di costo 10002 (assicurazione dipendente) relativo al saldo registrato nell'elemento di costo 10001 (retribuzioni).

**Regola di distribuzione costi**

| Nodo gerarchia dimensioni di oggetto di costo | Nodo gerarchia dimensioni di elemento di costo | Comportamento costo | Base di allocazione |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | Non classificato  | 10001           |

**Eseguire il calcolo generale**

Una volta che l'elemento di costo 10001 (retribuzioni) viene applicato come base di allocazione, il risultato del calcolo generale è il seguente.

| Oggetto di costo | Descrizione | Grandezza |   Fattore di allocazione         | Importo |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | Risorse umane          | 2.000     | (2.000 ÷ 10.000) × 1.000,00 | 200,00 |
| CC002       | FI          | 5.000     | (5.000 ÷ 10.000) × 1.000,00 | 500,00 |
| CC003       | TS          | 3.000     | (3.000 ÷ 10.000) × 1.000,00 | 300,00 |

**Giornale di registrazione**

| Giornale di registrazione | Tipo giornale di registrazione                          | Periodo di calendario fiscale | Anno | Periodo   | Versione                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | Giornale di registrazione calcolo distribuzione costo | Fiscale                 | 2017 | Periodo 1 | Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1 |

**Scritture contabili saldo oggetto di costo**

| Data di registrazione | Oggetto di costo | Descrizione         | Elemento di costo | Descrizione        | Comportamento costo |  Importo  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | Centro di costo predefinito | 10002        | Assicurazione dipendente | Non classificato  | 1.000,00 |

**Voci di costo**

| Oggetto di costo |  Descrizione        | Elemento di costo |    Descrizione     | Comportamento costo | Importo    | Data di registrazione |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | Centro di costo predefinito | 10002        | Assicurazione dipendente | Non classificato  | -1.000,00 | 31-01-2017      |
| CC001       | Risorse umane                  | 10002        | Assicurazione dipendente | Non classificato  | 200,00    | 31-01-2017      |
| CC002       | FI                  | 10002        | Assicurazione dipendente | Non classificato  | 500,00    | 31-01-2017      |
| CC099       | TS                  | 10002        | Assicurazione dipendente | Non classificato  | 300,00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>Esempio 2: Utilizzare un membro di dimensione statistica come base di allocazione

I membri di dimensione statistica possono essere utilizzati come base di allocazione per definire i criteri o specificare il consumo non monetario degli oggetti di costo. È possibile creare manualmente i membri di dimensione statistica o eseguire l'importazione da un file utilizzando lo strumento di importazione o esportazione della gestione dei dati.

**Membri di dimensione statistica**

| Nome dimensione statistica | Elemento statistico | Descrizione               | Unità |
|----------------------------|---------------------|---------------------------|------|
| Elementi statistici       | FTE                 | Dipendenti a tempo pieno       | Cadauno   |
| Elementi statistici       | Elettricità         | Consumo di elettricità   | kWh  |

Quando un membro di dimensione statistica viene salvato, un record corrispondente viene creato nelle basi di allocazione del membro di dimensione predefinite.

**Basi di allocazione membro di dimensione predefinita**

| Nome        | Descrizione             | Dimensione elemento statistico |
|-------------|-------------------------|-------------------------------|
| FTE         | Dipendenti a tempo pieno     | Elementi statistici          |
| Elettricità | Consumo di elettricità | Elementi statistici          |

Le misure statistiche possono derivare da diverse origini:

- Il consumo di elettricità può essere misurato da contatori installati in varie aree diverse della società.
- Le tabelle contengono le misure statistiche. Ad esempio, la tabella HcmEmployment contiene l'elenco di tutti i dipendenti e dei centri di costo per cui lavorano.

| Nome       | Centro di costo |  Descrizione  | Tipo di lavoratore |
|------------|-------------|----|-------------|
| Dipendente A | CC001       | Risorse umane | Dipendente    |
| Dipendente B | CC002       | FI | Dipendente    |
| Dipendente C | CC002       | FI | Dipendente    |
| Dipendente D | CC003       | TS | Dipendente    |
| Dipendente F | CC003       | TS | Dipendente    |

> [!NOTE]
> Tutte le tabelle che contengono dimensioni finanziarie possono essere utilizzate come origini delle misure statistiche.

La contabilità industriale supporta una raccolta di misure statistiche utilizzando le seguenti connessioni dati:

- Strumento di esportazione/importazione della gestione dati 
- Misure statistiche

Per recuperare le misure statistiche dal sistema, è necessario un modello provider misure statistiche. Per altre informazioni vedere Modello provider misure statistiche. (Si aggiungerà il collegamento quando l'argomento è stato scritto).

**Modelli provider misure statistiche**

| Nome  | Funzione | Tabella di origine  | Campo somma      | Campo data     |
|-------|----------|---------------|----------------|----------------|
| FTE | Conteggio    | HcmEmployment | Non applicabile | Non applicabile |

Dopo l'elaborazione dei dati di origine delle misure statistiche, le seguenti voci vengono create nella contabilità industriale.

**Voci statistiche**

| Oggetto di costo | Descrizione      | Data di registrazione | Membro di dimensione statistica | Descrizione         | Grandezza |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Risorse umane               | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 1,00      |
| CC002       | FI               | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 2.00      |
| CC003       | TS               | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 2.00      |

Di seguito è riportato un esempio di regola di distribuzione costi se la base di allocazione del membro di dimensione predefinita di FTE è assegnata come base di allocazione.

| Oggetto di costo | Descrizione  | Grandezza | Fattore di allocazione |
|-------------|------|-----------|-------------------|
| CC001       | Risorse umane   | 1,00      | (1/5) × Importo    |
| CC002       | FI   | 2.00      | (2/5) × Importo    |
| CC003       | TS   | 2.00      | (2/5) × Importo    |

È possibile utilizzare l'entità di dati delle misure statistiche per importare le misure statistiche nella contabilità industriale. È inoltre possibile utilizzare lo strumento di importazione o esportazione della gestione dei dati. In Excel, il consumo di elettricità viene registrato come indicato di seguito.

| Data di registrazione | Membro di dimensione | Grandezza | Identificatore di origine |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | Elettricità       |
| 31-01-2017      | CC002            | 4,100.00  | Elettricità       |
| 31-01-2017      | CC003            | 15.000,00 | Elettricità       |

Dopo l'elaborazione dei dati di origine delle misure statistiche, le seguenti voci vengono create nella contabilità industriale.

**Voci statistiche**

| Oggetto di costo |    | Data di registrazione | Membro di dimensione statistica |    Descrizione          | Grandezza |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Risorse umane | 31-01-2017      | Elettricità                  | Consumo di elettricità | 2,450.00  |
| CC002       | FI | 31-01-2017      | Elettricità                  | Consumo di elettricità | 4,100.00  |
| CC003       | TS | 31-01-2017      | Elettricità                  | Consumo di elettricità | 15.000,00 |

Di seguito è riportato un esempio di regola di distribuzione costi se la base di allocazione del membro di dimensione predefinita dell'elettricità è assegnata come base di allocazione.

| Oggetto di costo | Descrizione  | Grandezza | Fattore di allocazione          |
|-------------|------|-----------|----------------------------|
| CC001       | Risorse umane   | 2,450.00  | (2,450 ÷ 21,550) × Importo  |
| CC002       | FI   | 4,100.00  | (4,100 ÷ 21,550) × Importo  |
| CC003       | TS   | 15.000,00 | (15,000 ÷ 21,550) × Importo |

## <a name="hierarchy-allocation-bases"></a>Basi di allocazione gerarchia

I contabili possono creare manualmente le basi di allocazione di gerarchia applicando un nodo di gerarchia di dimensione oggetto di costo a una base di allocazione. In questo modo, è possibile limitare l'intervallo delle basi di allocazione del membro di dimensione predefinite originali. Una base di allocazione del membro di dimensione predefinita può essere utilizzata per creare più basi di allocazione della gerarchia. Gli intervalli possono essere gestiti nella gerarchia di dimensione oggetto di costo associata alle basi di allocazione della gerarchia.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>Esempio: basi di allocazione della gerarchia basate sui dipendenti a tempo pieno nell'organizzazione
Di seguito è riportato un esempio di una gerarchia di dimensioni oggetto di costo che può essere creata per descrivere un'organizzazione semplificata.

| Nome gerarchia | Livello nodo 0 | Livello nodo 1 | Livello nodo 2 | Membri di dimensione |
|----------------|--------------|--------------|--------------|-------------------|
| Organizzazione   | Direttore generale          | CFO          | FICO         | CC001             |
| Organizzazione   | Direttore generale          | CFO          | Risorse umane           | CC002             |
| Organizzazione   | Direttore generale          | CIO          | TS           | CC003             |

La base di allocazione del membro di dimensione predefinita del FTE creata nella sezione precedente contiene le seguenti voci.

**Voci statistiche**

| Oggetto di costo | Descrizione  | Data di registrazione | Membro di dimensione statistica | Descrizione | Grandezza |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | Risorse umane   | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 1,00      |
| CC002       | FI   | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 2.00      |
| CC003       | TS   | 31-01-2017      | FTE                        | Dipendenti a tempo pieno | 2.00      |

Un costo deve essere distribuito tra centri di costo che rispondono al responsabile finanziario (CFO) dell'organizzazione. È riconosciuto che il rapporto di allocazione corretto è il numero di dipendenti a tempo pieno (FTE) per centro di costo.

**Basi di allocazione gerarchia**

| Nome                  | Base di allocazione | Gerarchia dimensioni di oggetto di costo | Nodo gerarchia dimensioni di oggetto di costo |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| Numero di FTE in CFO | FTE           | Organizzazione                    | CFO                                  |

Una funzione di anteprima consente di convalidare la base di allocazione gerarchia creata, in base alle voci statistiche nel sistema.

**Dettagli base allocazione**

| Oggetto di costo | Descrizione  |  Grandezza |
|-------------|------|------------|
| CC001       | Risorse umane   | 1,00       |
| CC002       | FI   | 2.00       |

Di seguito è riportato un esempio di regola di distribuzione costi se il numero di FTE nella base di allocazione della gerarchia CFO è assegnata come base di allocazione.

| Oggetto di costo | Descrizione  | Grandezza | Fattore di allocazione |
|-------------|------|-----------|-------------------|
| CC001       | Risorse umane   | 1,00      | (1/3) × Importo    |
| CC002       | FI   | 2.00      | (2/3) × Importo    |

## <a name="formula-allocation-bases"></a>Basi di allocazione formula

Le base di allocazione della formula consente di definire le formule avanzate per ottenere una corretta base di allocazione. È possibile creare manualmente le basi di allocazione della formula.

Quando si crea una base di allocazione della formula, si seleziona la dimensione statistica e le dimensioni dell'elemento di costo da considerare come base per la formula. Tutte le basi di allocazione che derivano dalle dimensioni selezionate in precedenza possono essere utilizzare nella base di allocazione della formula.

> [!NOTE]
> Le base di allocazione della formula precedentemente definite possono essere utilizzate per definire una nuova base di allocazione della formula.

Nei fattori della base di allocazione della formula, si crea un alias e lo si associa a una base di allocazione o una costante. Gli alias vengono utilizzati per definire la formula.

È possibile utilizzare i seguenti operatori per definire la formula.

| Simboli | Testo           |
|---------|----------------|
| ( )     | Parentesi    |
| \<      | Minore di   |
| \>      | Maggiore di    |
| +       | Addizione       |
| –       | Sottrazione    |
| \*      | Moltiplicazione |

Le istruzioni tradizionali **IF** non sono supportate. Tuttavia, è possibile creare istruzioni e convalidare se sono true.

| Rendiconto | Convalida | Risultato |
|-----------|------------|--------|
| a \> b    | True       | 1      |
| a \> b    | False      | 0      |

### <a name="example-1-a-simple-formula"></a>Esempio 1: Una formula semplice

Le bollette della luce sono spesso composte da due parti:

- Una commissione fissa per il collegamento alla rete
- Un costo associato al consumo per kWh

La base di allocazione del membro di dimensione predefinita dell'elettricità è già stata definita e contiene questi valori.

**Voci statistiche**

| Oggetto di costo | Nome | Data di registrazione | Membro di dimensione statistica | Descrizione             | Grandezza |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | Risorse umane   | 31-01-2017      | Elettricità                  | Consumo di elettricità | 2,450.00  |
| CC002       | FI   | 31-01-2017      | Elettricità                  | Consumo di elettricità | 4,100.00  |
| CC003       | TS   | 31-01-2017      | Elettricità                  | Consumo di elettricità | 15.000,00 |

Se la commissione fissa deve essere distribuita agli oggetti di costo che utilizzano elettricità, sono disponibili due opzioni per l'allocazione dei costi:

- Creare una nuova base di allocazione predefinita, elettricità fissa e quindi applicare una misura statistica di 1.00 per ogni oggetto di costo che ha consumato elettricità.
- Creare una base di allocazione della formula, elettricità fissa, che usa la base di allocazione predefinita dell'elettricità già definita nel sistema. Il vantaggio di questa opzione è che i dati devono essere caricati nella contabilità industriale solo per un membro di dimensione statistica dell'elettricità.

**Base di allocazione formula** 

| Nome              | Dimensione elemento di costo | Dimensione statistica | Formula |
|-------------------|------------------------|-----------------------|---------|
| Elettricità fissa |                        | Elementi statistici  |         |

Affinché il campo **Formula** possa essere specificato, è necessario specificare l'alias da utilizzare nella formula.

**Fattori di base di allocazione formula**

| Alias | Costante | Base di allocazione |
|-------|----------|-----------------|
| a     |          | Elettricità     |
| b     | 0,01     |                 |

Tenere presente che 0 (zero) non è supportato come costante.

**Base di allocazione formula**

| Nome              | Dimensione elemento di costo | Dimensione statistica | Formula |
|-------------------|------------------------|-----------------------|---------|
| Elettricità fissa |                        | Elementi statistici  | a \> b  |

Una funzione di anteprima consente di convalidare la base di allocazione formula creata, in base alle voci statistiche nel sistema.

**Dettagli base allocazione**

| Oggetto di costo | Descrizione  | Formula           | Grandezza |
|-------------|------|-------------------|-----------|
| CC001       | Risorse umane   | 2.450,00 \> 0,01  | 1,00      |
| CC002       | FI   | 4.100,00 \> 0,01  | 1,00      |
| CC003       | TS   | 15.000,00 \> 0,01 | 1,00      |

Di seguito è riportato un esempio di regola di distribuzione costi se la base di allocazione della formula dell'elettricità è assegnata come base di allocazione.

**Fattore di allocazione grandezza oggetto di costo**

| Oggetto di costo | Nome | Grandezza |  Fattore di allocazione |
|-------------|------|-----------|--------------------|
| CC001       | Risorse umane   | 1,00      | (1/3) × Importo     |
| CC002       | FI   | 1,00      | (1/3) × Importo     |
| CC003       | TS   | 1,00      | (1/3) × Importo     |

### <a name="example-2-an-advanced-formula"></a>Esempio 2: Una formula avanzata
Per questo esempio, il costo dell'elettricità non è solo per l'elettricità effettiva consumata in kWh. Il management vuole includere l'incentivo per ridurre l'uso dell'elettricità. 

| Regola              | Tasso | 
|-------------------|------|
| a <= 10000,00 kWh | 0.75 |
| a > 10000,00 kWh  | 1.15 |

Una nuova base di allocazione della formula, Uso dell'elettricità, viene creata.

**Base di allocazione formula**

| Nome              | Dimensione elemento di costo | Dimensione statistica | Formula |
|-------------------|------------------------|-----------------------|---------|
| Uso dell'elettricità |                        | Elementi statistici  |         |

Affinché il campo **Formula** possa essere specificato, è necessario specificare l'alias da utilizzare nella formula.

**Fattori di base di allocazione formula**

| Alias | Costante  | Base di allocazione |
|-------|-----------|-----------------|
| a     |           | Elettricità     |
| b     | 10.000,00 |                 |
| c     | 0.75      |                 |
| d     | 1.15      |                 |

**Base di allocazione formula**

| Nome              | Dimensione elemento di costo | Dimensione statistica | Formula                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| Elettricità fissa |                        | Elementi statistici  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

Una funzione di anteprima consente di convalidare la base di allocazione formula creata, in base alle voci statistiche nel sistema.

**Dettagli base allocazione**

| Oggetto di costo |    | Formula                                                                                                                             | Grandezza |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | Risorse umane | ((2,450.00 \> 10.000.00) × ((10,000.00 × 0.75) + (2,450.00 – 10,000.00) × 1.15)) + ((2,450.00 \<= 10,000.00) × 2,450.00 × 0.75)     | 1,837.50  |
| CC002       | FI | ((4,100.00 \> 10.000.00) × ((10,000.00 × 0.75) + (4,100.00 – 10,000.00) × 1.15)) + ((4,100.00 \<= 10,000.00) × 4,100.00 × 0.75)     | 3,075.00  |
| CC003       | TS | ((15,000.00 \> 10.000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) | 1,3250.00 |

Di seguito un esame più attento alla formula per CC003 (IT):

((15,000.00 \> 10,000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) = 13,250.00

(1 × (7,500.00 + 5,000.00 × 1.15)) + (0 × 15,000.00 × 0.75)            

1 × 7,500.00 + 5,750.00 + 0 

Di seguito è riportato un esempio di regola di distribuzione costi se la base di allocazione della formula dell'elettricità fissa è assegnata come base di allocazione.


| Oggetto di costo | Descrizione | Grandezza |        Fattore di allocazione         |
|-------------|-------------|-----------|----------------------------------|
|    CC001    |     Risorse umane      | 1,837.50  | (1,837.50 ÷ 18,162.50) × Importo  |
|    CC002    |     FI      | 3,075.00  | (3,075.00 ÷ 18,162.50) × Importo  |
|    CC003    |     TS      | 13,250.00 | (13,250.00 ÷ 18,162.50) × Importo |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]