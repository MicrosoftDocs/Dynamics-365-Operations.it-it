---
title: Ritenuta d'acconto per l'Italia
description: In questo argomento viene illustrato come configurare le impostazioni specifiche per l'Italia per la ritenuta d'acconto e i report italiani relativi alla ritenuta d'acconto.
author: Anasyash
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 272733
ms.assetid: a5628f89-2ebb-4df2-a8a5-522649fb66da
ms.search.region: Italy
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f2194b8457c55f16bd972ab44e338da26cbe274a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408091"
---
# <a name="withholding-tax-for-italy"></a>Ritenuta d'acconto per l'Italia

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come configurare le impostazioni specifiche per l'Italia per la ritenuta d'acconto e i report italiani relativi alla ritenuta d'acconto.

Per l'Italia, gli acquirenti devono soddisfare alcuni requisiti legali specifici del paese che comportano la trattenuta della ritenuta d'acconto per alcuni tipi di pagamenti fornitore, ad esempio per i pagamenti dei lavoratori autonomi. La società deve quindi versare questa imposta all'ufficio tributario. La ritenuta d'acconto è un'imposta trattenuta dall'importo del pagamento per le fatture fornitore. In questo argomento vengono descritte le impostazioni specifiche per Italia relative alla ritenuta d'acconto e i seguenti report italiani: **Ritenuta d'acconto - certificazione**, **Ritenuta d'acconto - mensile** e **Ritenuta d'acconto - annuale**. Impostare i codici della ritenuta d'acconto in **Imposta** &gt; **Imposte indirette** &gt; **Ritenuta d'acconto** &gt; **Codici ritenuta d'acconto**. Definire le impostazioni standard nelle Schede dettaglio **Generale** e **Calcolo**. Nella scheda dettaglio **Reporting italiano** definire le seguenti impostazioni.

|Gruppo campi|Campo|descrizione|
|------------|----------------|----------------|
|Tipo di voce   |Codice causale ritenuta d'acconto|Selezionare il riferimento utilizzato quando viene effettuato un pagamento agli uffici tributari.|
|Tipo di voce   |Origine|Specificare se riepilogare l'imposta registrata in base all'origine (ritenuta a titolo di imposta o ritenuta a titolo di acconto). Questo campo viene utilizzato nei report **Ritenuta d'acconto - certificazione** e **Ritenuta d'acconto - annuale**.|
|Tipo di voce   |Facoltà dichiarazione percettore|Specificare se riepilogare l'imposta registrata in base al destinatario (il destinatario con o senza facoltà dichiarazione percettore). Questo campo viene utilizzato nei report **Ritenuta d'acconto - certificazione** e **Ritenuta d'acconto - annuale**.|
|Dichiarazione annuale - 770|Tipo di servizio|Immettere il codice per il tipo di servizio. Il codice viene utilizzato come classificazione nella dichiarazione annuale.|
|Dichiarazione annuale - 770|Quadro 770|Immettere il codice per la sezione della dichiarazione fiscale annuale in cui deve essere inclusa la ritenuta.|

Nel **Riquadro azioni** fare clic su **Valori** e impostare i valori per il codice ritenuta d'acconto.

| Campo            | descrizione                                                                                  |
|------------------|----------------------------------------------------------------------------------------------|
| Dal        | Immettere la prima data a partire dalla quale la percentuale di ritenuta d'acconto è valida.                     |
| Al          | Immettere l'ultima data per cui la percentuale di ritenuta d'acconto è valida.                      |
| Limite minimo    | Immettere l'imponibile minimo per il calcolo della ritenuta d'acconto.                           |
| Limite massimo    | Immettere l'imponibile massimo per il calcolo della ritenuta d'acconto.                           |
| Valore            | Immettere il valore percentuale della ritenuta d'acconto.                                                  |
| % non deducibile | Immettere la percentuale utilizzata per ridurre l'importo imponibile prima del calcolo della ritenuta d'acconto. |

Nel Riquadro azioni fare clic su **Limiti** e impostare i limiti per l'importo della ritenuta d'acconto.

| Campo                   | descrizione                                                                                                            |
|-------------------------|------------------------------------------------------------------------------------------------------------------------|
| Dal               | Immettere la prima data di applicazione dei limiti di ritenuta d'acconto. La data di registrazione determina l'intervallo di limiti utilizzato.  |
| Al                 | Immettere l'ultima data di applicazione dei limiti di ritenuta d'acconto. La data di registrazione determina l'intervallo di limiti utilizzato.   |
| Ritenuta minima | Immettere l'importo minimo della ritenuta d'acconto che è possibile registrare per qualsiasi transazione per il codice ritenuta d'acconto selezionato. |
| Ritenuta massima | Immettere l'importo massimo della ritenuta d'acconto che è possibile registrare per qualsiasi transazione per il codice ritenuta d'acconto selezionato. |

Impostare i gruppi di ritenuta d'acconto in **Imposta** &gt; **Imposte indirette** &gt; **Ritenuta d'acconto** &gt; **Gruppi ritenute d'acconto**. Immettere il codice e il nome per un gruppo di ritenute d'acconto e assegnare un codice di ritenuta d'acconto al gruppo. Per ulteriori informazioni, vedere [Impostare la ritenuta d'acconto](../general-ledger/tasks/set-up-withholding-tax.md). Impostare un conto fornitore per il calcolo della ritenuta d'acconto in **Contabilità fornitori** &gt; **Fornitori** &gt; **Tutti i fornitori**. Definire le seguenti impostazioni.


|         Scheda dettaglio         |              Campo               |                                descrizione                                |
|-------------------------|----------------------------------|---------------------------------------------------------------------------|
|  Fattura e consegna   |    Calcola ritenuta d'acconto     |   Impostare questa opzione su <strong>Sì</strong> per calcolare la ritenuta d'acconto.   |
|  Fattura e consegna   |        Gruppo ritenute d'acconto         |                           Gruppo ritenute d'acconto                           |
|  Fattura e consegna   |           Codice fiscale            |                          Immettere il codice fiscale.                           |
| Dati demografici acquisti | Paese estero di residenza |                        Selezionare il paese.                         |
| Dati demografici acquisti |           Luogo di nascita            |                         Immettere il luogo di nascita.                         |
|         Generale         |   Data di nascita - Giorno, mese, anno    | Immettere la data di nascita per un fornitore di tipo <strong>Persona</strong>. |

Per eseguire i report specifici dell'Italia relativi alla ritenuta d'acconto, passare a **Imposta** &gt; **Richieste di informazioni e report** &gt; **Report ritenuta d'acconto**:

-   **Ritenuta d'acconto - certificazione** - Questo report viene utilizzato per stampare un report di certificazione per l'Italia nella valuta della ritenuta d'acconto. Il report è predisposto per essere inviato al fornitore. Include i dati della ritenuta d'acconto per il periodo specificato. Il report certifica al fornitore che gli importi dell'imposta sono stati trattenuti durante il periodo di reporting.
-   **Ritenuta d'acconto - mensile** - Questo report viene utilizzato per stampare, per ciascun conto fornitore, i dettagli degli importi di ritenuta d'acconto per tutte le fatture pagate durante il mese: il codice motivo della ritenuta d'acconto, l'importo totale, l'importo non soggetto a ritenuta, l'importo non tassabile per Reg. Conv., l'importo non tassabile, la base tassabile e l'importo della ritenuta d'acconto. Se l'utente seleziona per stampare i dettagli nella finestra di dialogo, il report mostra i dettagli dell'importo in base a data del documento e numero di fattura.
-   **Ritenuta d'acconto - annuale** - Questo report viene utilizzato per stampare, per ciascun conto fornitore, gli importi risultanti della ritenuta d'acconto. Tali importi vengono raggruppati in base al codice di ritenuta d'acconto e i dettagli vengono inclusi nella fattura. A seconda delle impostazioni di **Origine** e **Facoltà dichiarazione percettore** sul codice ritenuta d'acconto, il report mostra inoltre gli importi totali: importi totali che il percettore può o meno dichiarare e l'importo totale di ritenuta a titolo di imposta e ritenuta a titolo di acconto.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]