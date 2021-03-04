---
title: Aggiornare l'entità composta giornale di registrazione bancario
description: I passaggi seguenti sono necessari per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.
author: ShylaThompson
manager: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec196600a54a2aed4565cf422dc386d6646ff524
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444648"
---
# <a name="update-the-bank-journal-composite-entity"></a>Aggiornare l'entità composta giornale di registrazione bancario

[!include [banner](../includes/banner.md)]

I passaggi seguenti sono necessari per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.

Effettuare le seguenti operazioni per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.

1.  Compilare e sincronizzare le entità composte, entità e tabelle di gestione temporanea del giornale di registrazione bancario seguenti:
    -   Entità composta\\BankJournalEntity
    -   Entità\\BankJournalHeaderEntity
    -   Entità\\BankJournalLineEntity
    -   Tabella\\BankJournalHeaderStaging
    -   Tabella\\BankJournalLineStaging

2.  Gestione dati\\Progetti dati
    -   Esporre il tipo **Transazione bancaria** sul layout **Dati di origine**.
        -   Formato dati di origine = Elemento XML
        -   Nome entità = Giornale di registrazione bancario
        -   Caricare il file di dati = nuova versione SampleBankJournalCompositeEntity.xml
        -   Fare clic su **Sì** per sovrascrivere il file esistente.
        -   Fare clic su **Sì** per generare un mapping completamente nuovo.
        -   Verificare che Tipo di transazione bancaria sia mappato.
            -   Fare clic su **Visualizza mapping** sull'entità Riga.
            -   Verificare che Tipo di transazione bancaria sia mappato da Origine a Gestione temporanea.

3.  Importare il nuovo rendiconto.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]