---
title: Importazione MT940 riconciliazione estratti conto avanzata - Aggiornamento entità di dati compositi
description: Un numero progressivo deve essere aggiunto all'entità importazione rendiconto bancario per supportare il formato MT940.
author: panolte
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c891a5139ff7de85e6762513f57236e24f1644529d7825c9ce5e1dfda50fbad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739385"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Importazione MT940 riconciliazione estratti conto avanzata - Aggiornamento entità di dati compositi

[!include [banner](../includes/banner.md)]

Un numero progressivo deve essere aggiunto all'entità importazione rendiconto bancario per supportare il formato MT940. 

Effettuare le seguenti operazioni per aggiungere l'entità importazione rendiconto bancario per supportare il formato MT940.

1.  Compilare e sincronizzare quanto segue:
    -   Entità composta\\BankStatementImportEntity
    -   Entità\\BankStatementBalanceEntity
    -   Entità\\BankStatementDocumentEntity
    -   Entità\\BankStatementEntity
    -   Entità\\BankStatementLineEntity
    -   Tabelle\\BankStatementStaging

2.  Gestione dati\\Progetti dati.
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
            6.  Verificare che S **equenceNumber** sia stato mappato.
                -   Fare clic su **Visualizza mapping** sull'entità rendiconto.
                -   Verificare che **SequenceNumber** sia mappato da Origine a Gestione temporanea.

3.  Importare il nuovo rendiconto.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]