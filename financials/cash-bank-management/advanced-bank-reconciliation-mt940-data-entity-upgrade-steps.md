---
title: "Importazione avanzata di riconciliazione estratti conto MT940 - Aggiornamento composito di entità di dati"
description: "Un numero progressivo deve essere aggiunto all&quot;entità importazione rendiconto bancario per supportare il formato MT940."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: 3a4868045a12f7210a4d3924b4a335a52206341a
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importazione avanzata di riconciliazione estratti conto MT940 - Aggiornamento composito di entità di dati

Un numero progressivo deve essere aggiunto all'entità importazione rendiconto bancario per supportare il formato MT940. 

Effettuare le seguenti operazioni per aggiungere l'entità importazione rendiconto bancario per supportare il formato MT940.

1.  Compilare e sincronizzare quanto segue:
    -   Entità Panoramica dati compositi BankStatementImportEntity\\
    -   Entità BankStatementBalanceEntity\\
    -   Entità BankStatementDocumentEntity\\
    -   Entità BankStatementEntity\\
    -   Entità BankStatementLineEntity\\
    -   Pertanto BankStatementStaging\\

2.  Progetti di dati\\per la gestione dei dati.
    1.  Caricare i progetti di importazione MT940
        1.  Modificare XSLT.
            -   Fare clic su **Visualizza mapping**.
            -   Fare clic su **Visualizza mapping** sul documento di rendiconto bancario.
            -   Fare clic su **Trasformazioni**
            -   Eliminare il file BankReconiliation-to-Composite.xslt.
            -   Aggiungere la nuova versione di BankReconiliation-to-Composite.xsl.

        2.  Esporre **Numero progressivo** sul layout **Dati di origine**.
            1.  Formato dati di origine = Elemento XML.
            2.  Nome entità = Rendiconti bancari.
            3.  Caricare il file di dati = nuova versione SampleBankCompositeEntity.xml.
            4.  Fare clic su **Sì** per sovrascrivere il file esistente.
            5.  Fare clic su **Sì** per generare un nuovo mapping.
            6.  Verificare che S**equenceNumber** sia stato mappato.
                -   Fare clic su **Visualizza mapping** sull'entità rendiconto.
                -   Verificare che **SequenceNumber** sia mappato da Origine a Gestione temporanea.

3.  Importare il nuovo rendiconto.



