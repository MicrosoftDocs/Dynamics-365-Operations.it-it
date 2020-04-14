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
ms.openlocfilehash: 01f44c49b6623cbcc2f08cfd6e4978c9a1676b83
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140043"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importare la configurazione di bonifico ISO20022

[!include [banner](../../includes/banner.md)]

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

