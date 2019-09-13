---
title: Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima
description: Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte.
author: ChristianRytt
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 478dd85abebf76dd264e93bcbe3f218a0ff0a5a8
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916808"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte. Ciò viene effettuato facendo uso del giornale di registrazione delle scorte di sicurezza. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata al responsabile pianificazione della produzione, per facilitare il mantenimento della copertura minima.


## <a name="create-a-new-safety-stock-journal-name"></a>Creare un nuovo nome per il giornale di registrazione delle scorte di sicurezza
1. Nel **pannello di navigazione**, andare a **Pianificazione generale > Impostazioni > Nomi giornali di registrazione scorte di sicurezza**.
2. Fare clic su **Nuovo**.
3. Nel campo **Nome** digitare "Materiale".
4. Digitare "Materiale" nel campo **Descrizione**.
5. Chiudere la pagina.

## <a name="create-a-safety-stock-journal"></a>Creare un giornale di registrazione delle scorte di sicurezza
1. Nel **pannello di navigazione**,andare a **Pianificazione generale > Pianificazione generale > Esegui Calcolo scorte di sicurezza**.
2. Fare clic su **Nuovo**.
3. Nel campo **Nome** immettere o selezionare un valore. Selezionare il nome del giornale di registrazione delle scorte di sicurezza creato, ad esempio, Materiale.  
4. Fare clic su **Crea righe**.
5. Immettere una data nel campo **Dal**.  
6. Nel campo **Al** immettere una data.
7. Fare clic su **OK**. Ciò creerà le righe per le dimensioni che hanno operazioni di magazzino.  

## <a name="calculate-proposal"></a>Calcola proposta
1. Fare clic su **Calcola proposta**.
2. Selezionare l'opzione **Utilizza uscita media durante il lead time**.
3. Impostare **Fattore di moltiplicazione** su "10". Il fattore di moltiplicazione è usato per rettificare la proposta. Poiché i dati dimostrativi hanno soltanto alcune transazioni, dovrete impostare il fattore in modo da ottenere una proposta realistica.  
4. Fare clic su **OK**. Scorrere in basso fino a trovare M0002 e M0003. Visualizzare la colonna **Quantità minima calcolata**.   

## <a name="update-minimum-quantity"></a>Aggiornare la quantità minima
1. Nel campo **Nuova quantità minima** immettere un numero. Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata. Se il minimo calcolato è zero, potete immettere il valore futuro desiderato. Ad esempio, potete immettere la quantità minima calcolata in questo campo per M0002 che ha magazzino 12.  
2. Nell'elenco trovare e selezionare il record desiderato. Ad esempio, potete selezionare M0002 che ha magazzino 12.  
3. Nel campo **Nuova quantità minima** immettere un numero. Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata. Se il minimo calcolato è zero, potete immettere il valore futuro desiderato.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Inviare la nuova quantità minima e convalidare il risultato
1. Fare clic su **Registra**.
2. Fare clic su **OK**.
3. Fare clic per seguire il collegamento nel campo **Numero articolo**.
4. Fare clic per seguire il collegamento nel campo **Numero articolo**.
5. Nel **riquadro azioni**, fare clic su Piano.
6. Fare clic su **Copertura articoli**. Notare che la **quantità minima** è stata aggiornata con la nuova quantità minima dal giornale di registrazione delle scorte di sicurezza.  

