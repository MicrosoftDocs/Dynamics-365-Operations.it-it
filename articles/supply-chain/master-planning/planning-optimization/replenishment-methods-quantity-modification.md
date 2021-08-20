---
title: Metodi di rifornimento e modifica della quantità
description: Questo argomento fornisce informazioni sui metodi di rifornimento in Ottimizzazione pianificazione. Spiega anche come la quantità di più ordini per un prodotto influisce sul risultato.
author: crytt
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19853bdb3c469dbfea3a3a0165a9cb5f47e73122cc695de3535a58f6e65e7933
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759529"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Metodi di rifornimento e modifica della quantità

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce informazioni sui metodi di rifornimento in Ottimizzazione pianificazione. Spiega anche come la quantità di più ordini per un prodotto influisce sul risultato.

I metodi di rifornimento sono anche noti come metodi di copertura e metodi di dimensionamento dei lotti.

## <a name="coverage-codes"></a>Codici di copertura

L'ottimizzazione della pianificazione può essere configurata per utilizzare differenti metodi di rifornimento. I metodi di rifornimento sono le tecniche che il sistema utilizza per calcolare i requisiti per un prodotto. I metodi di rifornimento sono definiti dai codici di copertura che è possibile impostare sul gruppo di copertura o sul prodotto.

I seguenti codici di copertura possono essere utilizzati in Ottimizzazione pianificazione:

- **Periodo** - Il metodo di rifornimento combina tutta la domanda durante un periodo in un ordine per il prodotto. L'ordine verrà pianificato per il primo giorno del periodo e la relativa quantità soddisferà i fabbisogni netti durante il periodo stabilito. Il periodo inizia con la prima domanda del prodotto e copre la lunghezza definita nel tempo. Il periodo successivo inizierà con i requisiti successivi del prodotto. Il codice di copertura *Periodo* viene spesso utilizzato per il prelievo di scorte non prevedibile, prodotti influenzati dalla stagione o prodotti ad alto costo. Nella figura seguente viene illustrato un esempio.

    ![Esempio di utilizzo del codice di copertura del periodo.](./media/coverage-code-period.png "Esempio di utilizzo del codice di copertura del periodo")

- **Fabbisogno** - Il metodo di rifornimento in cui il sistema crea un ordine di produzione, trasferimento o fornitore per fabbisogno per il prodtto. Questo metodo viene utilizzato per prodotti costosi che hanno una domanda intermittente. Il codice di copertura *Fabbisogno* viene spesso utilizzato per prodotti configurabili o scenari su ordinazione. Nella figura seguente viene illustrato un esempio.

    ![Esempio di utilizzo del codice di copertura del fabbisogno.](./media/coverage-code-requirement.png "Esempio di utilizzo del codice di copertura del fabbisogno")

- **Min/Max** – Il metodo di rifornimento si basa sul livello delle scorte. Definisce il rifornimento delle scorte fino a un livello specifico quando il livello di disponibilità previsto è inferiore a una soglia specifica. La quantità di rifornimento sarà la differenza tra il livello massimo e il livello disponibile previsto. Il codice di copertura *Min/Max* viene spesso utilizzato per il prelievo di scorte prevedibile, high runner o prodotti meno costosi. Nella figura seguente viene illustrato un esempio.

    ![Esempio di utilizzo del codice di copertura Min/Max.](./media/coverage-code-min-max.png "Esempio di utilizzo del codice di copertura Min/Max")

- **Manuale** - Il metodo di rifornimento in cui il sistema non suggerisce ordini di produzione, trasferimento o fornitore per il prodotto. Invece, l'addetto alla pianificazione del prodotto è responsabile della creazione degli ordini richiesti per il rifornimento del prodotto. Il codice di copertura *Manuale* viene spesso utilizzato per prodotti per i quali gli ordini pianificati generati dal sistema non sono desiderati.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Impatto della quantità dell'ordine dalle impostazioni dell'ordine predefinite

Nella pagina **Impostazione ordine predefinita** per un prodotto rilasciato, è possibile specificare ciascuna delle seguenti impostazioni di quantità nelle schede dettaglio **Ordine fornitore**, **Inventario**, e **Ordine cliente**. La scheda dettaglio **Inventario** viene utilizzata sia per gli ordini di trasferimento che per gli ordini di produzione.

- **Multiplo** – Gli ordini pianificati saranno multipli di questa quantità.

    Ad esempio, se il campo **Multiplo** è impostato su *5*, un ordine può essere per una quantità di 5, 10, 15, 20 e così via.

- **Quantità min. ordine** – Gli ordini pianificati non saranno inferiori al valore specificato.

    Ad esempio, se il campo **Quantità min. ordine** è impostato su *10*, verrà creato un ordine pianificato per una quantità di 10, anche se ne sono necessari solo quattro per soddisfare la domanda.

- **Quantità max. ordine** – Gli ordini pianificati non saranno superiori al valore specificato. Se la domanda è superiore al valore **Quantità max. ordine** verranno creati più ordini pianificati per coprirlo.

    Ad esempio, se il campo **Quantità max. ordine** è impostato su *100* e la domanda è 450, verranno creati quattro ordini pianificati per una quantità di 100 e un ordine pianificato per una quantità di 50.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Esempi di rifornimento che utilizzano il codice di copertura Min/Max

Se non specifichi un valore nel campo **Multiplo** per un prodotto nella pagina **Impostazione ordine predefinita** e se stai usando il metodo di rifornimento *Min/Max* Ottimizzazione pianificazione rifornisce le scorte fino a un livello specifico quando il livello di disponibilità previsto è inferiore a una soglia specifica.

Se definisci una quantità multipla per un prodotto, il metodo di rifornimento *Min/Max* cambia il suo comportamento e considera il valore **Multiplo**.

In altre parole, l'ottimizzazione della pianificazione rifornirà comunque le scorte fino al livello massimo definito quando il livello di disponibilità previsto è inferiore al livello minimo definito. Tuttavia, la quantità di rifornimento deve essere un multiplo del valore **Multiplo**.

Se la quantità di rifornimento (la differenza tra il livello massimo e il livello di disponibilità previsto) non è un multiplo della quantità multipla definita, Ottimizzazione pianificazione utilizza il primo valore possibile che, insieme al livello di disponibilità previsto, sarà inferiore il livello massimo. Se la somma è inferiore al livello minimo, Ottimizzazione pianificazione utilizza il primo valore che, insieme alla disponibilità prevista, sarà al di sopra del livello massimo.

Le seguenti sottosezioni forniscono alcuni esempi che mostrano come la quantità di ordini multipli per un prodotto influenzi il risultato del metodo di rifornimento *Min/Max* .

### <a name="example-1"></a>Esempio 1

Un prodotto ha la seguente configurazione:

- **Codice di copertura:** *Min/Max*
- **Minimo:** *15*
- **Massimo:** *22*
- **Multiplo:** *0*

Ci sono 10 pezzi di scorte disponibili per il prodotto e non c'è altra domanda o offerta.

Quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per 12 pezzi per rifornire le scorte alla quantità massima.

### <a name="example-2"></a>Esempio 2

Un prodotto ha la seguente configurazione:

- **Codice di copertura:** *Min/Max*
- **Minimo:** *15*
- **Massimo:** *22*
- **Multiplo:** *5*

Ci sono 10 pezzi di scorte disponibili per il prodotto e non c'è altra domanda o offerta.

Quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per 10 pezzi (perché 15 pezzi di rifornimento più 10 pezzi di scorte disponibili supereranno la quantità massima).

### <a name="example-3"></a>Esempio 3

Un prodotto ha la seguente configurazione:

- **Codice di copertura:** *Min/Max*
- **Minimo:** *21*
- **Massimo:** *24*
- **Multiplo:** *5*

Ci sono 10 pezzi di scorte disponibili per il prodotto e non c'è altra domanda o offerta.

Quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per 15 pezzi (perché 10 pezzi di rifornimento più 10 pezzi di scorte disponibili saranno inferiori alla quantità minima).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
