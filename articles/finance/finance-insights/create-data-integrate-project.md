---
title: Creare un progetto di integrazione dei dati
description: Questo argomento spiega come creare un progetto di integrazione dei dati.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 956524e3778eed9898374952466f70c37c99163f
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968939"
---
# <a name="create-a-data-integration-project"></a>Creare un progetto di integrazione dei dati

[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare un progetto di integrazione dei dati.

1. Accedere a Microsoft Dynamics 365 Finance.
2. Vai a **Aree di lavoro \> Gestione dati** e seleziona **Entità di dati**. Attendi che tutte le entità di dati siano state aggiornate prima di passare alla fase successiva.
3. Apri il [portale di Power Apps](https://make.powerapps.com/) e segui questi passaggi:

    1. Seleziona l'ambiente appropriato.
    2. Nel riquadro di spostamento sinistro, seleziona **Dataverse \> Connessioni**.
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

        - Risultato delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops 10.0.17+)
        - Risultati delle serie temporali del flusso di cassa (da CDS a Fin and Ops)
        - Risultati delle serie temporali del budget (da CDS a Fin and Ops)

    2. Imposta la pianificazione appropriata per ogni progetto.

> [!NOTE]
> Se non vedi le entità richieste in CDS, vai a **Credito e riscossioni > Imposta > Finance Insights > Parametri di Finance Insights**, abilita la funzionalità Previsioni di pagamento del cliente e fai clic sul pulsante **Crea modello di previsione**. Quando la distribuzione del modello di intelligenza artificiale è completata (riuscita o non riuscita), le entità CDS necessarie per creare l'integrazione verranno distribuite in CDS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
