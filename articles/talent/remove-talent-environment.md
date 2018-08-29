---
title: Rimuovere ambienti Talent
description: Questo argomento descrive il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 5080f1ec182b8cbdf281967185a1afeb9887f682
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="remove-talent-environments"></a>Rimuovere ambienti Talent

Questo argomento descrive il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Rimozione di un ambiente test drive

Il provisioning dei test drive di Talent viene effettuato con criteri di scadenza di 60 giorni. I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti. 

1. Accedere all'[interfaccia di amministrazione di PowerApps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain
4. Selezionare **Elimina** e confermare la decisione. 

L'ambiente test drive esistente verrà rimosso. Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive. 

## <a name="removing-a-production-environment"></a>Rimozione di un ambiente di produzione

In questo argomento si presuppone che Talent sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA). 

Poiché un unico ambiente Talent è "contenuto" in unico ambiente PowerApps, è necessario considerare due opzioni. La prima opzione implica prima di tutto la rimozione dell'intero ambiente PowerApps. La seconda opzione implica la rimozione solo di Talent. La prima opzione è preferibile se si è creato un ambiente PowerApps appositamente per il provisioning di Talent e l'implementazione è appena stata iniziata, oppure se non si hanno integrazioni stabilite. La seconda opzione è appropriata quando si è stabilito un ambiente PowerApps con dati complessi utilizzati in PowerApps e in flussi.

> [!Important]
> Prima di rimuovere l'ambiente PowerApps, assicurarsi che non sia utilizzato per integrazioni di dati complessi al di fuori dell'ambito di Talent. Inoltre si noti che, gli ambienti PowerApps predefiniti non possono essere rimossi. 

Per rimuovere l'intero ambiente PowerApps, inclusi Talent nonché le app e i flussi associati:

1. Accedere all'[interfaccia di amministrazione di PowerApps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente da rimuovere.
4. Selezionare **Elimina** e confermare la decisione. 
5. Attendere fino al completamento dell'eliminazione.
6. Accedere a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) utilizzando l'account usato per iscriversi a Talent. 
7. Selezionare il progetto Talent contenente l'ambiente. 
8. Nel progetto LCS selezionare il riquadro **Gestione app Talent**. 
9. Selezionare l'istanza da rimuovere. 
10. Selezionare **Rimuovere istanza** e confermare la decisione.  

Per rimuovere un ambiente Talent da un ambiente PowerApps esistente, completare le operazioni seguenti. Si noti che la necessità di coinvolgere il supporto e contattare il team Talent DevOps è temporanea fino a che questa funzionalità è attivata direttamente in LCS.

1. Contattare il Supporto per avviare una richiesta di rimozione.
2. Il team di supporto avvierà una richiesta di rimozione con il team Talent DevOps. 
3. Continuare dopo aver ricevuto conferma che l'ambiente è stato rimosso.
4.  Accedere a LCS utilizzando l'account usato per iscriversi a Talent. 
5. Selezionare il progetto Talent contenente l'ambiente. 
6. Nel progetto LCS selezionare il riquadro **Gestione app Talent**. 
7. Selezionare l'istanza che si desidera rimuovere, che deve essere contrassegnata con lo stato di distribuzione **Non riuscita**.
8. Selezionare **Rimuovere istanza** e confermare la decisione. 


