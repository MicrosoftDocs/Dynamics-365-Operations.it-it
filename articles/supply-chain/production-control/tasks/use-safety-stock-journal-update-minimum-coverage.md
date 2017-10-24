--- 
title: Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima
description: Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte.
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d278b20724006ec3b3aa557738e8b130ca2bba15
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# Utilizzare il giornale di registrazione delle scorte di sicurezza per aggiornare la copertura minima

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come calcolare le proposte di copertura minima basate sulle transazioni storiche e poi aggiornare la copertura articoli con le proposte. Ciò viene effettuato facendo uso del giornale di registrazione delle scorte di sicurezza. La società di dati dimostrativi utilizzata per creare questa attività è USMF. Questa attività è destinata al responsabile pianificazione della produzione, per facilitare il mantenimento della copertura minima.


## Creare un nuovo nome per il giornale di registrazione delle scorte di sicurezza
1. Andare a Nomi giornali di registrazione scorte di sicurezza.
2. Fare clic su Nuovo.
3. Nel campo Nome digitare 'Materiale'.
4. Digitare 'Materiale' nel campo Descrizione.
5. Chiudere la pagina.

## Creare un giornale di registrazione delle scorte di sicurezza
1. Andare a Calcolo scorte di sicurezza.
2. Fare clic su Nuovo.
3. Nel campo Nome immettere o selezionare un valore.
    * Selezionare il nome del giornale di registrazione delle scorte di sicurezza creato, ad esempio, Materiale.  
4. Fare clic su Crea righe.
5. Immettere una data nel campo Dal.
    * Impostare la data su '02-01-2015'.  
6. Nel campo Data finale immettere una data.
    * Impostare la data su '30-12-2015'.  
7. Fare clic su OK.
    * Ciò creerà le righe per le dimensioni che hanno operazioni di magazzino.  

## Calcola proposta
1. Fare clic su Calcola proposta.
2. Selezionare l'opzione Utilizza uscita media durante il lead time.
3. Impostare Fattore di moltiplicazione su '10'.
    * Il fattore di moltiplicazione è usato per rettificare la proposta. Poiché i dati dimostrativi hanno soltanto alcune transazioni, dovrete impostare il fattore in modo da ottenere una proposta realistica.  
4. Fare clic su OK.
    * Scorrere in basso fino a trovare M0002 e M0003. Visualizzare la colonna Quantità minima calcolata.   

## Aggiornare la quantità minima
1. Nel campo Nuova quantità minima immettere un numero.
    * Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata. Se il minimo calcolato è zero, potete immettere il valore futuro desiderato. Ad esempio, potete immettere la quantità minima calcolata in questo campo per M0002 che ha magazzino 12.  
2. Nell'elenco trovare e selezionare il record desiderato.
    * Ad esempio, potete selezionare M0002 che ha magazzino 12.  
3. Nel campo Nuova quantità minima immettere un numero.
    * Aggiornare la Nuova quantità minima in modo che corrisponda al valore della Quantità minima calcolata. Se il minimo calcolato è zero, potete immettere il valore futuro desiderato.  

## Inviare la nuova quantità minima e convalidare il risultato
1. Fare clic su Registra.
2. Fare clic su OK.
3. Fare clic per seguire il collegamento nel campo Numero articolo.
4. Fare clic per seguire il collegamento nel campo Numero articolo.
5. Nel riquadro azioni fare clic su Piano.
6. Fare clic su Copertura articoli.
    * Notare che la quantità minima è stata aggiornata con la nuova quantità minima dal giornale di registrazione delle scorte di sicurezza.  


