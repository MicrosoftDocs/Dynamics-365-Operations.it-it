---
title: Importare la configurazione di bonifico ISO20022
description: In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee7e69611d31d2577ebafdfc059b0936aef0520b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848793"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importare la configurazione di bonifico ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore. Viene usato il formato di bonifico tedesco ISO 20022 come esempio. Questa procedura può essere utilizzata per un altro formato di creazione di report elettronici disponibile. 

Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF ma è possibile utilizzare qualsiasi società di dati dimostrativi per completare l'attività.

Si tratta della prima attività di cinque, tale set illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Nell'elenco di provider di configurazioni disponibili selezionare Microsoft.
3. Fare clic su Imposta attivo.
4. Fare clic su Archivi.
5. Fare clic su Apri.
6. Fare clic su Mostra filtri.
7. Applicare i filtri seguenti: immettere un valore di filtro "Bonifico ISO20022 (DE)" nel campo "Nome configurazione" utilizzando l'operatore di filtro "inizia con".
    * In alternativa, individuare la configurazione nell'elenco, selezionarla e spostarla nell'attività di importazione.  
8. Fare clic su Importa.
    * Se il pulsante di importazione non è disponibile, significa che la configurazione è già stata importata.  
9. Fare clic su Sì.

