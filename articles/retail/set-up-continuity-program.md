---
title: Impostare programmi di continuità per i servizi clienti
description: In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 369856f33c6da49b6c6b3f51f42c99a8f07fe777
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "320974"
---
# <a name="set-up-continuity-programs-for-call-centers"></a>Impostare programmi di continuità per i servizi clienti

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come impostare un programma di continuità per il servizio clienti.

In un programma di continuità, noto anche come programma ordine ricorrente, i clienti ricevono le spedizioni prodotto normali in base a una programmazione predefinita. Ogni spedizione può contenere un prodotto diverso, come nel caso di un club libro del mese oppure lo stesso prodotto può essere inviato più volte. Per impostare un gruppo di continuità, è necessario completare le seguenti attività.

1. Impostare i parametri di continuità nella pagina **Parametri servizio clienti**.
2. Creare un programma di continuità che specifica dettagli quali lo scadenzario pagamenti, i tempi di spedizione e se la fatturazione è con costi preliminari fatturabili. È inoltre necessario aggiungere un elenco di prodotti inclusi nel programma di continuità. Ciascun prodotto riceve un numero ID evento allocato in sequenza, a partire da 1. Gli ID evento determinano l'ordine in cui i prodotti sono inviati.

    - Se i clienti ricevono un prodotto diverso in ogni spedizione, i prodotti vengono introdotti in ordine sequenziale in base ai relativi ID evento e a partire dall'evento corrente.
    - Se i clienti ricevono lo stesso prodotto in ogni spedizione, l'elenco conterrà solo un prodotto con un ID evento. Lo stesso evento si verifica più volte. È possibile specificare quante volte ciascun evento viene ripetuto.

3. Creare un prodotto padre che rappresenta il programma continuità creato nell'attività 2. Se si aggiunge il prodotto in un ordine cliente, la pagina **Continuità** verrà aperta. È quindi possibile utilizzare tale pagina per creare l'ordine di continuità effettivo. Il prodotto padre non specifica i singoli prodotti che il cliente riceve in ogni spedizione.

Dopo aver impostato un programma di continuità come descritto in precedenza, è possibile creare un ordine di continuità per un cliente. Potrebbe inoltre essere necessario eseguire le seguenti attività di manutenzione aggiuntive.

- **Aggiornare il periodo evento corrente di continuità**: impostare un processo batch che indica al sistema il periodo evento corrente.
- **Crea ordini di continuità figlio**: creare ordini figlio dall'ordine di continuità padre.
- **Elabora pagamenti di continuità**: elaborare la fatturazione e le notifiche per pagamenti associati agli ordini cliente di continuità.
- **Estendi righe continuità** (se necessario): estendere il numero di volte che un evento di continuità può essere ripetuto. La ripetizione delle spedizioni può quindi estendersi oltre il limite impostato nel campo **Soglia ripetizione continuità** dei parametri del servizio clienti.
- **Eseguire un aggiornamento di continuità** (se necessario): sincronizzare le modifiche tra il programma di continuità e gli ordini cliente padre di continuità.
- **Chiudi righe e ordini di continuità**: chiudere gli ordini di continuità.
