---
title: Rivalutare i canoni di leasing collegati a un tasso di indicizzazione
description: In questo articolo viene descritta la rettifica effettuata per l'obbligazione sul leasing per un asset Right of use quando i canoni di leasing variabili cambiano a causa di una variazione del tasso di indicizzazione.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8dc2325e9f0651bea0d70d9f66e5d88b741009f8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903249"
---
# <a name="revalue-lease-payments-that-are-linked-to-an-index-rate"></a>Rivalutare i canoni di leasing collegati a un tasso di indicizzazione

[!include [banner](../includes/banner.md)]

In questo articolo viene descritta la rettifica effettuata per l'obbligazione sul leasing per un asset Right of use quando i canoni di leasing variabili cambiano a causa di una variazione del tasso di indicizzazione. L'obbligazione sul leasing e l'asset Right of use saranno rettificati per contabilizzare i nuovi importi del pagamento. Ai sensi del principio Accounting Standards Codification Topic 842 (ASC 842), che è lo standard nei Principi contabili generalmente accettati negli Stati Uniti (US GAAP), solo i pagamenti variabili cambiano quando i pagamenti aumentano o diminuiscono a causa di una variazione del tasso di indicizzazione, a meno che non ci siano ulteriori modifiche ai flussi di cassa. Queste modifiche aggiuntive potrebbero includere una modifica dei termini del leasing correlata ai tassi di interesse. Per ulteriori informazioni, vedi ASC 842-10-55-225 e il paragrafo 42 (b) dell'International Financial Reporting Standard 16 (IFRS 16).

## <a name="adjust-lease-payments"></a>Rettificare i canoni del leasing

Segui questi passaggi per rivalutare i canoni di leasing collegati a un tasso di indicizzazione.

1. Per eseguire il processo di rivalutazione dell'indice di leasing, vai a **Leasing cespite \> Periodico \> Rivalutazione tasso di indicizzazione**.

    La pagina **Rivalutazione tasso di indicizzazione** viene visualizzata e mostra tutti i precedenti processi di rivalutazione dell'indice di leasing che sono stati eseguiti. Le informazioni in questa pagina includono l'ID processo generato dalla configurazione della sequenza numerica, la persona giuridica, il numero di libri di leasing che sono stati rettificati, la rettifica della passività totale per leasing IFRS 16 e i pagamenti variabili totali che sono stati rettificati per leasing ASC 842.

2. Per eseguire la rivalutazione, nel riquadro azioni seleziona **Rivalutazione indice leasing**.

    Viene visualizzata la finestra di dialogo **Parametri rivalutazione indice**. Qui è possibile filtrare e selezionare i leasing, i gruppi di leasing o altri criteri da utilizzare quando si selezionano i leasing da rivalutare. Inoltre, nella scheda **Esegui in background**, puoi configurare il processo di rivalutazione dell'indice in modo che venga eseguito in batch.

4. Seleziona i filtri per la selezione dei leasing da includere nell'elaborazione in background, quindi seleziona **OK**.

    Viene visualizzata la finestra di dialogo **Anteprima rivalutazione tasso di indicizzazione** che mostra i leasing che verranno rivalutati. Mostra anche le rettifiche di attività e passività o le rettifiche di pagamento variabile.

5. Per evitare che i leasing vengano rivalutati, seleziona i leasing che **dovrebbero** essere rivalutati. Se non selezioni alcun leasing, tutti i leasing verranno rivalutati. Al termine, seleziona **OK** per rivalutare i canoni di leasing.
6. Per visualizzare le transazioni create per un processo di rivalutazione dell'indice specifico, seleziona l'ID processo, quindi seleziona **Transazioni**.

    Viene visualizzata una finestra di dialogo che mostra i dettagli delle transazioni create durante l'elaborazione.

> [!NOTE]
> Possono essere rivalutati solo i leasing che hanno una data di rivalutazione uguale o precedente alla data di sistema. Il sistema ignora automaticamente tutti i leasing la cui data di rivalutazione è successiva alla data di sistema.

## <a name="asc-842-leases--index-revaluation"></a>Leasing ASC 842 - Rivalutazione indice

Per visualizzare gli effetti del processo di rivalutazione del leasing sui leasing ASC 842, apri lo scadenziario pagamenti per un leasing. La pagina mostra solo i pagamenti variabili effettuati in data o dopo la modifica della data di rivalutazione a causa della rivalutazione dell'indice. I piani di ammortamento restano invariati. Quando crei una fattura con un pagamento variabile, il pagamento variabile viene addebitato sul conto di registrazione pagamento variabile. Inoltre, l'importo del pagamento variabile viene aggiunto al movimento di accredito registrato direttamente al fornitore o registrato nel conto Effetti passivi, a seconda della configurazione del libro di leasing.

Le righe dello scadenzario pagamenti nella pagina dei dettagli del leasing vengono aggiornate automaticamente con una nuova riga che indica il nuovo tasso di indicizzazione. Inoltre, una colonna mostra se la riga è stata creata manualmente o tramite il processo di rivalutazione dell'indice.

## <a name="ifrs-16-leases--index-revaluation"></a>Leasing IFRS 16 - Rivalutazione indice

Per visualizzare gli effetti del processo di rivalutazione del leasing sui leasing IFRS 16, apri i dettagli del leasing per un leasing rettificato. I campi **Termine del leasing** e **Vita utile cespite** sono stati aggiornati per riflettere il tempo trascorso dalla data di inizio o dalla data di modifica alla data di rivalutazione. Inoltre, le righe dello scadenzario pagamenti sono state aggiornate per riflettere i nuovi pagamenti sul leasing, il nuovo tasso di indicizzazione e il modo in cui è stata creata la riga.

È possibile visualizzare lo scadenziario pagamenti appena generato che inizia alla data di rivalutazione e mostrare l'importo totale del pagamento aggiornato. Sono stati inoltre creati un nuovo piano di ammortamento dell'obbligazione sul leasing e un piano di ammortamento dei cespiti per riflettere lo scadenziario dei pagamenti rettificato.

La scrittura contabile ha registrato automaticamente la scrittura contabile di rettifica nel conto per la modifica dei canoni di leasing correlati alla rivalutazione dell'indice.

> [!NOTE]
> Se l'opzione **Suddivisione importo pagamento** è abilitata nella scheda dettaglio **Generale** della pagina **Dettagli leaseing** e il libro associato è l'IFRS 16, il processo di rivalutazione dell'indice aggiungerà automaticamente un record nella finestra di dialogo **Suddivisione importo pagamento**. L'importo rifletterà la modifica apportata al pagamento a causa della rivalutazione dell'indice. Il record verrà contrassegnato come **Utilizzato per rivalutazione indice IRFS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
