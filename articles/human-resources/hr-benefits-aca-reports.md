---
title: Generare report Affordable Care Act (ACA)
description: La rendicontazione Affordable Care Act (ACA) genera i moduli 1095-B e 1095-C a sostegno della quota **Mandato del datore di lavoro** dell'Affordable Care Act.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067003"
---
# <a name="generate-aca-reports"></a>Generare report ACA


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La rendicontazione Affordable Care Act (ACA) genera i moduli 1095-B e 1095-C a sostegno della quota **Mandato del datore di lavoro** dell'Affordable Care Act.

> [!NOTE]
> La rendicontazione ACA è abilitato solo per le persone giuridiche negli Stati Uniti.

## <a name="getting-started"></a>Introduzione

Per tenere traccia delle informazioni per i moduli 1095-B e 1095-C, creare prima uno o più gruppi di copertura Affordable Care. I gruppi di copertura Affordable Care indicano:

- L'offerta di copertura per un dipendente
- La quota del dipendente del premio mensile più basso, se il costo è superiore alla soglia di povertà federale
- Safe Harbor utilizzato dal datore di lavoro, se applicabile

I gruppi di copertura Affordable Care consente di gestire le informazioni relative a questi campi senza dover cambiare record dipendente per il quale le condizioni siano identiche. Puoi facilmente assegnare gruppi di copertura Affordable Care a uno o più dipendenti utilizzando l'opzione **Assegnazione di massa** nella pagina.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Gestione di più versioni di un gruppo di copertura

Puoi mantenere più versioni di qualsiasi gruppo di copertura. Questa funzionalità consente di apportare modifiche senza dover creare un nuovo gruppo e riassegnarvi i dipendenti. 

Dopo aver creato i gruppi di copertura ACA, è possibile assegnare in massa i gruppi ai dipendenti con l'opzione **Assegnazione di massa**. Puoi anche indicare singolarmente se monitorare e segnalare le informazioni ACA e assegnare un dipendente a un gruppo di copertura Affordable Care.

Non è necessario tenere traccia di alcune informazioni sulla copertura ACA, ad esempio per i dipendenti part-time. In questo caso, imposta il campo **Copertura del rapporto** su **No**. Sebbene sia necessario assegnare a ciascun dipendente informazioni ACA tracciabili a un gruppo di copertura Affordable Care, puoi comunque modificare le seguenti opzioni per mesi con valori diversi:

- **Offerta di copertura**
- **Quota costo dipendente**
- **Safe Harbor**

Per immettere le eccezioni per i valori di gruppo di copertura Affordable Care, seleziona il collegamento **Copertura Affordable Care** nella pagina **Dettagli lavoratore**, che si trova sotto la sezione **Informazioni aggiuntive** nella **scheda Impiego**.

## <a name="reporting-health-care-coverage"></a>Report di copertura delle spese mediche

Oltre a tenere traccia di qualsiasi copertura di assicurazione sanitaria offerta a dipendenti a tempo pieno, se il datore di lavoro offre una copertura sanitaria autoassicurata patrocinata dal datore di lavoro per cui il dipendente è iscritto (indipendentemente dal fatto che si tratti di un dipendente a tempo pieno o parziale), le informazioni aggiuntive devono essere dichiarate nel modulo 1095-C. Ciascun dipendente (dipendenti inclusi) coperto dai piani di benefit patrocinati da datore di lavoro deve essere incluso nel report per i mesi per cui sono stati coperti. 

Puoi indicare se si desidera che ciascun piano di benefit debba essere dichiarato selezionando la casella di controllo **Dichiarabile all'ACA**.

Inoltre, se i dipendenti hanno scelto di avere uno dei relativi dipendenti coperti da un benefit, è possibile indicare le date in cui il dipendente era coperto per ciascun dipendente nella pagina **Gestisci benefit**. Per indicare che il dipendente è coperto dal benefit, seleziona il pulsante **Modifica** nel riquadro azioni della Scheda dettaglio **Dipendenti**.

Nella pagina **Gestione date di copertura persone a carico**, è possibile indicare le date in cui il dipendente è stato coperto dal benefit. Immettendo le date in questa pagina verrà automaticamente selezionata la casella di controllo **Coperto** nella pagina **Gestisci benefit**.

## <a name="generate-1095-b-and-1095-c-forms"></a>Genera moduli 1095-B e 1095-C

Puoi inoltre generare i moduli 1095-B e 1095-C dal prodotto e distribuirli a ciascuno dei dipendenti. Il sistema può anche generare elettronicamente moduli 1095-C e file di trasmissione IRS 1094-C.  

Durante la generazione del modulo 1095-C, immettere l'anno fiscale appropriato e indicare se i numeri di previdenza sociale devono essere mascherati. Quando si stampano moduli 1095-C per più di 500 dipendenti, si riceveranno più di un file PDF. Si consiglia di aumentare il valore **Dimensioni massime di file** nella finestra **Parametri di gestione documenti** a 150 MB.

## <a name="viewing-information"></a>Visualizzazione delle informazioni

È possibile utilizzare la pagina **Copertura Affordable Care Act del lavoratore** per visualizzare i dipendenti assegnati a ciascun gruppo di copertura, quelli che non devono essere inclusi in un report e i dipendenti che non sono assegnati.

Se uno qualsiasi dei valori predefiniti del gruppo di copertura Affordable Care viene sovrascritto, un asterisco verrà visualizzato accanto al valore modificato. Se i valori per tutti i 12 mesi sono uguali e non sono stati ignorati, il valore verrà stampato nella colonna **Tutti i 12 mesi**.

Puoi, inoltre, utilizzare la finestra di richiesta per capire quali dipendenti sono stati contrassegnati come non soggetti a comunicazione ACA. Non è necessario monitorare se è stata offerta loro la copertura e non sarà necessario emettere un 1095-C alla fine dell'anno. Seleziona **Non segnalabile ACA** nel campo **Filtra per** per generare un elenco di tutti i dipendenti che non riceveranno un 1095-C.

Oltre a visualizzare i dipendenti che non sono assegnati (il campo **Dichiara copertura ACA** è vuoto) o assegnati a un gruppo di copertura Affordable Care che è scaduto per l'anno selezionato nel campo **Anno**.

È possibile esportare gli elenchi di dipendenti generati mediante una delle opzioni di filtro in Excel.

Se devi segnalare le persone coperte perché fornisci una copertura autoassicurata, puoi visualizzare qualsiasi dipendente coperto da piani di benefit che sono contrassegnati come **Non segnalabile ACA**. Seleziona **Visualizza copertura dipendente** nel riquadro azioni.

> [!NOTE]
> Solo i piani di benefit contrassegnati come **Segnalabile ACA** vengono visualizzati nella finestra di richiesta di informazioni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
