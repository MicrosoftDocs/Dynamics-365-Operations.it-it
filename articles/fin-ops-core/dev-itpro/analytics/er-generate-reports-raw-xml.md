---
title: Generare report aggiungendo contenuto come XML non elaborato
description: È possibile progettare formati di report elettronici (ER) che generano documenti in uscita in formato XML.
author: kfend
ms.date: 05/25/2018
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
ms.openlocfilehash: 87b70d5893d71e5022205a2f39f8263edf6d5280
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277544"
---
# <a name="generate-reports-by-adding-content-as-raw-xml"></a>Generare report aggiungendo il contenuto non elaborato come XML

[!include[banner](../includes/banner.md)]

È possibile utilizzare il nuovo elemento di formato **RAW XML** per progettare formati di report elettronici (ER) che generano i documenti in uscita in formato XML. In alcuni casi, è preferibile aggiungere dati XML non elaborati a questi report per uno dei seguenti motivi:

- È più pratico utilizzare il codice XML non elaborato per la progettazione originale e la gestione continua di un report, poiché la struttura XML può essere generata automaticamente eseguendo un'espressione runtime. Di conseguenza, non è necessario determinare più associazioni per più elementi di formato in fase di progettazione. È possibile quando le origini dati in uso contengono informazioni che possono essere utilizzate per creare elementi XML quando viene generato il report.
- Non esiste alcuna altra modalità per compilare il report con contenuto XML precedentemente ricevuto e archiviato nel sistema. Ad esempio, la risposta XML che viene generata potrebbe dover includere il contenuto di una richiesta XML che è stata inviata in precedenza.
- Nessun'altra modalità può essere utilizzata per inserire caratteri nel documento generato in base ai codici numerici. Per alcune lingue e alcuni caratteri, i codici di questo tipo non sono disponibili. Alcuni esempi sono rappresentati dalla lettera greca rho (ρ) e dai codici di entità HTML quali \&eacute; per una *e* che ha l'accento acuto (é).

> [!NOTE]
> Tenere presente che il framework non verifica se il contenuto XML che viene inserito nel documento generato utilizzando l'elemento di formato **RAW XML** è corretto.

Per ulteriori informazioni su questa funzionalità, riprodurre le guide attività **ER Utilizzare dati XML non elaborati per generare report XML (Parte 1: Progettare un modello di dati)** e **ER Utilizzare dati XML non elaborati per generare report XML (Parte 2: Progettare un modello di dati)** che fanno parte dell processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)** e che possono essere scaricate dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Queste guide attività illustrano in dettaglio il processo di configurazione di un formato di ER per inserire dati XML non elaborati in file generati.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
