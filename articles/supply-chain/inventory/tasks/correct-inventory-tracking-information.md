---
title: Correggere le informazioni di tracciabilità di magazzino
description: In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimenti scorte per correggere le informazioni di tracciabilità inventario.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8a488d4c30923445b3ebc2626a79b8fa45012c7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204196"
---
# <a name="correct-inventory-tracking-information"></a>Correggere le informazioni di tracciabilità di magazzino

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per creare e registrare un giornale di registrazione trasferimenti scorte per correggere le informazioni di tracciabilità inventario. In questo esempio, si aggiornano le informazioni di un articolo controllato da batch modificando un batch registrato in modo non corretto con un altro batch. È possibile eseguire questa procedura nella società di dati dimostrativi USPI oppure utilizzando i propri dati. Se si utilizzano propri dati, è necessario disporre di un articolo che supporta i batch e che non è controllato da ubicazione. È inoltre necessario disporre di un nome del giornale di registrazione magazzino configurato per i trasferimenti scorte. Queste attività verranno in genere svolte da un dipendente del magazzino.


## <a name="create-an-inventory-transfer-journal"></a>Creare un giornale di registrazione trasferimento scorte
1. Passare a Trasferimenti.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
4. Fare clic su OK.

## <a name="create-journal-lines"></a>Creare righe di giornale di registrazione
1. Fare clic su Nuovo.
2. Nel campo Numero di articoli immettere o selezionare un valore.
    * Se si utilizza USPI, selezionare l'articolo M5003.  
3. Nel campo Quantità immettere un numero.
4. Fare clic sulla scheda Dimensioni inventariali.
5. Nel campo Numero batch immettere o selezionare un valore.
6. Nel campo Sito immettere o selezionare un valore.
7. Nel campo Magazzino immettere o selezionare un valore.
8. Nel campo Numero batch immettere o selezionare un valore.

## <a name="post-the-journal"></a>Registra il giornale
1. Fare clic su Registra.
2. Fare clic su OK.

## <a name="check-tracing-information"></a>Controllare le informazioni di traccia
1. Fare clic su Scorte.
2. Fare clic su Traccia.
3. Fare clic su OK.
    * Con queste informazioni di traccia è possibile tracciare a ritroso da quale batch è iniziata la correzione dell'inventario.  È inoltre possibile utilizzare la pagina Tracciabilità articolo per visualizzare queste informazioni.  
4. Chiudere la pagina.

## <a name="check-inventory-transactions"></a>Controllare le transazioni di inventario
1. Fare clic su Scorte.
2. Fare clic su Transazioni.
    * È possibile visualizzare le transazioni create quando è stato registrato il giornale di registrazione.   

