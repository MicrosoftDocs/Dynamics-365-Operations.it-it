---
title: Criteri rollup costi e calcolo dei costi generali
description: "In questo argomento vengono fornite informazioni sulla determinazione del livello corretto degli elementi di costo secondari e creare le regole di rollup dei costi adatte al reporting dell'organizzazione e alla tracciabilità dei costi."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostRollupRule, CAMDimensionHierarchy
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 044a943eeba91f5dbebd4dcd70bc8152c4109037
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="cost-rollup-policy-and-overhead-calculation"></a>Criteri rollup costi e calcolo dei costi generali 

[!include[banner](../includes/banner.md)]

La contabilità industriale consente di ottenere i dettagli di come il flusso dei costi riguarda i prodotti e i servizi offerti a un'organizzazione. Per vedere la trasparenza dei costi, è essenziale ottenere l'allocazione dei costi tra gli oggetti di costo secondo una base di allocazione appropriata. Per impostazione predefinita, l'allocazione dei costi viene raggiunta per l'elemento di costo principale, utile in alcune situazioni, ma con alcune implicazioni che devono essere considerate.

-   Gli oggetti di costo ausiliari terminano con saldo zero per l'elemento di costo principale dopo il calcolo dei costi generali.

-   Il volume delle voci di costo generate dal calcolo dei costi generali può essere molto elevato.

-   Non è possibile tenere traccia del flusso dei costi tra gli oggetti di costo.

Per evitare queste implicazioni, la contabilità industriale consente di configurare l'allocazione dei costi adatta ai requisiti di reporting direttivi dell'organizzazione. In questo argomento viene descritto come determinare il livello corretto degli elementi di costo secondari e creare le regole di rollup dei costi adatte al reporting dell'organizzazione e alla tracciabilità dei costi.

> [!NOTE]
> È possibile modificare le configurazioni se cambiano i requisiti di reporting.

## <a name="example-of-cost-rollup-policy-setup"></a>Esempio di impostazione dei criteri di rollup dei costi

Si supponga che un'organizzazione abbia la seguente struttura con 4 centri di costo.

![Esempio di struttura di un'organizzazione](./media/dimension-hierarchy-org.png)

**Dimensione oggetto di costo**

| Centri di costo | descrizione          |
|--------------|-----------|
| CC001        | Risorse umane        |
| CC002        | Dati finanziari   |
| CC003        | Assemblaggio  |
| CC004        | Imballaggio |

**Dimensione elemento di costo**

| Elementi di costo | descrizione | Tipo    |
|---------------|-------------|---------|
| 1001          | Elettricità | Primario |
| 1002          | Stipendi    | Primario |
| 1003          | Annunci | Primario |

Una gerarchia di dimensioni che soddisfa i requisiti di reporting dell'organizzazione può essere impostata come indicato di seguito.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione    | Nome tipo di gerarchia dimensioni      | Gerarchia elenco accessi |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organizzazione             | Centri di costo | Gerarchia classificazioni dimensione | No                    |

**Gerarchia dimensioni**

|              | Intervalli membro di dimensione |                     |
|--------------|-------------------------|---------------------|
| **Nodi**        | **Membro di dimensione di inizio**   | **Membro di dimensione di fine** |
| Organizzazione |                         |                     |
| &nbsp;&nbsp;Amministratore             |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Dati finanziari              | CC001                   | CC001               |
| &nbsp;&nbsp;&nbsp;&nbsp;Risorse umane               | CC002                   | CC002               |
| &nbsp;&nbsp;Produzione               |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Imballaggio              | CC003                   | CC003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Assemblaggio             | CC004                   | CC004               |

Una gerarchia di dimensioni che soddisfa i requisiti dei criteri può essere impostata come indicato di seguito.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione     | Nome tipo di gerarchia dimensioni      |
|--------------------------|---------------|------------------------------------|
| Rendiconto profitti e perdite  | Elementi di costo | Gerarchia classificazioni dimensione |

**Gerarchia dimensioni**

|                         | Intervalli membro di dimensione |                     |
|-------------------------|-------------------------|---------------------|
| Nodi                   | Membro di dimensione di inizio   | Membro di dimensione di fine |
| Rendiconto profitti e perdite |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Costo primario                    | 10001                   | 10003               |

Dopo che le voci di contabilità generale vengono elaborate, il saldo delle voci di costo per oggetto di costo sarà simile al seguente.

|                      | **Oggetto di costo** |           |           |           | **Totale**     |
|----------------------|-----------------|-----------|-----------|-----------|---------------|
| **Elemento di costo**     | **CC001**       | **CC002** | **CC003** | **CC004** |               |
| **1001 Elettricità** | 100,00          | 200.00    | 6.000,00  | 2.000,00  | **8.300,00**  |
| **1002 Stipendi**    | 10.000,00       | 10.000,00 | 8.000,00  | 6.500,00  | **34.500,00** |
| **1003 Annunci** | 0.00            | 4.000,00  | 0.00      | 0.00      | **4.000,00**  |
|                      | 10.100,00       | 14.200,00 | 14.000,00 | 8.500,00  | **46.800,00** |

**Dimensione statistica**

| Elementi statistici |    descrizione   |
|----------------------|------------------|
| SE-1                 | Servizi HR      |
| SE-2                 | Servizi finanziari |

L'oggetto di costo CC001 HR contribuisce Servizi HR a più oggetti di costo.

I Servizi HR vengono utilizzati dalla seguente distribuzione di grandezza.

| Oggetto di costo | descrizione |   Servizi HR |
|-------------|-------------|----|
| CC002       | Dati finanziari     | 35 |
| CC003       | Assemblaggio    | 55 |
| CC004       | Imballaggio   | 10 |

L'oggetto di costo CC002 Finanza contribuisce a più oggetti di costo.

I Servizi finanziari vengono utilizzati dalla seguente distribuzione di grandezza.

| Oggetto di costo |   descrizione    |  Servizi finanziari   |
|-------------|------------------|----|
| CC003       | Assemblaggio         | 65 |
| CC004       | Imballaggio        | 35 |

I criteri di allocazione costi possono essere impostati come indicato di seguito.

| Nome criteri | descrizione     | Gerarchia dimensioni di oggetto di costo | Dimensione statistica | Dimensione elemento di costo |
|-------------|-----------------|---------------------------------|-----------------------|------------------------|
| 2017        | Allocazione costi | Organizzazione                    | Elementi statistici  | Elementi di costo          |

Le regole di allocazione costi possono essere impostate come indicato di seguito.

| Nodo gerarchia dimensioni di oggetto di costo | Comportamento costo | Base di allocazione        |
|--------------------------------------|---------------|------------------------|
| CC001                                | Totale         | **Servizi HR**        |
| CC002                                | Totale         | **Servizi finanziari** |

<a name="brhow-cost-flows-between-cost-centers"></a><br>Flusso dei costi tra centri di costo 
---------------------------------------------------

Per sapere come avviene il flusso dei costi tra i centri di costo dell'organizzazione, è possibile creare elementi di costo di tipo **Secondario** per ogni centro di costo. Questi elementi di costo verranno utilizzati per trasferire i saldi tra i centri di costo durante il calcolo dei costi generali.

I membri di dimensione elemento di costo possono essere impostati come indicato di seguito.

| Elementi di costo | Tipo          |               |
|---------------|---------------|---------------|
| 1001          | Elettricità   | Primario       |
| 1002          | Stipendi      | Primario       |
| 1003          | Annunci   | Primario       |
| **SC-CC001**  | **Risorse umane**        | **Secondario** |
| **SC-CC002**  | **Dati finanziari**   | **Secondario** |
| **SC-CC003**  | **Assemblaggio**  | **Secondario** |
| **SC-CC004**  | **Imballaggio** | **Secondario** |

La gerarchia di dimensioni **Rendiconto profitti e perdite** deve essere aggiornata con nuovi membri di dimensione in modo che la gerarchia di dimensioni contenga i dati corretti che possono essere utilizzati per la definizione dei report e dei criteri.

**Dettagli gerarchia dimensioni**

| Nome gerarchia dimensioni | Dimensione     | Nome tipo di gerarchia dimensioni      |
|--------------------------|---------------|------------------------------------|
| Rendiconto profitti e perdite  | Elementi di costo | Gerarchia classificazioni dimensione |

**Gerarchia dimensioni**

|                         | Intervalli membro di dimensione |                     |
|-------------------------|-------------------------|---------------------|
| Nodi                   | Membro di dimensione di inizio   | Membro di dimensione di fine |
| Rendiconto profitti e perdite |                         |                     |
| &nbsp;&nbsp;&nbsp;&nbsp;Costo primario                        | 10001                   | 10003               |
| &nbsp;&nbsp;&nbsp;&nbsp;Costo secondario                         | **SC-CC001**            | **SC-CC004**        |

Creare **Criteri rollup costi** in cui ogni centro di costo sia associato a un elemento di costo corrispondente di tipo **Secondario**.

**Criteri rollup costi**

| Nome criteri | descrizione | Gerarchia dimensioni di oggetto di costo | Gerarchia dimensioni di elemento di costo |
|-------------|-------------|---------------------------------|----------------------------------|
| 2017        | Flusso dei costi   | Organizzazione                    | Rendiconto profitti e perdite          |

**Regole rollup costi**

| Nodo gerarchia dimensioni di oggetto di costo | Nodo gerarchia dimensioni di elemento di costo | Elemento di costo secondario |
|--------------------------------------|---------------------------------------|------------------------|
| CC001                                | Rendiconto profitti e perdite               | **SC-CC001**           |
| CC002                                | Rendiconto profitti e perdite               | **SC-CC002**           |
| CC003                                | Rendiconto profitti e perdite               | **SC-CC003**           |
| CC004                                | Rendiconto profitti e perdite               | **SC-CC004**           |

## <a name="perform-overhead-calculation"></a>Eseguire il calcolo generale

**Giornale di registrazione**

| Giornale di registrazione | Tipo giornale di registrazione            | Periodo di calendario fiscale | Anno | Periodo | Versione       |
|---------|-------------------------|------------------------|------|--------|---------------|
| 00002   | Giornale di registrazione allocazione costi | Fiscale                 | 2017    | Periodo 1 | Calcolo dei costi generali / 01-02-2017 23.51.00 / Contabilità generale /2017 / Periodo 1 |

Il sistema ora applica i **Criteri rollup costi** quando vengono create le **Scritture contabili saldo oggetto di costo**.

**Scritture contabili saldo oggetto di costo**

| Data di registrazione | Oggetto di costo | descrizione  | Elemento di costo | descrizione |  Importo |
|-----------------|-------------|--------------|----------|-----------|-----------|
| 31-01-2017      | CC001       | Risorse umane           | SC-CC001 | Risorse umane        | 10.100,00 |
| 31-01-2017      | CC002       | Dati finanziari      | SC-CC002 | Dati finanziari   | 17.735,00 |
| 31-01-2017      | CC003       | Assemblaggio     | SC-CC003 | Assemblaggio  | 31.082,75 |
| 31-01-2017      | CC004       | Imballaggio    | SC-CC004 | Imballaggio | 15.717,25 |

> [!NOTE]
> Gli inserimenti nel giornale di registrazione vengono creati in base alle regole dei **Criteri rollup costi** se presenti. Il saldo visualizzato è il saldo del calcolo dei costi generali.

La pagina **Dettagli scrittura contabile saldo costi oggetto di costo** che viene aperta dagli inserimenti nel giornale di registrazione indica come viene ottenuto il saldo.

**Esempio: l'inserimento nel giornale di registrazione per Oggetto di costo CC002 Finanza**

**Dettagli scrittura contabile saldo costi oggetto di costo**

| Membro di dimensione elemento di costo | descrizione |  Importo   |
|-------------------------------|-------------|-----------|
| 1001                          | Elettricità | 200.00    |
| 1002                          | Stipendi    | 10.000,00 |
| 1003                          | Annunci | 4.000,00  |
| SC-CC001                      | Risorse umane          | 3.535,00  |

**Voci di costo generate dal calcolo dei costi generali**

| Oggetto di costo | descrizione  | Elemento di costo   | descrizione  |        Importo     |       Data di registrazione     |
|-------------|--------------|----------|-----------------|-------------|------------|
| CC001       | Risorse umane           | SC-CC001 | Risorse umane              | 10.100,00 \- | 31-01-2017 |
| CC002       | Dati finanziari      | SC-CC001 | Risorse umane              | 3.535,00    | 31-01-2017 |
| CC003       | Assemblaggio     | SC-CC001 | Risorse umane              | 5.555,00    | 31-01-2017 |
| CC004       | Imballaggio    | SC-CC001 | Risorse umane              | 1.010,00    | 31-01-2017 |
| CC002       | Dati finanziari      | SC-CC002 | Dati finanziari         | 17.735,00 \- | 31-01-2017 |
| CC003       | Assemblaggio     | SC-CC002 | Dati finanziari         | 11.527,75   | 31-01-2017 |
| CC004       | Imballaggio    | SC-CC002 | Dati finanziari         | 6.207,25    | 31-01-2017 |

Dopo aver completato il **calcolo dei costi generali**, è possibile segnalare i risultati utilizzando strumenti quali l'area di lavoro Microsoft SharePoint, Excel o Power BI.

## <a name="view-reporting-in-excel"></a>Visualizzare i report in Excel 

Le gerarchie di dimensioni consentono di visualizzare i dati a diversi livelli di aggregazione.

Di seguito è riportato un esempio di reporting Power Pivot in Excel.

| **Rendiconto profitti e perdite** | **Oggetto di costo** |                |               |               |  **Totale**    |
|-----------------------------|-----------------|----------------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002**      | **CC003**     | **CC004**     |               |
| **Costo primario**            | **10.100,00**   | **14.200,00**  | **14.000,00** | **8.500,00**  | **46.800,00** |
| 1001 &nbsp;&nbsp;&nbsp;&nbsp;                            | 100,00          | 200.00         | 6.000,00      | 2.000,00      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                            | 10.000,00       | 10.000,00      | 8.000,00      | 6.500,00      | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0.00            | 4.000,00       | 0.00          | 0.00          | **4.000,00**  |
|**Costo secondario**                            | **-10.100,00**  | **-14.200,00** | **17.082.75** | **7.217,25**  | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC001                            | 10.100,00 \-     | 3.535,00       | 5.555,00      | 1.010,00      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC002                             | 0.00            | 17.735,00 \-    | 11.527,75     | 6.207,25      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC003                            | 0.00            | 0.00           | 0.00          | 0.00          | 0.00          |
|&nbsp;&nbsp;&nbsp;&nbsp;SC-CC004                             | 0.00            | 0.00           | 0.00          | 0.00          | 0.00          |
| **Totale**                   | **0,00**        | **0,00**       | **31.082,75** | **15.717,25** | **46.800,00** |

Utilizzando i **criteri rollup costi** e gli **elementi di costo di tipo secondario** è possibile lasciare il costo primario per oggetto di costo per la creazione di report interni come costo primario rimanente dopo il **calcolo dei costi generali**.

Se lo stesso esempio fosse stato eseguito senza creare i **criteri rollup costi,** il risultato del report sarebbe come quello indicato di seguito. Il costo viene eseguito correttamente ma la tracciabilità e i dettagli dei flussi dei costi tra i centri di costo verranno persi.

| **Rendiconto profitti e perdite** | **Oggetto di costo** |           |               |               |          **Totale**  |
|-----------------------------|-----------------|-----------|---------------|---------------|---------------|
|                             | **CC001**       | **CC002** | **CC003**     | **CC004**     |               |
| **Costo primario**            | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |
|1001 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0.00            | 0.00      | 6.207,75      | 2.092,25      | **8.300,00**  |
| 1002 &nbsp;&nbsp;&nbsp;&nbsp;                             | 0.00            | 0.00      | 22.275,00     | 12.225,00     | **34.500,00** |
|1003 &nbsp;&nbsp;&nbsp;&nbsp;                              | 0.00            | 0.00      | 2600,00       | 1.400,00      | **4.000,00**  |
|**Costo secondario**                            | **0,00**        | **0,00**  | **0,00**      | **0,00**      | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC001                             | 0.00            | 0.00      | 0.00          | 0.00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC002                             | 0.00            | 0.00      | 0.00          | 0.00          | **0,00**      |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC003                             | 0.00            | 0.00      | 0.00          | 0.00          | 0.00          |
|&nbsp;&nbsp;&nbsp;&nbsp; SC-CC004                             | 0.00            | 0.00      | 0.00          | 0.00          | 0.00          |
| **Totale**                   | **0,00**        | **0,00**  | **31.082,75** | **15.717,25** | **46.800,00** |

A seconda dei requisiti di report e tracciabilità dell'organizzazione è possibile determinare il livello corretto degli elementi di costo secondari e creare le regole di rollup dei costi adatte alle proprie esigenze.

La netta separazione tra **Allocazione costi** e **Criteri rollup costi** fornisce la flessibilità di effettuare aggiornamenti continuare senza interferenze.



## <a name="see-also"></a>Vedere anche
-  [Dimensioni oggetto di costo](cost-objects.md)
-  [Dimensioni elemento di costo](cost-elements.md)
-  [Gerarchie di dimensioni](dimension-hierarchy.md)
-  [Calcolo generale](overhead-calculation.md)

