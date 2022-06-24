---
title: Verificare la configurazione della doppia scrittura nelle app per la finanza e le operazioni e in Dataverse
description: Questo articolo spiega come determinare se è configurata la doppia scrittura nelle app per finanza e operazioni e in Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 7131e6c2c4ca4d9c6bb84ad74bf425faf28bd92c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884461"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificare la configurazione della doppia scrittura nelle app per la finanza e le operazioni e in Dataverse

[!include [banner](../../includes/banner.md)]





In questo articolo vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse. In particolare, spiega come determinare se è configurata la doppia scrittura nelle app per finanza e operazioni e in Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verificare la doppia scrittura sia configurata in un'app per finanza e operazioni

Per determinare se gli errori visualizzati quando si tentano di salvare le righe per l'aggiornamento provengono dalla doppia scrittura, verificare innanzitutto che la doppia scrittura sia configurata.

+ Se si dispone dei privilegi di amministratore nell'app per finanza e operazioni, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Doppia scrittura**. Se vengono visualizzati i dettagli degli ambienti collegati e l'elenco delle mappe della tabella in esecuzione, è configurata la doppia scrittura.

    ![Verifica della connessione dell'app per finanza e operazioni quando non si dispone dei privilegi di amministratore.](media/verify_fin_ops_1.png)

+ Se non si dispone dei privilegi di amministratore, viene visualizzato un messaggio di errore, *Impossibile scrivere i dati nell'entità \<entity name\>*. Nell'esempio della figura seguente, non è possibile creare una riga cliente nell'app per finanza e operazioni perché la doppia scrittura è configurata, ma i dati di riferimento del gruppo di clienti e dei termini di pagamento non esistono in Dataverse.

    ![Verifica della connessione dell'app per finanza e operazioni quando non si dispone dei privilegi di amministratore.](media/verify_fin_ops_2.png)

Per informazioni su come risolvere i problemi durante la creazione di dati nelle app per finanza e operazioni, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verificare che sia configurata la doppia scrittura in Dataverse

Quando si creano i dati, se la colonna **Società** è presente nelle pagine di Dataverse, la doppia scrittura è configurata.

![Verifica della connessione Dataverse.](media/verify_cds.png)

Per informazioni su come risolvere i problemi durante la creazione di dati in Dataverse, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

Per informazioni su come visualizzare i dettagli dell'errore se si verificano errori durante la creazione dei dati in Dataverse, vedere [Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]