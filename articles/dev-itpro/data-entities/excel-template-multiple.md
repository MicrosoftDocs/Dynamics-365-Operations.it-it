---
title: "Importare i dati dai modelli di entità di dati di Excel con più fogli di lavoro"
description: "In questo argomento viene descritto come importare i dati mediante modelli di entità di dati Excel in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: 84b9e9128d7ea6cdf9949549f4ab7a1c6c01691b
ms.contentlocale: it-it
ms.lasthandoff: 12/14/2017

---

# <a name="excel-templates-with-multiple-worksheets"></a>Modelli di Excel con più fogli di lavoro

[!include[banner](../includes/banner.md)]

La gestione dei dati in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition supporta modelli basati su Microsoft Excel per le entità di dati. Questi modelli possono contenere uno o più fogli di lavoro. I modelli con più fogli di lavoro vengono spesso utilizzati quando è conveniente gestire i dati in un singolo file e importarli in più entità di dati. Un esempio potrebbe essere il caso di siti e magazzini.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Caricare una volta un file e mapparlo a tutte le entità
Si veda un esempio in cui esiste un file Excel con i fogli di lavoro chiamati **Siti** e **Magazzini**. Per impostare il progetto di importazione di dati, aggiungere la prima entità di dati **Siti**, quindi caricare il file. Sarà possibile selezionare **Siti** come foglio di lavoro da utilizzare per questa entità.

Se si aggiunge la seconda entità **Magazzini** senza chiudere il modulo **Aggiungi file**, la ricerca del foglio di lavoro consente di selezionare il foglio di lavoro **Magazzini** senza dover caricare di nuovo il file. Il solo motivo per caricare un nuovo file sarebbe se i dati di **Magazzini** si trovassero in un altro file.

![Fogli di lavoro multipli](./media/AddFileMultipleWorkSheets.png) 

## <a name="fix-worksheet-to-entity-mapping"></a>Fissare il foglio di lavoro al mapping di entità

Il mapping del foglio di lavoro a un'entità di dati nel processo di importazione può essere fissato dalla griglia. La colonna **Foglio di lavoro** nella griglia mostra i fogli di lavoro del file che è stato mappato. È possibile scegliere un foglio di lavoro diverso dal menu a discesa. Se il foglio di lavoro è già stato mappato a un'entità nel progetto di dati, il sistema chiede di confermare la modifica. Si consiglia di fissare tutti i mapping nella griglia.

![Aggiornare il mapping del foglio di lavoro](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Ripetere il mapping in un nuovo file

Nei casi in cui una nuova versione dello stesso file o un file completamente nuovo viene caricata per le entità esistenti in un progetto di dati, è necessario utilizzare l'esperienza **Aggiungi file** e aggiungere di nuovo le entità come se si stessero aggiungendo per la prima volta. Il sistema confermerà che si desidera sovrascrivere le entità esistenti nel progetto di dati prima di continuare. Le entità che non vengono aggiunte (o sovrascritte) continueranno a mantenere i mapping precedenti del file precedente.

## <a name="upload-a-file-using-run-project"></a>Caricare un file tramite Esegui progetto

È possibile caricare un file di Excel quando si utilizza l'opzione **Esegui progetto** per eseguire un progetto di importazione. Prestare attenzione a caricare solo i file con gli stessi fogli di lavoro dei mapping esistenti nelle entità di dati nel progetto dati. Se non è possibile trovare un foglio di lavoro nel nuovo file caricato, il sistema visualizza un errore e interrompe l'importazione. Se il mapping al foglio di lavoro deve essere modificato per un'entità, i mapping nel progetto di dati devono essere aggiornati nel progetto dati prima di utilizzare il file nell'esperienza **Esegui progetto**.


