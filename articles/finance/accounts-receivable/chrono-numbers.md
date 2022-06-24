---
title: Numerazione cronologica di documenti e giustificativi
description: Questo articolo spiega come impostare e utilizzare i numeri cronologici per i documenti applicabili e i relativi giustificativi.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6baf307406982e8f72acc0d02f047dbc7c63a5ed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876385"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Numerazione cronologica di documenti e giustificativi

[!include [banner](../includes/banner.md)]


In alcuni paesi, esiste l'obbligo legale di numerare i documenti e i relativi giustificativi in ordine cronologico. La cronologia deve essere supportata in base a periodi. Tutti i numeri che appartengono a periodi precedenti devono essere inferiori ai numeri che appartengono a periodi successivi. Per soddisfare questo requisito, è stata implementata la funzionalità di numerazione cronologica. Questo articolo spiega come configurare e utilizzare i numeri cronologici per i documenti applicabili e i relativi giustificativi.

## <a name="prerequisites"></a>Prerequisiti

Nell'area di lavoro Gestione funzionalità, abilita la funzionalità **Numerazione cronologica**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Configurare la numerazione cronologica

La numerazione cronologica interessa i seguenti documenti.

**Contabilità clienti**
- Fattura cliente
- Giustificativo fattura cliente
- Nota di accredito vendita
- Giustificativo nota di accredito vendita
- Fattura a testo libero
- Giustificativo fattura a testo libero
- Nota di accredito a testo libero
- Giustificativo nota di accredito a testo libero
- Documento di trasporto
- Giustificativo documento di trasporto
- Giustificativo di correzione documento di trasporto
- Giustificativo nota d'interesse
- Giustificativo lettera di sollecito

**Contabilità fornitori**
- Giustificativo fattura
- Giustificativo nota di accredito
- Giustificativo entrata prodotti

**Gestione progetti**
- Fattura
- Giustificativo fattura
- Nota di accredito
- Giustificativo nota di accredito 

### <a name="define-number-sequences"></a>Definire le sequenze numeriche

Per definire sequenze numeriche, vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Sequenze numeriche**. È possibile definire tutte le sequenze numeriche necessarie per coprire i periodi interessati dei documenti richiesti. 

Specifica una società per ogni sequenza numerica. I segmenti delle sequenze numeriche devono essere definiti in modo che forniscano un ordine cronologico per i periodi. Ad esempio, i nomi dei segmenti possono contenere un prefisso speciale che identifica un periodo specifico.

![Impostazione della sequenza numerica.](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Configurare i gruppi di sequenze numeriche

Per configurare i gruppi di sequenze numeriche, vai a **Contabilità clienti** > **Impostazione** > **Parametri contabilità clienti**. Nella scheda **Sequenze numeriche** definisci tutti i gruppi di sequenze numeriche necessari per coprire i periodi interessati. 

Per ogni gruppo, nella sezione **Riferimento** seleziona uno dei riferimenti di documenti supportati e nel campo **Codice sequenza numerica** e fai riferimento a una sequenza numerica creata in precedenza per il periodo correlato.

![Impostazione del gruppo di sequenze numeriche.](media/chrono-num-sequence-group.jpg)

Allo stesso modo, configura i gruppi di sequenze numeriche nei moduli **Contabilità fornitori** e **Gestione progetti e contabilità**.

### <a name="configure-number-sequence-groups-chronology"></a>Configurare la cronologia dei gruppi di sequenze numeriche

Per configurare la cronologia dei gruppi di sequenze numeriche, vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Gruppi di sequenze numeriche cronologiche**. Definisci le condizioni di applicabilità per i gruppi di sequenze numeriche.

![Impostazione dei numeri cronologici.](media/chrono-num-sequence-group-period.jpg)

| Campo            | descrizione                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Valido  | La data di inizio dell'applicabilità del gruppo di sequenze numeriche. |
| Scadenza      | La data di fine dell'applicabilità del gruppo di sequenze numeriche. Se non si applica alcuna data di fine, seleziona **Mai**. |
| Gruppo di sequenze numeriche | Gruppo di sequenza numerica che verrà utilizzato per generare i numeri di documento durante il periodo. |
| Gruppo di sequenze numeriche originale | Questo codice di gruppo di sequenza numerica viene utilizzato per i filtri aggiuntivi nei casi in cui i documenti hanno già un specifico gruppo di sequenze numeriche *permanente* assegnato. Un valore vuoto è considerato un valore specifico. Se è necessario ignorare un gruppo assegnato preliminarmente, utilizza l'opzione **Predefinito** per questa configurazione. |
| Predefinita | Se attivato, il sistema ignora il gruppo di sequenza numerica documento assegnato in precedenza e utilizza solo le date di inizio e di fine dei periodi per l'analisi di applicabilità. Se disattivato, il sistema utilizza la combinazione completa **Validità** + **Scadenza** + **Gruppo di sequenza numerica originale** per la selezione. |

## <a name="document-posting"></a>Registrazione del documento
Quando si registra un documento, il gruppo di sequenza numerica appropriato viene assegnato al documento, in base alla data di registrazione del documento, e quindi utilizzato per generare un numero di documento in base alla sequenza numerica rilevata. Il sistema fornisce un messaggio relativo all'assegnazione del gruppo di sequenze numeriche.

![Numero documento.](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> Per alcuni paesi esiste una logica specifica già implementata per la numerazione dei documenti. In questo caso, la logica specifica del paese avrà la precedenza sulla funzionalità **Numerazione cronologica**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
