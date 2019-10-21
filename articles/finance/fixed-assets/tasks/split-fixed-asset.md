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
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178440"
---
# <a name="split-a-fixed-asset"></a>Dividere un cespite

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritto come suddividere una percentuale di un libro cespiti in un nuovo libro cespiti. Utilizza il ruolo Ragioniere e i dati dimostrativi USMF.


## <a name="create-a-new-fixed-asset"></a>Crea un nuovo cespite
1. Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.
2. Selezionare **Nuovo**.
3. Nel campo **Gruppo cespite** immettere o selezionare un valore. Si noti il numero cespite da utilizzare successivamente nel processo di divisione.  
4. Digitare un valore nel campo **Nome**.
5. Chiudere il modulo.

## <a name="split-a-fixed-asset"></a>Dividere un cespite
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
1. Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.
2. Nell'elenco, selezionare il giornale di registrazione creato con il processo di divisione.
3. Selezionare **Righe**.

    - Verificare le righe del giornale di registrazione create.  
    - Una transazione di rettifica acquisizione viene creata per il cespite originario per diminuire il valore della percentuale specificata durante il processo di divisione.  
    - Una transazione di acquisizione viene creata per il nuovo cespite per lo stesso importo.  

4. Selezionare **Registra**.

