---
title: "Impostare un programma di continuità per un servizio clienti"
description: "In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: e32961f2a0e0e41715d98075cbc5777d256eb187
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Impostare un programma di continuità per un servizio clienti

In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti.

In un programma di continuità, noto anche come programma ordine ricorrente, i clienti ricevono le spedizioni prodotto normali in base a una programmazione predefinita. Ogni spedizione può contenere un prodotto diverso, come nel caso di un club libro del mese oppure lo stesso prodotto può essere inviato più volte. Per impostare un gruppo di continuità, è necessario completare le seguenti attività.

1.  Impostare i parametri di continuità nella pagina **Parametri servizio clienti**.
2.  Creare un programma di continuità che specifica dettagli quali lo scadenzario pagamenti, i tempi di spedizione e se la fatturazione è con costi preliminari fatturabili. È inoltre necessario aggiungere un elenco di prodotti inclusi nel programma di continuità. A ciascun prodotto riceve un numero ID evento allocato in sequenza, che inizia con 1. ID dell'evento determina l'ordine in cui i prodotti sono inviati in.
    -   Se i clienti ricevono un prodotto diverso in ogni spedizione, i prodotti vengono introdotti in ordine sequenziale in base ai relativi ID evento e a partire dall'evento corrente.
    -   Se i clienti ricevono lo stesso prodotto in ogni spedizione, l'elenco conterrà solo un prodotto con un ID evento. Lo stesso evento si verifica più volte. È possibile specificare quante volte ciascun evento viene ripetuto.

3.  Creare un prodotto padre che rappresenta il programma continuità aver creato l'attività. 2. Se si aggiunge il prodotto in un ordine cliente, ** continuità ** la pagina verrà aperto. È quindi possibile utilizzare tale pagina per creare l'ordine di continuità effettivo. Il prodotto padre non specifica i singoli prodotti che il cliente riceve in ogni spedizione.

Dopo aver impostato un programma di continuità come descritto in precedenza, è possibile creare un ordine di continuità per un cliente. Potrebbe inoltre essere necessario eseguire le seguenti attività di manutenzione aggiuntive.

-   **Aggiornare il periodo evento corrente di continuità**: impostare un processo batch che indica al sistema il periodo evento corrente.
-   **Crea ordini di continuità figlio**: creare ordini figlio dall'ordine di continuità padre.
-   **Elabora pagamenti di continuità**: elaborare la fatturazione e le notifiche per pagamenti associati agli ordini cliente di continuità.
-   **Estendi righe continuità** (se necessario): estendere il numero di volte che un evento di continuità può essere ripetuto. La ripetizione delle spedizioni può quindi estendersi oltre il limite impostato nel campo **Soglia ripetizione continuità** dei parametri del servizio clienti.
-   **Eseguire un aggiornamento di continuità** (se necessario): sincronizzare le modifiche tra il programma di continuità e gli ordini cliente padre di continuità.
-   **Chiudi righe e ordini di continuità**: chiudere gli ordini di continuità.


