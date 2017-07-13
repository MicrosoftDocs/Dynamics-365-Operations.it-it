---
title: "Liquidazione automatica e assegnazione di priorità"
description: "Questo articolo descrive la modalità di liquidazione delle transazioni se si seleziona la liquidazione automatica nella pagina Parametri contabilità clienti. Viene anche illustrato come è possibile utilizzare la liquidazione automatica insieme alla priorità di pagamento."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 3e2ca11eef4246d5abfd77351325ac2b4440b446
ms.contentlocale: it-it
ms.lasthandoff: 06/20/2017


---

# <a name="automatic-settlement-and-prioritization"></a>Liquidazione automatica e assegnazione di priorità

[!include[banner](../includes/banner.md)]


Questo articolo descrive la modalità di liquidazione delle transazioni se si seleziona la liquidazione automatica nella pagina Parametri contabilità clienti. Viene anche illustrato come è possibile utilizzare la liquidazione automatica insieme alla priorità di pagamento.

Quando vengono liquidati i pagamenti con le fatture e altre transazioni sono disponibili due opzioni. È possibile selezionare manualmente le transazioni da liquidare oppure Microsoft Dynamics 365 for Finance and Operations può selezionare le transazioni automaticamente utilizzando la funzionalità di liquidazione automatica. È inoltre possibile personalizzare il modo in cui le liquidazioni automatiche vengono elaborate tramite l'opzione **Assegna priorità a liquidazione**. Tutte queste opzioni fanno parte dei parametri di liquidazione definiti nella pagina **Parametri contabilità clienti**. La modalità in cui le transazioni vengono automaticamente liquidate può essere diversa, a seconda del metodo utilizzato per la liquidazione automatica. Sono disponibili i seguenti metodi:

-   Priorità di liquidazione definita dall'utente
-   Liquidazione automatica predefinita

Nelle sezioni seguenti viene descritto come vengono liquidate le transazioni per ciascun metodo.

## <a name="example-transactions"></a>Transazioni di esempio
Gli esempi di liquidazioni più avanti in questo articolo si basano sulle seguenti transazioni. Tutte le transazioni sono relative al cliente 2050.

| Transazione   | Data        | Importo | Termini dello sconto di cassa | Data sconto di cassa | Commenti                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fattura 1     | 15 agosto   | 100,00 | 2%14, Net 30        | 29 agosto          |                                                                                                                                                                                               |
| Fattura 2     | 1 settembre | 250,00 | 2%14, Net 30        | 15 settembre       |                                                                                                                                                                                               |
| Fattura 3     | 15 ottobre  | 500,00 | 2% 14/Net 30        | 29 ottobre         |                                                                                                                                                                                               |
| Nota d'interesse | 15 ottobre  | 7,00   |                     |                    | Questa nota d'interesse è per la fattura 1 e la fattura 2. L'importo viene calcolato come interesse del 2% sugli importi che sono scaduti da 30 o più giorni. Ad esempio, 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="userdefined-settlement-priority"></a>Priorità di liquidazione definita dall'utente
Se si imposta **Utilizza priorità per liquidazioni automatiche** su **Sì** nella pagina **Parametri contabilità clienti**, la priorità di liquidazione definita nella pagina **Priorità liquidazione** viene utilizzata quando le transazioni vengono selezionate per la liquidazione automatica. Per questo esempio, la seguente priorità di liquidazione viene definita:

1.  Tipo di transazione
    -   Commissioni di pagamento
    -   Lettere di sollecito
    -   Note d'interesse
    -   Fatture

2.  Data transazione, Crescente
3.  Giustificativo

Se si registra un pagamento di 700,00 il 25 ottobre, il pagamento viene liquidato per le transazioni nell'ordine seguente.

| Giustificativo       | Data       | Fattura | Importo nella valuta della transazione | Importo da liquidare | Saldo | Valuta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Nota d'interesse | 15/10/2015 |         | 7,00                           | 7,00             | 0,00    | GBP      |
| Fattura 1     | 15/08/2015  | 10001   | 100,00                         | 100,00           | 0,00    | GBP      |
| Fattura 2     | 01/09/2015   | 10002   | 250,00                         | 250,00           | 0,00    | GBP      |
| Fattura 3     | 15/10/2015 |         | 500,00                         | 343,00           | 157,00  | GBP      |

## <a name="default-automatic-settlement"></a>Liquidazione automatica predefinita
Se non esiste una priorità di liquidazione definita dall'utente, le transazioni vengono automaticamente selezionate per la liquidazione in base alla data di scadenza. Le transazioni che vengono liquidate devono avere la stessa valuta della transazione con cui vengono liquidate. Se si registra un pagamento di 700,00 il 25 ottobre, le seguenti transazioni vengono selezionate per la liquidazione.

| Giustificativo       | Data       | Fattura | Importo nella valuta della transazione | Importo da liquidare | Saldo | Valuta |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Fattura 1     | 15/08/2015  | 10001   | 100,00                         | 100,00           | 0,00    | GBP      |
| Fattura 2     | 01/09/2015   | 10002   | 250,00                         | 250,00           | 0,00    | GBP      |
| Fattura 3     | 15/10/2015 |         | 500,00                         | 350,00           | 150,00  | GBP      |
| Nota d'interesse | 15/10/2015 |         | 7,00                           | 0,00             | 0,00    | GBP      |






