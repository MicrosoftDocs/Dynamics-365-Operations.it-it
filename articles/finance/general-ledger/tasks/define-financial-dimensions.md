---
title: Definire dimensioni finanziarie
description: Questa mostra come aggiungere una dimensione finanziaria supportata da un'entità e una dimensione finanziaria personalizzata.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716945"
---
# <a name="define-financial-dimensions"></a>Definire dimensioni finanziarie

[!include [banner](../../includes/banner.md)]

Questa mostra come aggiungere una dimensione finanziaria supportata da un'entità e una dimensione finanziaria personalizzata. La guida utilizza la società dimostrativa USMF.

## <a name="create-an-entity-backed-financial-dimension"></a>Creare una dimensione finanziaria supportata da un'entità
1. Selezionare **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Dimensioni > Dimensioni finanziarie**.
2. Fare clic su **Nuovo**.
3. Nel campo **Usa valori da**, selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria. 
4. Nel campo **Nome dimensione**, immettere un valore per descrivere la dimensione finanziaria. Il nome può essere diverso da quello dell'entità definita dal sistema ma non può contenere spazi o caratteri speciali.
5. Fare clic su **Attiva**. Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata fino all'attivazione.  
6. Fare clic su **Chiudi** nel messaggio di attivazione.
7. Fare clic su **Attiva**. L'attivazione della dimensione può essere programmata per l'esecuzione in batch a una data e un'ora specifica.  
8. Nel **riquadro azioni**, fare clic su **Valori di dimensione**. Alcuni valori di dimensione sono specifici di società. È possibile verificare se sono specifici di una società dalla presenza del nome della società nell'elenco di valori di dimensione.  

## <a name="create-a-custom-financial-dimension"></a>Creare una dimensione finanziaria personalizzata
1. Fare clic su **Nuovo**.
2. Nel campo **Usa valori da**, selezionare **Dimensione personalizzata**.
3. Nel campo **Nome dimensione**, immettere un valore per descrivere la dimensione finanziaria.
    - Il nome non può contenere spazi o caratteri speciali.  
    - È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione.   
    - È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino. È inoltre possibile immettere i segni di numero (#) e commerciali (&) come segnaposto per le lettere e i numeri che cambieranno ogni volta che un valore di dimensione viene creato. Utilizzare un simbolo di numero (#) come segnaposto per un numero e la e commerciale (&) come segnaposto per una lettera.  Esempio: per limitare il valore della dimensione alle lettere CC e a tre numeri, immettere CC-### come maschera formato.  
4. Fare clic su **Attiva**. Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate. È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata fino all'attivazione.     
5. Fare clic su **Attiva**. L'attivazione della dimensione può essere programmata per l'esecuzione in batch a una data e un'ora specifica.      
6. Nel **riquadro azioni**, fare clic su **Valori di dimensione**.
7. Fare clic su **Nuovo**.
8. Nel campo **Valore di dimensione**, immettere un nome per descrivere il valore della dimensione finanziaria.
9. Nel campo **Descrizione**, immettere una descrizione che descrive il valore di dimensione finanziaria.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
