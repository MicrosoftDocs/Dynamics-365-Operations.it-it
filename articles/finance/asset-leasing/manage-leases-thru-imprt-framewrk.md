---
title: Gestire i leasing tramite il framework di importazione dei leasing
description: Questo argomento spiega come utilizzare il framework di importazione dei leasing per rettificare più leasing contemporaneamente.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseImportHeader
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 083adf0a4bb74ac65e6f8b5077f65c74eb3fa337
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880912"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Gestire i leasing tramite il framework di importazione dei leasing

[!include [banner](../includes/banner.md)]

Questo argomento spiega come utilizzare il framework di importazione dei leasing per rettificare più leasing con un solo passaggio. Utilizzando questa funzionalità, puoi risparmiare tempo e puoi anche garantire rettifiche più accurate riducendo la possibilità di errore umano. Inoltre, questa funzionalità può connettere Microsoft Dynamics 365 Finance con entità di dati esterne per caricare i dati in modo efficiente.

Le seguenti entità di dati possono essere utilizzate per integrare Leasing cespite con sistemi esterni:

- Gestione temporanea leasing
- Gestione temporanea contratto di pagamento
- Gestione temporanea contratto esecutivo

È possibile utilizzare il processo di importazione per rettificare un leasing, aggiornare informazioni non finanziarie o aggiungere nuovi leasing. È possibile visualizzare e modificare i dati di leasing prima di importarli.

Il sistema può eseguire i tre processi seguenti tramite la suite di importazione dei leasing.

| Tipo di processo  | Descrizione |
|---------------|-------------|
| Aggiungere record    | I leasing migrati che hanno questo tipo di processo creano un leasing nel sistema. Lo scadenzario pagamenti deve essere confermato manualmente e la scrittura contabile di riconoscimento iniziale deve essere registrata manualmente dopo la migrazione. |
| Aggiorna record | I leasing migrati che hanno questo tipo di processo aggiornano i valori dei campi per un leasing che è già nel sistema. Solo i campi che sono stati selezionati nella pagina **Aggiorna selezione campi** vengono aggiornati. È consigliabile selezionare campi non finanziari nella pagina **Aggiorna selezione campi**, perché questo tipo di processo non rettifica il leasing. |
| Rettifica record | I leasing migrati che hanno questo tipo di processo rettificano il leasing. Questa rettifica determina una modifica del leasing finanziario. Dopo l'elaborazione del leasing, il sistema crea un nuovo scadenziario pagamenti utilizzando i nuovi dati dalla suite di importazione del leasing. Il sistema non conferma lo scadenzario pagamenti né registra la scrittura contabile di rettifica. |

Dopo che le informazioni sono state caricate tramite l'area di lavoro **Gestione dati** , apri la pagina **Importa intestazione** (**Leasing cespite \> Framework di importazione leasing \> Importa intestazione**). Questa pagina elenca tutte le importazioni delle tre entità di dati elencate in precedenza.

Per visualizzare i dati di staging del leasing prima dell'esecuzione dell'elaborazione, seleziona **dati di gestione temporanea**.

La funzione di confronto consente di confrontare un record che stai importando con il record corrispondente che è già nel tuo sistema. Per confrontare un singolo record di leasing, seleziona un leasing, quindi seleziona **Confronta**. È necessario completare questo passaggio per generare un report **Differenze** prima di migrare i record di leasing. La funzionalità Confronta mette a confronto i valori nei dati di gestione temporanea con i valori per i leasing attualmente nel sistema.

> [!NOTE]
> La funzionalità Confronta non funzionerà per i leasing con tipo di processo **Aggiungi record**, perché non c'è niente da confrontare con quel leasing.
>
> Per confrontare più leasing contemporaneamente, vai a **Leasing cespite \> Framework di importazione leasing \> Periodico** e seleziona **Confronta**.

Per ogni entità, puoi visualizzare le differenze tra ciò che è attualmente nel sistema e ciò che è nelle tabelle temporanee. Per ogni entità nelle tabelle di gestione temporanea, seleziona **Visualizza differenze**. La finestra di dialogo che appare mostra il valore corrente e il valore di gestione temporanea proposto.

È inoltre possibile aggiornare il valore di gestione temporanea modificandolo nella colonna **Nuovo valore** e quindi selezionando **Aggiorna gestione temporanea**.

Puoi convalidare i leasing per garantire che i record possano essere importati nel sistema senza introdurre errori. Prima che un record di leasing venga migrato, il sistema esegue diverse convalide per garantire che il record venga importato correttamente. Per convalidare un singolo leasing, seleziona **Convalida**.

> [!NOTE]
> Per convalidare più leasing contemporaneamente, vai a **Leasing cespite \> Framework di importazione leasing \> Periodico** e seleziona **Convalida**.

Per elaborare un singolo leasing, seleziona **Esegui migrazione record di leasing** nella pagina **Importa intestazione**. Quando un leasing viene migrato, il sistema esegue l'azione specificata nel campo **Tipo di processo**.

> [!NOTE]
> Per migrare più leasing contemporaneamente, vai a **Leasing cespite \> Framework di importazione leasing \> Periodico** e seleziona **Esegui migrazione**.

Dopo aver confrontato i leasing, è possibile eseguire un report per visualizzare le differenze per ogni leasing incluso nell'ID di importazione. Per eseguire il report per un leasing, selezionare tale leasing nei dati di gestione temporanea, quindi seleziona **Confronta e visualizza report \> Report sulle differenze**.

> [!NOTE]
> Per confrontare più leasing contemporaneamente, vai a **Leasing cespite \> Framework di importazione leasing \> Periodico** e seleziona **Confronta**. 

## <a name="set-up-update-fields"></a>Configurare i campi di aggiornamento

Se stai utilizzando il framework di importazione leasing per aggiornare i leasing e il tipo di processo è **Aggiorna record**, puoi selezionare campi specifici da aggiornare.

1. Vai a **Leasing cespite \> Framework di importazione leasing \> Imposta \> Aggiorna selezione campi**.
2. Nella pagina visualizzata, seleziona i campi da aggiornare, quindi seleziona la freccia verde per spostarli nell'elenco **Campi selezionati**. Solo i campi nell'elenco **Campi selezionati** possono essere aggiornati utilizzando la suite di importazione leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
