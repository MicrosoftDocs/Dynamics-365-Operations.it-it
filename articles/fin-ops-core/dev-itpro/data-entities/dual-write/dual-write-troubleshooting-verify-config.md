---
title: Verificare la configurazione della doppia scrittura nelle app Finance and Operations e Dataverse
description: Questo argomento spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: af746d1d20ddd1552bce797288c6d62d69d7bd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748851"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificare la configurazione della doppia scrittura nelle app Finance and Operations e Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verificare che sia configurata la doppia scrittura in un'app Finance and Operations

Per determinare se gli errori visualizzati quando si tentano di salvare le righe per l'aggiornamento provengono dalla doppia scrittura, verificare innanzitutto che la doppia scrittura sia configurata.

+ Se si dispone dei privilegi di amministratore nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Doppia scrittura**. Se vengono visualizzati i dettagli degli ambienti collegati e l'elenco delle mappe della tabella in esecuzione, è configurata la doppia scrittura.

    ![Verifica della connessione dell'app Finance and Operations quando si dispone dei privilegi di amministratore](media/verify_fin_ops_1.png)

+ Se non si dispone dei privilegi di amministratore, viene visualizzato un messaggio di errore, *Impossibile scrivere i dati nell'entità \<entity name\>*. Nell'esempio della figura seguente, non è possibile creare una riga cliente nell'app Finance and Operations perché la doppia scrittura è configurata, ma i dati di riferimento del gruppo di clienti e dei termini di pagamento non esistono in Dataverse.

    ![Verifica della connessione dell'app Finance and Operations quando non si dispone dei privilegi di amministratore](media/verify_fin_ops_2.png)

Per informazioni su come risolvere i problemi durante la creazione di dati nelle app Finance and Operations, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verificare che sia configurata la doppia scrittura in Dataverse

Quando si creano i dati, se la colonna **Società** è presente nelle pagine di Dataverse, la doppia scrittura è configurata.

![Verifica della connessione Dataverse](media/verify_cds.png)

Per informazioni su come risolvere i problemi durante la creazione di dati in Dataverse, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

Per informazioni su come visualizzare i dettagli dell'errore se si verificano errori durante la creazione dei dati in Dataverse, vedere [Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]