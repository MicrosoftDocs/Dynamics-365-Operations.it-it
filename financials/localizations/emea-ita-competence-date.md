---
title: Data di competenza dalle transazioni
description: "In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264534
ms.assetid: d151f65a-3257-4296-8b00-d93c1dfdcf0e
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 87599514ed92eb1507ece44c00b2ca075c391132
ms.lasthandoff: 03/31/2017


---

# <a name="competence-date-for-transactions"></a>Data di competenza dalle transazioni

In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia.

In Italia, le società devono utilizzare una data di registrazione per registrare le transazioni. Data di registrazione corrisponde alla data in cui la società riconosce la transazione. Le transazioni di chiusura e rettifica è possibile effettuare diversi mesi dopo l'ultimo giorno dell'anno fiscale. (In genere, queste transazioni vengono effettuate alla data in cui lo stato patrimoniale viene approvato dal consiglio di amministrazione.) Queste transazioni devono essere dichiarate nel giornale di registrazione fiscale italiano alla data in cui vengono registrati, ma devono disporre di un riferimento alla data delle competenze. Di conseguenza, due date sono richieste:

-   Data competenze, che rappresenta la data in cui la transazione sull'importo del saldo
-   Data di registrazione, ovvero la data in cui l'utente registra la transazione

** Esempio: ** L'anno fiscale della società è dal 1° gennaio al 31 dicembre. Stato patrimoniale viene approvato il 15 aprile. Di conseguenza, le transazioni di chiusura e rettifica vengono dichiarate nel giornale di registrazione fiscale italiano ad aprile, ma influiscono sul saldo il 31 dicembre.

## <a name="enable-the-competence-date"></a>Attivare la data di competenza
Per attivare questa funzionalità per le transazioni, in ** parametri di contabilità generale ** pagine, ** contabilità generale ** nella scheda, impostare ** riferimento alla data transazione alla data di competenza ** l'opzione ** Sì **. Dopo la data di competenza è attivata, è possibile specificare le competenze e le date di transazione per ogni giornale di registrazione utilizzato per registrare la rettifica e la chiusura e/o transazioni di apertura per l'anno fiscale:

-   Giornale di registrazione generale
-   Giornale di registrazione cespiti
-   Riconciliazione estratti conto
-   Bilancio di chiusura
-   Transazione di apertura
-   Progetto - Registra costi
-   Progetto - (si il fatturato
-   Progetto - posta di stima
-   Progetto - storno di stima



