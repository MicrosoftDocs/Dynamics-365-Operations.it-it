---
title: Consenti modifiche ai dati interni dei giustificativi di contabilità generale
description: Questo articolo fornisce informazioni su come modificare i dati interni nei giustificativi di contabilità generale.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 26fc6518f0b4eae815e047db1dbaadd7c56a2e67
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220663"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Consenti modifiche ai dati interni dei giustificativi di contabilità generale

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]


Quando registri le voci contabili nella contabilità generale, il campo **Descrizione** viene spesso utilizzato per memorizzare note interne o documentazione. Se le informazioni non sono corrette, possono creare confusione e rendere più difficile la chiusura di fine periodo. Questa funzionalità consente al direttore amministrativo o al supervisore contabile di correggere gli errori modificando il campo **Descrizione** nei giustificativi registrati nella contabilità generale.

Le modifiche ai giustificativi registrati nella contabilità generale sono limitate ai dati di natura interna. Questa funzionalità non ti consentirà mai di modificare dati come importi, date di registrazione, conti CoGe e valuta delle transazioni. Le modifiche a tali dati influiranno sulla dichiarazione esterna dei rendiconti finanziari e devono essere apportate solo tramite nuovi giustificativi di contabilità generale.

> [!NOTE]
> Per Dynamics 365 Finance versione 10.0.29, questa funzionalità è limitata alle modifiche al campo **Descrizione**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Modificare i dati interni dei giustificativi di contabilità generale

Prima di poter modificare i dati interni sui giustificativi di contabilità generale, devi abilitare la funzionalità **Consenti modifiche ai dati interni dei giustificativi di contabilità generale** nell'area di lavoro in **Gestione funzionalità**.
Dopo l'abilitazione della funzionalità, all'utente che modificherà i giustificativi registrati deve essere assegnato il ruolo di Direttore amministrativo o Supervisore contabile. Puoi aggiungere autorizzazioni anche ad altri ruoli, personalizzando i ruoli di sicurezza.

Il processo di modifica è consentito solo dalla pagina Transazioni giustificativo.

1. Vai a **Contabilità generale** > **Richieste di informazioni e report** > **Transazioni giustificativo**.
2. Nella finestra di dialogo **SysQuery**, immetti i criteri di ricerca per selezionare giustificativi.
3. Seleziona le righe per i giustificativi che vuoi modificare, quindi seleziona **Modifica giustificativo** > **Modifica dati giustificativo interno**.

    [![Pagina Transazioni giustificativo.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
Nella pagina **Modifica dati giustificativo interno**, per ogni riga selezionata vengono visualizzati i seguenti dati:
  
  - Conto CoGe
  - Nome conto
  - Giustificativo
  - Descrizione corrente
  - Nuova descrizione

    [![Giustificativo giornale di registrazione.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Solo il campo **Nuova descrizione** può essere modificato. Per impostazione predefinita, il valore corrisponde al valore del campo **Descrizione corrente**, di modo che tu possa correggere errori minori nella descrizione.

4. Modifica il campo **Nuova descrizione** in ogni riga o elimina la descrizione da ogni riga.

   In alternativa, se devi aggiornare più righe con lo stesso valore, attieniti alla seguente procedura:

      1. Seleziona le righe da modificare, quindi seleziona **Aggiorna in blocco record selezionati**.
      2. Nel campo **Campo da modificare**, seleziona il campo da modificare. Attualmente, la ricerca include solo il campo **Nuova descrizione**.
      3. Nel campo **Nuovo valore**, immetti una nuova descrizione.
      4. Selezionare **Aggiornamento**. Tutti i record selezionati vengono aggiornati con il nuovo valore.

      [![Finestra di dialogo Aggiorna in blocco record selezionati.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. Nel campo **Motivo della modifica**, inserisci una nota per spiegare perché è stata effettuata la modifica. Questa nota è visualizzata nella pagina **Audit trail delle modifiche ai giustificativi**.

   È possibile apportare più modifiche allo stesso giustificativo e ogni modifica verrà monitorata.

## <a name="audit-trail-of-voucher-edits"></a>Audit trail delle modifiche ai giustificativi

Un audit trail specifico viene mantenuto per tenere traccia delle modifiche apportate tramite questa funzionalità. Puoi accedere all'audit trail delle modifiche ai giustificativi in due modi:

  - Vai a **Contabilità generale** > **Richieste di informazioni e report** > **Transazioni giustificativo**. Nella pagina **Richieste di buoni**, seleziona **Modifica giustificativo** > **Audit trail delle modifiche ai giustificativi**. L'audit trail viene visualizzato solo per il record di giustificativo selezionato. 
   
    Aprendo la richiesta di informazioni in questo modo, puoi concentrarti su tutte le modifiche apportate a un singolo record di giustificativo.
  
  - Vai a **Contabilità generale** > **Attività periodiche** > **Audit trail delle modifiche ai giustificativi**. Nella finestra di dialogo, immetti i criteri per specificare i giustificativi per i quali vuoi visualizzare l'audit trail delle modifiche. Per visualizzare l'audit trail per tutti i giustificativi, lascia vuoti i criteri e seleziona **OK**. 
    
    Aprendo la richiesta di informazioni in questo modo, puoi filtrare le modifiche apportate in una data specifica o da un utente specifico.

La pagina **Audit trail delle modifiche ai giustificativi** mostra le seguenti informazioni:

- **Data e ora di creazione**: la data e l'ora della modifica.
- **Motivo della modifica**: il motivo che l'utente ha inserito per la modifica.
- **Autore**: l'utente che ha apportato la modifica.

Per visualizzare i dettagli di ogni audit trail, esegui il drill-down del valore **Data e ora di creazione**. La pagina **Visualizza proprietà giustificativo modificato** mostra le stesse informazioni della pagina di modifica originale, inclusa la descrizione precedente e la descrizione aggiornata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
