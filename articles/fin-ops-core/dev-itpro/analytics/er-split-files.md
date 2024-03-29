---
title: Dividere i file XML generati in base alle dimensioni del file e alla quantità del contenuto
description: In questo articolo vengono fornite informazioni su come dividere i file generati in base alla dimensione del file e alla quantità del contenuto.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 5347d4e85198893dd94f14508176db93ccd47c22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280097"
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

- [Configurazione del modello di ER - XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [Configurazione del modello di ER - XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>Risorse aggiuntive
[Destinazioni dei report elettronici (ER)](electronic-reporting-destinations.md)

[Designer formula nella creazione di report elettronici (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
