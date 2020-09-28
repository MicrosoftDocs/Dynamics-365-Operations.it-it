---
title: Prestazioni di programmazione risorse di progetto
description: Questo argomento fornisce informazioni su come migliorare le prestazioni della programmazione delle risorse per un numero elevato di progetti.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760589"
---
# <a name="project-resource-scheduling-performance"></a>Prestazioni di programmazione risorse di progetto

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


I problemi di prestazioni relativi alla programmazione delle risorse possono verificarsi quando il numero di progetti raggiunge le migliaia. Per migliorare le prestazioni della programmazione delle risorse, è disponibile una funzione che consente agli utenti di ridurre il tempo necessario per avviare il modulo di disponibilità delle risorse. In particolare, viene rimosso il processo di sincronizzazione di roll-up della capacità delle risorse e utilizzata la tabella **ResProjectResource** per velocizzare la ricerca delle risorse. Notare che la tabella **ResRollup** non verrà più utilizzata.

> [!IMPORTANT]
> Se esiste una dipendenza dal processo di sincronizzazione di roll-up della capacità delle risorse o dalla tabella **ResProjectResource**, non utilizzare questa funzione.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Abilitare il miglioramento delle prestazioni della programmazione delle risorse
Per abilitare il miglioramento delle prestazioni della programmazione delle risorse, completare i seguenti passaggi.

1. Andare a **Gestione funzionalità** > **Tutto** e nell'elenco delle funzionalità individuare **Abilita il miglioramento delle prestazioni della programmazione delle risorse di progetto**.
2. Selezionare **Abilita ora**.

> [!NOTE]
> Se non si riesce a trovare la funzione nell'elenco, selezionare **Controlla aggiornamenti** per aggiornare l'elenco.

3. Aggiornare il browser, quindi andare a **Gestione progetti e contabilità** > **Periodico** > **Risorse di progetto** > **Sincronizza capacità dei calendari delle risorse per tutte le società**.
4. Impostare **Rimuovi record di capacità esistenti** su **Sì** per rimuovere i dati precedenti. Se si desidera generare dati incrementali, impostare su **No**.
5. Nel campo **Codice periodo** selezionare il periodo in cui generare i dati. Se si seleziona un codice periodo, non è necessario definire una data di inizio e di fine.
6. Se si lascia il campo **Codice periodo** vuoto, selezionare date di inizio e fine specifiche per generare i dati.
7. Selezionare **OK**.

 > [!NOTE]
 > Questo distribuirà i dati generali alla tabella **ResCalendarCapacity** per tutte le società dell'ambiente, quindi il processo batch deve essere eseguito solo in una persona giuridica. I dati in questo processo batch sono necessari per calcolare la capacità delle risorse tramite il calendario associato.

8. Andare a **Gestione progetti e contabilità** > **Periodico** > **Risorse di progetto** > **Popola risorse del progetto per tutte le società** e selezionare **OK**. Questo è lo script di aggiornamento per i dati generali nelle tabelle **ResProjectResource**, **ResCalendarDateTimeRange** e **ResEffectiveDateTimeRange**. I valori per il campo **PSAPRojSchedRole.RootActivity** vengono aggiornati. Se non viene eseguito, viene visualizzato un avviso quando si prova a eseguire le operazioni di pianificazione delle risorse.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Disattivare il miglioramento delle prestazioni della programmazione delle risorse

1. Andare a **Gestione funzionalità** > **Tutto** e individuare **Abilita il miglioramento delle prestazioni della programmazione delle risorse di progetto**.
2. Selezionare la funzione, quindi selezionare il pulsante **Disabilita**.
3. Aggiornare il browser.
4. Andare a **Gestione progetti e contabilità** > **Periodico** > **Sincronizzazione capacità** > **Sincronizza rollup capacità risorse**.
5. Nella pagina **Sincronizza rollup capacità** impostare **Rimuovi record di capacità esistenti** su **Sì** per rimuovere i dati precedenti. Se si desidera generare dati incrementali, impostare su **No**.
6. Nel campo **Codice periodo** selezionare il periodo in cui generare i dati. Se si seleziona un codice periodo, non è necessario definire una data di inizio e di fine.
7. Se si lascia il campo **Codice periodo** vuoto, selezionare date di inizio e fine specifiche per generare i dati.
8. Selezionare **OK**.

> [!NOTE]
> Questo distribuirà i dati generali alla tabella **ResRollup** per tutte le società dell'ambiente, quindi il processo batch deve essere eseguito solo in una persona giuridica. Questo processo batch è necessario per tutte le visualizzazioni **Disponibilità risorse**. Se questo processo batch non viene eseguito, i dati **ResRollup** verranno generati immediatamente, il che può richiedere tempo.
