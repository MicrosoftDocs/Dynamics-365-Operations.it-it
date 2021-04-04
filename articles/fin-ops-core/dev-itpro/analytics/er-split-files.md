---
title: Dividere file XML generati in base alla dimensione di file e alla quantità di contenuto
description: In questo argomento vengono fornite informazioni su come dividere i file generati in base alla dimensione del file e alla quantità del contenuto.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: d347bd0decf3ab274157d75ec29b0c9dc376e96b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570816"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dividere file XML generati in base alla dimensione di file e alla quantità di contenuto

[!include[banner](../includes/banner.md)]

È possibile progettare formati di report elettronici (ER) per generano documenti in uscita in formato XML. Talvolta, tali documenti possono essere accettati solo se soddisfano criteri specifici, ad esempio una dimensione di file massima o un numero massimo di nodi XML. È possibile progettare formati di ER per generare documenti elettronici che soddisfano i requisiti specificati dai destinatari di tali documenti.

- Per la voce di formato FILE, è possibile definire un limite per la dimensione di file come espressione di ER. Se il limite definito quando viene superato quando viene generato un report di ER, ER completa la creazione del file corrente e quindi passa a creare il file successivo.
- Per qualsiasi formato XML ELEMENT, è possibile definire un limite nel numero di elementi come espressione di ER. Se il numero di nodi XML nel file che viene generato supera il limite definito quando viene eseguito un report di ER, ER completa la creazione del file corrente e quindi passa a creare il file successivo.
- Per qualsiasi elemento di formato XML SEQUENCE, è possibile definire un limite nel numero di elementi figlio come espressione di ER. Se il numero di nodi XML nidificati dell'elemento di formato nel file generato supera il limite definito quando viene eseguito un report di ER, ER completa la creazione del file corrente e quindi passa a creare il file successivo.
- È possibile contrassegnare qualsiasi elemento di formato XML ELEMENT come non interrompibile. In questo modo, è possibile mantenere gli articoli nidificati di nodi XML generati sotto l'elemento di formato in un singolo file generato.

Oltre all'utilizzo degli elementi di formato XML ELEMENT e XML SEQUENCE per aggiungere nodi XML al file generato, è possibile utilizzare l'elemento di formato RAW XML. I nodi che si aggiungono utilizzando l'elemento di formato RAW XML non vengono tuttavia considerati quando il numero di nodi viene calcolato per valutare i limiti nel numero di elementi.

Se sono state configurate destinazioni di file per un elemento di formato FILE che è stato configurato per dividere l'output generato ogni volta che vengono superati limiti specifici, ogni parte dell'output generato viene inviato alla destinazione del file configurato come singolo file. Per denominare in modo univoco i file creati dividendo l'output, è necessario configurare un'espressione di ER per l'elemento di formato FILE. Se si include un'origine dati di ER del tipo NUMBER SEQUENCE, la sequenza numerica verrà incrementata per ogni parti di output diviso.

Per ulteriori informazioni su questa funzionalità, riprodurre la guida attività **ER Dividere i file XML in base alla dimensione di file o alla quantità di contenuto**, che fa parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)** e che può essere scaricata dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Questa guida attività illustra in dettaglio il processo di configurazione di un formato di ER per dividere i file generati in base ai limiti di dimensione di file o alla quantità di contenuto. Per completare la guida attività, è necessario scaricare i file seguenti:

- [Configurazione del modello di ER - XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configurazione del modello di ER - XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>Risorse aggiuntive
[Destinazioni dei report elettronici (ER)](electronic-reporting-destinations.md)

[Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]