---
title: Dividere un cespite
description: In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000295"
---
# <a name="split-a-fixed-asset"></a>Dividere un cespite

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti. Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.

## <a name="create-a-new-fixed-asset"></a>Crea un nuovo cespite

1. Nel pannello di navigazione, passare a **Moduli \> Cespiti \> Cespiti \> Cespiti**.
2. Selezionare **Nuovo**.
3. Nel campo **Gruppo cespite** immettere o selezionare un valore. Si noti il numero cespite da utilizzare successivamente nel processo di divisione.
4. Nel campo **Nome** immettere un valore.
5. Chiudere il modulo.

## <a name="split-a-fixed-asset"></a>Dividere un cespite

Prima che un cespite completamente ammortizzato venga suddiviso, lo stato del libro cespiti deve essere modificato manualmente da **Chiuso** in **Aperto**. Questo passaggio è necessario perché lo stato del libro deve essere **Aperto** per registrare le transazioni per l'attività (ad esempio, per una vendita di dismissione). Dopo che lo stato del libro cespiti è cambiato, seguire questi passaggi per suddividere il cespite.

1. Nell'elenco, individuare e selezionare il collegamento del cespite da dividere.
2. Selezionare **Libri**. Selezionare il libro per la divisione in base al nuovo cespite.
3. Selezionare **Funzioni**.
4. Selezionare **Dividi cespite**.
5. Nel campo **A cespite** immettere o selezionare un valore.
6. Nel campo **Al libro** selezionare il pulsante a discesa per aprire la ricerca.
7. Nel campo **Data della transazione** immettere una data.
8. Nel campo **Percentuale** immettere un numero.
9. Nel campo **Nome giornale di registrazione** immettere o selezionare un valore.
10. Selezionare **OK**.

## <a name="post-the-journal-transaction"></a>Registrare la transazione del giornale di registrazione

1. Nel pannello di navigazione, andare a **Moduli \> Cespiti \> Inserimenti nel giornale di registrazione \> Giornale di registrazione cespiti**.
2. Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.
3. Selezionare **Righe**.

    - Verificare le righe del giornale di registrazione create.
    - Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.
    - Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.

4. Selezionare **Registra**.
