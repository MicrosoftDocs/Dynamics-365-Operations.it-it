---
title: Sincronizzare le capacità risorse
description: Questo argomento fornisce informazioni su come sincronizzare la capacità di una risorsa tra calendari e progetti.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760582"
---
# <a name="synchronize-resource-capacity"></a>Sincronizzare le capacità risorse

[!include [banner](../includes/banner.md)]

I processi per la sincronizzazione delle risorse garantiscono l'inserimento delle informazioni per il calendario e il calendario di base nella pianificazione delle risorse del progetto. Se il calendario viene modificato, i processi eseguono gli aggiornamenti necessari alla pianificazione delle risorse di progetto. I processi consentono anche di migliorare le prestazioni, poiché le informazioni sulle risorse del calendario vengono sincronizzate in anticipo. Di conseguenza, gli aggiornamenti alle informazioni sulla pianificazione delle risorse si verificano più rapidamente.. È consigliabile pianificare i processi come batch e non uno alla volta. In caso contrario, esiste il rischio che qualcuno dimentichi le date in cui le informazioni sono state sincronizzate l'ultima volta. Se le date incluse non vengono utilizzate, possono verificarsi dei vuoti durante la sincronizzazione delle date.

![Sincronizzazione del calendario](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizza rollup capacità risorse

Il processo di sincronizzazione è progettato per sincronizzare tutte le informazioni sul calendario delle risorse. Queste informazioni includono le informazioni sul calendario di base su tutte le modifiche alla tabella della capacità del calendario risorse del progetto. Se nuove risorse vengono aggiunte nel progetto, la sincronizzazione garantisce che le informazioni del calendario aggiornate siano disponibili. Questa sincronizzazione può essere eseguita in qualsiasi momento.

Si consiglia di utilizzare un batch. Le opzioni sono disponibili durante la sincronizzazione delle prenotazioni della capacità.

1. Selezionare **Gestione progetti e contabilità** &gt; **Periodico** &gt; **Sincronizzazione capacità** &gt; **Sincronizza rollup capacità risorse**.
2. Impostare le opzioni nella seguente tabella.

    | Opzione      | descrizione |
    |-------------|-------------|
    | Codice periodo | È possibile selezionare il codice intervallo date della contabilità generale per impostare le date di inizio e fine per il processo di sincronizzazione dei roll-up delle capacità delle risorse. |
    | Data di inizio  | Immettere la data di inizio del processo di sincronizzazione per i roll-up delle capacità delle risorse. |
    | Data di fine    | Immettere la data di fine del processo di sincronizzazione per i roll-up delle capacità delle risorse. |

[![Processo di sincronizzazione](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
