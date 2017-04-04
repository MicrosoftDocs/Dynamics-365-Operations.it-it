---
title: Creare modelli di record
description: Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.
author: pvillads
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 209e4fb346b8c5a02390996cb1fc8fdbd41ba241
ms.lasthandoff: 03/31/2017


---

# <a name="create-record-templates"></a>Creare modelli di record

Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.

I modelli di record consentono di creare più rapidamente i record in Microsoft Dynamics 365 per le operazioni. È possibile creare modelli di record solo per alcuni tipi di record in Microsoft Dynamics 365 per le operazioni. Ad esempio, il **** immagina che si sta immettendo le informazioni per un locative business di l noleggio auto che si trova a San Francisco. Dal momento che è probabile che la maggior parte dei clienti sia dell'area di San Francisco, sarebbe utile poter compilare automaticamente i valori dei campi **Stato**, **Paese** e **Città** del modulo di noleggio. ** Nota: ** È possibile applicare modelli solo per le aree di Dynamics 365 per le operazioni che è possibile accedere. Tuttavia, tutti i titoli di modello sono visibili a chi crea un nuovo record e anche agli altri utenti, se si creano modelli che saranno disponibili a tutti gli utenti. Assicurarsi di considerare questo aspetto quando si denominano i modelli. Ad esempio, è opportuno evitare di utilizzare nomi che includono parole, ad esempio "provvigione", se è confidenziale che alcuni dipendenti della società abbiano retribuzioni base alle provvigioni. Quando sono presenti uno o più modelli a cui si ha accesso per un modulo specifico e si tenta di creare un nuovo record nel modulo, viene visualizzata la pagina **Selezionare un modello per**. Se si seleziona un modello nell'elenco, il nuovo record viene creato e conterrà informazioni predefinite basate sul modello selezionato. Se non si desidera utilizzare modelli quando si creano nuovi record, selezionare ** non ancora ** chiedere la casella di controllo ** selezionare un modello per ** nella pagina. Per visualizzare di nuovo la finestra di dialogo per la selezione del modello, fare clic con il pulsante destro del mouse su un record, fare clic su ** informazioni record ** quindi su ** visualizzare la selezione del modello **.


