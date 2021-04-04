---
title: Configurare i libri di leasing
description: In questo argomento vengono descritte le informazioni conservate nei libri di leasing. I libri di leasing contengono i criteri contabili che determinano la modalità di contabilizzazione di un leasing nel sistema.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f5eac47448835dae5837b31c59a72833652f63bf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249655"
---
# <a name="set-up-lease-books"></a>Configurare i libri di leasing

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I libri di leasing contengono i criteri contabili che determinano la modalità di contabilizzazione di un leasing nel sistema. Oltre alla contabilità di cassa, Leasing cespite supporta i seguenti standard:

- Principi contabili generalmente accettati negli Stati Uniti (US GAAP)
- Accounting Standards Codification Topic 842 (ASC 842)
- ASC 840
- International Financial Reporting Standard 16 (IFRS 16)
- International Accounting Standard 17 (IAS 17)

Per creare un libro di leasing, procedi come segue.

1. Vai a **Leasing cespiti \> Imposta \> Libri di leasing**.
2. Seleziona **Nuovo** per aggiungere un libro.
3. Impostare i seguenti campi.

    | Nome                                     | Descrizione |
    |------------------------------------------|-------------|
    | Livello di registrazione                            | Seleziona il livello di registrazione da utilizzare. Ogni libro allegato a un leasing è configurato per uno specifico livello di registrazione. Ogni livello di registrazione ha scopi di registrazione diversi. |
    | Tipo di leasing                               | Seleziona se il leasing deve essere classificato automaticamente o se deve essere predefinito come leasing finanziario o operativo. |
    | Framework di contabilità                     | Seleziona il framework associato al libro. |
    | Configurazione termine del leasing/vita utile          | Il sistema classificherà il leasing come leasing finanziario se il tipo di leasing è impostato su **Automatico** e se il termine del leasing sulla vita utile del cespite è maggiore o uguale alla percentuale immessa in questo campo.  |
    | Configurazione valore corrente/valore equo cespite   | Immetti un numero intero per definire la soglia che determinerà il tipo di leasing. Se il valore attuale dei canoni di leasing minimi futuri è superiore al valore definito dall'utente dalla configurazione del libro e se la classificazione del leasing del libro è impostata su automatica, il sistema classificherà il leasing come finanziario. |
    | Soglia a breve termine                     | Immetti il numero di mesi da utilizzare come soglia per i leasing a breve termine. Se il termine del leasing è inferiore o uguale al numero di mesi che immetti qui, il sistema classificherà il leasing come un leasing a breve termine e verrà applicato il trattamento della passività sui contratti. |
    | Soglia valore basso                      | Immetti un importo da utilizzare come soglia per i leasing a valore basso. Se il valore equo del cespite è inferiore o uguale al valore immesso qui, il sistema classificherà il leasing come un leasing a valore basso e verrà applicato il trattamento della passività sui contratti. |
    | Paga il fornitore                            | Imposta questa opzione su **Sì** per consentire la registrazione dei canoni di leasing, come fattura, nel conto fornitore specificato in ogni leasing. Quando viene registrato un canone di leasing, verrà accreditato il conto fornitore. Se questa opzione è impostata su **No**, il conto specificato per il tipo di registrazione **Canone di leasing** nella pagina **Parametri di registrazione del leasing** verrà invece accreditato. |
    | Convenzione di leasing                       | Seleziona la convenzione per la data di inizio del contratto di leasing:<ul><li><b>Nessuno</b>: utilizza la data di inizio del contratto di leasing come data di inizio.</li><li><b>Mese intero</b>: usa il primo giorno del mese in cui cade la data di inizio del leasing come data di inizio.</li></ul><p>Se selezioni <b> Nessuna</b>, vi è il rischio che i piani di ammortamento delle passività e dei beni patrimoniali maturino e registrino le spese a metà mese invece che alla fine del mese. Selezionando <b> Mese intero</b>, ti assicuri che il sistema inizi a contabilizzare il leasing il primo giorno del mese e che la spesa dell'intero mese verrà accumulata e registrata l'ultimo giorno del mese.</p><p><strong>Nota:</strong> la funzionalità per le convenzioni di leasing deve essere attivata tramite Feature Management. Nell'area di lavoro <b>Gestione delle funzionalità</b> trova e seleziona la funzione denominata <b>Convenzione di leasing per leasing di cespiti</b> quindi seleziona <b>Abilita ora</b>.</p> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]