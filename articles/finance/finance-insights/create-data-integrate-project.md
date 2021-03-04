---
title: Creare un progetto di integrazione dei dati (anteprima)
description: Questo argomento spiega come creare un progetto di integrazione dei dati.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: fb17d5e82709a34ff088774d9e9034adb714b58c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646255"
---
# <a name="create-a-data-integrator-project-preview"></a>Creare un progetto di integrazione dei dati (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento spiega come creare un progetto di integrazione dei dati.

1. Accedere a Microsoft Dynamics 365 Finance.
2. Vai a **Aree di lavoro \> Gestione dati** e seleziona **Entità di dati**. Attendi che tutte le entità di dati siano state aggiornate prima di passare alla fase successiva.
3. Apri il [portale di Power Apps](https://make.powerapps.com/) e segui questi passaggi:

    1. Seleziona l'ambiente appropriato.
    2. Nel riquadro di spostamento sinistro, seleziona **Dati \> Connessioni**.
    3. Connettiti alle istanze appropriate dei seguenti elementi:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

4. Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:

    1. Seleziona **Integrazione dei dati**.
    2. Seleziona **Set di connessioni**.
    3. Seleziona **Nuovo set di connessioni**.
    4. Immetti un nome per la connessione.
    5. Seleziona le connessioni appropriate per i seguenti elementi:

        - Dynamics 365
        - Dynamics 365 for Fin & Ops

    6. Seleziona il mapping dell'organizzazione appropriata.
    7. Selezionare **Crea**.

5. Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:  

    1. Crea progetti di integrazione dati per i seguenti modelli utilizzando il set di connessione appena creato:

        - Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)
        - Risultati delle serie temporali del flusso di cassa (da CDS a Fin and Ops)
        - Risultati delle serie temporali del budget (da CDS a Fin and Ops)

    2. Imposta la pianificazione appropriata per ogni progetto.

> [!NOTE]
> Se non vedi le entità richieste in CDS, vai a **Credito e riscossioni > Imposta> Informazioni finanziarie dettagliate > Parametri delle informazioni dettagliate finanziarie**, abilita la funzionalità Previsioni di pagamento del cliente e fai clic sul pulsante **Crea modello di previsione**. Quando la distribuzione del modello di intelligenza artificiale è completata (riuscita o non riuscita), le entità CDS necessarie per creare l'integrazione verranno distribuite in CDS.

## <a name="privacy-notice"></a>Informativa sulla privacy

Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]