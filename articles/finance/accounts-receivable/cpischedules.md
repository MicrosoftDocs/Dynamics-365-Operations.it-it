---
title: Programmazione indice dei prezzi al consumo
description: In questo argomento viene spiegato come creare l'elenco delle pianificazioni dell'indice dei prezzi al consumo (CPI) ottenute da Internet per determinare l'addebito dell'escalation nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 2a69e58095844286878e27a100fa49a44a4a71f4
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560490"
---
# <a name="consumer-price-index-schedule"></a>Programmazione indice dei prezzi al consumo

[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare, eliminare, rivedere ed elaborare le pianificazioni dell'indice dei prezzi al consumo (CPI). È possibile utilizzare una pianificazione CPI per determinare i prezzi dei beni di consumo e dei servizi aggiunti come righe di programma di fatturazione. La pianificazione CPI può quindi essere utilizzata con la determinazione dei prezzi di escalation e sconto in un programma di fatturazione oppure può essere elaborata manualmente per aggiornare gli importi di fatturazione nei programmi di fatturazione. È possibile immettere manualmente le pianificazioni CPI oppure importarle utilizzando l'entità composita pianificazione CPI.

Per aggiungere una pianificazione CPI segui questi passi.

1. Nella pagina **Programma dell'indice dei prezzi al consumo**, seleziona **Nuovo**.
2. Nel campo **Programma dell'indice dei prezzi al consumo** immetti un nome univoco.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nella scheda **Programma dell'indice dei prezzi al consumo**, seleziona **Aggiungi**.
5. Nel campo **Data indice dei prezzi al consumo** specifica la data in cui la nuova pianificazione CPI diventa attiva.
6. Nel campo **Programma dell'indice dei prezzi al consumo** immetti il nome che hai inserito nel passaggio 2.
7. Seleziona **Salva**.

Per eliminare una data della pianificazione CPI, attieniti a questa procedura.

1. Nella pagina **Programma dell'indice dei prezzi al consumo** seleziona una o più righe che vuoi eliminare, quindi seleziona **Rimuovi**.
2. Per eliminare l'intera pianificazione CPI, nel riquadro azioni seleziona **Elimina**. Non puoi eliminare la pianificazione CPI selezionata se è associata a un programma di fatturazione.
3. Nel riquadro azioni seleziona **Processo** per aggiornare i programmi di fatturazione che utilizzano la pianificazione CPI selezionata. Le ultime date CPI e gli importi della pianificazione verranno utilizzati per aggiornare i prezzi del programma di fatturazione.
4. Nella scheda dettaglio **Processo dell'indice dei prezzi al consumo** rivedi i campi aggiornati **Numero programma di fatturazione**, **Codice articolo**, **Data di inizio fatturazione**, **Data di fine fatturazione**, **Data di escalation**, e **Frequenza di escalation**.

Dopo aver impostato le pianificazioni CPI, possono essere utilizzate per le modifiche ai prezzi di escalation e sconto nei programmi di fatturazione.

## <a name="cpi-calculation"></a>Calcolo CPI

Per questi esempi, il periodo va dal 1 gennaio 2020 al 31 dicembre 2022. Il tasso CPI di base (il valore CPI all'inizio del contratto) è 105,65. Il 1° gennaio 2021, l'attuale CPI è 110,5. Il 1° gennaio 2022, l'attuale CPI è 114,25. L'importo iniziale è $ 1.000.

**Esempio 1**

Nella pagina **Parametri di fatturazione contratto ricorrente** imposta il campo **Calcolo dell'indice dei prezzi al consumo** su **Indice dei prezzi al consumo di base**.

Per il periodo 1 gennaio 2021, il primo importo dell'escalation è calcolato nel modo seguente, in base all'importo iniziale:

1.000 + (110,5 – 105,65) &divide; 105,65 &times; 1.000 = 1.045,91

Per il periodo 1 gennaio 2022, l'importo dell'escalation è calcolato nel modo seguente:

1.000 + (114,25 – 105,65) &divide; 105,65 &times; 1.000 = 1.081,40

**Esempio 2**

Nella pagina **Parametri di fatturazione contratto ricorrente** imposta il campo **Calcolo dell'indice dei prezzi al consumo** su **Indice dei prezzi al consumo precedente**.

Per il periodo 1 gennaio 2021, il primo importo dell'escalation è calcolato nel modo seguente, in base all'importo iniziale:

1.000 + (110,5 – 105,65) &divide; 105,65 &times; 1.000 = 1.045,91

Per il periodo 1 gennaio 2022, l'importo dell'escalation è calcolato nel modo seguente, in base all'importo della prima escalation:

1.045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1.045,91 = 1.081,40

> [!NOTE]
> Il processo di escalation utilizza sempre il valore CPI più recente, indipendentemente dalla data dell'indice. Ad esempio, se l'escalation è a settembre, ma l'ultimo valore CPI è per luglio, viene utilizzato l'indice di luglio. Non vengono apportate rettifiche dopo l'inserimento dell'indice di settembre.

## <a name="prorated-escalation"></a>Escalation proporzionale

Se l'escalation si verifica nel mezzo di un periodo di fatturazione, l'importo viene ripartito proporzionalmente. Ad esempio, il periodo di fatturazione va dal 1 agosto 2020 al 31 luglio 2021. Alla data CPI 1 settembre 2019, il valore CPI è 244. Alla data CPI 1 settembre 2020, il valore CPI è 250. Se il tasso precedente è 1.000, vengono utilizzate le seguenti formule per calcolare l'importo di fatturazione per il periodo:

* *Modifiche CPI* = (250 – 244) &divide; 244 = 2,459%
* *Tasso corrente* = 1.000 &times; 2,459% = 1.024,59
* *Numero di giorni al tasso corrente* = 31 luglio 2021 – 1 settembre 2020 = 334
* *Tasso precedente* = 1.000
* *Numero di giorni al tasso precedente* = 31 agosto 2020 – 1 agosto 2020 = 31
* *Numero di giorni totali del periodo di fatturazione* = 31 luglio 2021 – 1 agosto 2020 + 1 = 365
* *Importo di fatturazione per questo periodo* = (1.000 &times; 31 &divide; 365) + (1.024,59 &times; 334 &divide; 365) = 1.022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Escalation che utilizza il CPI e la percentuale

Le escalation possono essere eseguite utilizzando il CPI. Il CPI più un'escalation del 3 percento inizia il 1 gennaio 2020 e ha una frequenza annuale.

- L'importo fatturato dal 1 gennaio 2019 al 31 dicembre 2020 è 4.000.
- Il periodo di fatturazione che verrà sottoposto a escalation va dal 1 gennaio 2020 al 31 dicembre 2020.
- Alla data CPI 1 dicembre 2018, il valore CPI è 205,3. Alla data CPI 1 dicembre 2019, il valore CPI è 219,6.

Se il tasso precedente è 4.000, l'importo di fatturazione per questo periodo viene calcolato nel modo seguente:

- *Modifiche CPI* = (219,6 – 205,3) &divide; 205,3 = 6,965%
- *Tasso corrente* = (4,000 &times; 6,965%) – 4000 = 278,60
- *Modifiche percentuali* = (4.000 &times; 1,03) – 4.000 = 120
- *Importo di fatturazione* = 4.000 + 278,6 + 120 = 4.398,6
