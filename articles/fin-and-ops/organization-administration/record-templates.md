---
title: Modelli record
description: Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e89e4a74550597a4e497a1128fe91c07e766d697
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="record-templates"></a>Modelli record

[!include[banner](../includes/banner.md)]


Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.

I modelli di record possono aiutare a creare dei record più rapidamente in Microsoft Dynamics 365 for Finance and Operations. È possibile creare modelli di record solo per alcuni tipi di record presenti in Microsoft Dynamics 365 for Finance and Operations. 

Ad esempio, si supponga di dover inserire le informazioni di noleggio per una società di noleggio auto che ha sede a San Francisco. Dal momento che è probabile che la maggior parte dei clienti sia dell'area di San Francisco, sarebbe utile poter compilare automaticamente i valori dei campi **Stato**, **Paese** e **Città** del modulo di noleggio. 

> [!Note]
> È possibile applicare i modelli solo alle aree di Finance and Operations per le quali si dispone dell'accesso. Tuttavia, tutti i titoli di modello sono visibili a chi crea un nuovo record e anche agli altri utenti, se si creano modelli che saranno disponibili a tutti gli utenti. Assicurarsi di considerare questo aspetto quando si denominano i modelli. Ad esempio, è opportuno evitare di utilizzare nomi che includono parole, ad esempio "provvigione", se è confidenziale che alcuni dipendenti della società abbiano retribuzioni base alle provvigioni. 

Quando sono presenti uno o più modelli a cui si ha accesso per un modulo specifico e si tenta di creare un nuovo record nel modulo, viene visualizzata la pagina **Selezionare un modello per**. Se si seleziona un modello nell'elenco, il nuovo record viene creato e conterrà informazioni predefinite basate sul modello selezionato. Se non si desidera utilizzare i modelli quando si creano nuovi record, selezionare la casella di controllo **Non ripetere più la domanda** nella pagina **Selezionare un modello per**. Per visualizzare di nuovo la finestra di dialogo per la selezione del modello, fare clic con il pulsante destro del mouse su un record qualsiasi, scegliere **Informazioni sui record**, quindi **Mostra selezione modello**.




