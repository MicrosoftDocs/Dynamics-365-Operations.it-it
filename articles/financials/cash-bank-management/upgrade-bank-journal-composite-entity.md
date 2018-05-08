---
title: "Aggiornare l'entità composta giornale di registrazione bancario"
description: I passaggi seguenti sono necessari per aggiungere il campo BankTransactionType aggiuntivo a BankJournalEntity composta.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a8b11df3b21f8d97986d934ff3c65931aa7ee0c6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

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
    -   Esporre il tipo **Transazione bancaria**sul layout **Dati di origine**.
        -   Formato dati di origine = Elemento XML
        -   Nome entità = Giornale di registrazione bancario
        -   Caricare il file di dati = nuova versione SampleBankJournalCompositeEntity.xml
        -   Fare clic su **Sì** per sovrascrivere il file esistente.
        -   Fare clic su **Sì** per generare un mapping completamente nuovo.
        -   Verificare che Tipo di transazione bancaria sia mappato.
            -   Fare clic su **Visualizza mapping** sull'entità Riga.
            -   Verificare che Tipo di transazione bancaria sia mappato da Origine a Gestione temporanea.

3.  Importare il nuovo rendiconto.





