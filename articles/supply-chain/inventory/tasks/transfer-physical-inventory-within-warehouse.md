---
title: Trasferire l'inventario fisico all'interno del magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimento scorte in modo da registrare lo spostamento di un articolo da un'ubicazione di un magazzino a un'altra.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7344bfa3be0d7345d3ac68202c7bc26bcac8ebb9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845259"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Trasferire l'inventario fisico all'interno del magazzino

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimento scorte in modo da registrare lo spostamento di un articolo da un'ubicazione di un magazzino a un'altra. È necessario disporre di un nome del giornale di registrazione magazzino configurato per i trasferimenti scorte prima di iniziare. È possibile eseguire questa procedura nella società di dati dimostrativi USMF utilizzando i valori di esempio visualizzati o è possibile utilizzare propri dati se prodotti e ubicazioni sono stati configurati. Queste attività verranno in genere svolte da un dipendente del magazzino.


## <a name="create-an-inventory-transfer-journal"></a>Creare un giornale di registrazione trasferimento scorte
1. Passare a Trasferimenti.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
4. Fare clic su OK.
    * È presente l'opzione per specificare le dimensioni 'Da' e 'A' per ogni riga del giornale di registrazione che sono per questo tipo di giornale di registrazione. È possibile trasferire gli articoli nelle ubicazioni utilizzando regole diverse. In questo esempio verrà trasferito un articolo all'interno dello stesso magazzino, da un'ubicazione controllata da targa a un'ubicazione non controllata da targa.   

## <a name="create-journal-lines"></a>Creare righe di giornale di registrazione
1. Fare clic su Nuovo.
2. Nel campo Numero di articoli immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare 'A0001'.  
3. Nel campo Dal sito immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare '2'.  
4. Nel campo Al sito immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare '2'.  
5. Nel campo Magazzino origine immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare '24'.  
6. Nel campo Magazzino destinazione immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare '24'.  
7. Nel campo Ubicazione origine immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare 'FL-001'.  
8. Nel campo Ubicazione destinazione immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare 'BULK-001'.  
9. Nel campo Quantità immettere un numero.
10. Fare clic sulla scheda Dimensioni inventariali.
11. Nel campo Targa immettere o selezionare un valore.
    * Se si utilizza USMF, è possibile selezionare '24'.  
12. Fare clic su Salva.

## <a name="post-the-inventory-transfer-journal"></a>Registrare il giornale di registrazione trasferimento scorte
1. Fare clic su Registra.
2. Fare clic su OK.

## <a name="view-inventory-transactions"></a>Visualizza operazioni di magazzino
1. Fare clic su Scorte.
2. Fare clic su Transazioni.
    * È possibile visualizzare le transazioni create quando è stato registrato il giornale di registrazione.  

