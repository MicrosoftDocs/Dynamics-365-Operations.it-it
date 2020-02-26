---
title: Guida alla risoluzione dei problemi di integrazione dei dati
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione dei dati tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019861"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guida alla risoluzione dei problemi di integrazione dei dati

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Abilitare i registri di traccia plug-in in Common Data Service ed analizzare i dettagli degli errori del plug-in di doppia scrittura.

Se si verifica un problema o un errore durante la sincronizzazione della doppia scrittura, seguire i passaggi seguenti per analizzare gli errori nel registro di traccia:

1. Per poter analizzare gli errori, è necessario abilitare i registri di traccia plug-in. Per istruzioni, vedere la sezione "Visualizzare registri di traccia in [Esercitazione: Scrivere e registrare un plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    A questo punto è possibile analizzare gli errori.

2. Accedere a Microsoft Dynamics 365 Sales.
3. Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi selezionare **Impostazioni avanzate**.
4. Nel menu **Impostazioni**, scegliere **Personalizzazione \> Registro di traccia plug-in**.
5. Selezionare **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** come nome di tipo per visualizzare i dettagli dell'errore.

## <a name="inspect-dual-write-synchronization-errors"></a>Analizzare gli errori di sincronizzazione della doppia scrittura

Seguire questi passaggi per analizzare gli errori durante i test.

1. Accedere a Microsoft Dynamics Lifecycle Services (LCS).
2. Aprire il progetto LCS per il quale eseguire i test della doppia scrittura.
3. Selezionare **Distribuzione ambienti ospitati nel cloud**.
4. Eseguire una connessione Desktop remoto alla macchina virtuale (VM) dell'applicazione utilizzando l'account locale visualizzato in LCS.
5. Aprire il visualizzatore eventi. 
6. Andare a **Registri applicazioni e servizi \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operativo**. Gli errori e i dettagli vengono visualizzati.

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a>Scollegare un ambiente Common Data Service dall'applicazione e collegare un altro ambiente

Seguire i passaggi seguenti per aggiornare i collegamenti.

1. Accedere all'ambiente dell'applicazione.
2. Aprire Gestione dati.
3. Selezionare **Collega a CDS per le app**.
4. Selezionare tutti i mapping in esecuzione, quindi selezionare **Interrompi**.
5. Selezionare tutti i mapping e quindi selezionare **Elimina**.

    > [!NOTE]
    > L'opzione **Elimina** non è disponibile se il modello **CustomerV3-Account** è selezionato. Annullare la selezione di questo modello come necessario. **CustomerV3-Account** è un modello meno recente fornito e funziona con la soluzione Prospect to Cash. Poiché è rilasciato a livello globale, è visualizzato sotto tutti i modelli.

6. Selezionare **Scollega ambiente**.
7. Selezionare **Sì** per confermare l'operazione.
8. Per collegare il nuovo ambiente, seguire i passaggi nella [guida all'installazione](https://aka.ms/dualwrite-docs).
