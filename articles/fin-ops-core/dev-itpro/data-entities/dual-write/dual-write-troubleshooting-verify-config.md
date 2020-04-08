---
title: Verificare che sia configurata la doppia scrittura nelle app Finance and Operations e in Common Data Service
description: Questo argomento spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172647"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Verificare che sia configurata la doppia scrittura nelle app Finance and Operations e in Common Data Service

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, spiega come determinare se è configurata la doppia scrittura nelle app Finance and Operations e in Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verificare che sia configurata la doppia scrittura in un'app Finance and Operations

Per determinare se gli errori visualizzati quando si tentano di salvare i record per l'aggiornamento provengono dalla doppia scrittura, verificare innanzitutto che sia configurata la doppia scrittura.

+ Se si dispone dei privilegi di amministratore nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Doppia scrittura**. Se vengono visualizzati i dettagli degli ambienti collegati e l'elenco delle mappe di entità in esecuzione, è configurata la doppia scrittura.

    ![Verifica della connessione dell'app Finance and Operations quando si dispone dei privilegi di amministratore](media/verify_fin_ops_1.png)

+ Se non si dispone dei privilegi di amministratore, viene visualizzato un messaggio di errore, *Impossibile scrivere i dati nell'entità \<nome entità\>*. Nell'esempio della figura seguente, non è possibile creare un record cliente nell'app Finance and Operations perché la doppia scrittura è configurata, ma i dati di riferimento del gruppo di clienti e dei termini di pagamento non esistono in Common Data Service.

    ![Verifica della connessione dell'app Finance and Operations quando non si dispone dei privilegi di amministratore](media/verify_fin_ops_2.png)

Per informazioni su come risolvere i problemi durante la creazione di dati nelle app Finance and Operations, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Verificare che sia configurata la doppia scrittura in Common Data Service

Quando si creano i dati, se il campo **Società** è presente nelle pagine di Common Data Service, la doppia scrittura è configurata.

![Verifica della connessione Common Data Service](media/verify_cds.png)

Per informazioni su come risolvere i problemi durante la creazione di dati in Common Data Service, vedere [Risoluzione dei problemi di sincronizzazione in tempo reale](dual-write-troubleshooting-live-sync.md).

Per informazioni su come visualizzare i dettagli dell'errore se si verificano errori durante la creazione dei dati in Common Data Service, vedere [Abilitare e visualizzare il log di traccia del plug-in Common Data Service per visualizzare i dettagli dell'errore](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
