---
title: Rimuovere un'istanza
description: Questo argomento descrive il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba5d69ca33ac84743b178ded80b482eee6edab1e
ms.sourcegitcommit: 6f6ec4f4ff595bf81f0b8b83f66442d5456efa87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487732"
---
# <a name="remove-an-instance"></a>Rimuovere un'istanza

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento spiega il processo di rimozione di un ambiente di prova o di produzione per Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Rimuovere un ambiente test drive

Il provisioning dei test drive di Human Resources viene effettuato con criteri di scadenza di 60 giorni. I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti. 

1. Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain
4. Selezionare **Elimina** e confermare la decisione. 

L'ambiente test drive esistente verrà rimosso. Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive. 

## <a name="remove-a-production-environment"></a>Rimuovere un ambiente di produzione

Questo argomento presuppone che tu abbia acquistato Human Resources attraverso un Cloud Solution Provider (CSP) o un accordo di architettura aziendale (EA). 

Poiché un unico ambiente Human Resources è contenuto in unico ambiente Power Apps, è necessario considerare due opzioni. La prima opzione implica prima di tutto la rimozione dell'intero ambiente Power Apps. La seconda opzione implica la rimozione solo di Human Resources. La prima opzione è preferibile se si è creato un ambiente Power Apps appositamente per il provisioning di Human Resources e l'implementazione è appena stata iniziata, oppure se non si hanno integrazioni stabilite. La seconda opzione è appropriata quando si è stabilito un ambiente Power Apps con dati complessi utilizzati in Power Apps e Power Automate..

> [!Important]
> Prima di rimuovere l'ambiente Power Apps, assicurarsi che non sia utilizzato per integrazioni di dati complessi al di fuori dell'ambito di Human Resources. Inoltre si noti che, gli ambienti Power Apps predefiniti non possono essere rimossi. 

Per rimuovere l'intero ambiente Power Apps, inclusi Human Resources nonché le app e i flussi associati:

1. Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente da rimuovere.
4. Selezionare **Elimina** e confermare la decisione. 
5. Attendere fino al completamento dell'eliminazione.
6. Accedere a [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) utilizzando l'account usato per iscriversi a Human Resources. 
7. Selezionare il progetto Human Resources contenente l'ambiente. 
8. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**. 
9. Selezionare l'istanza da rimuovere. 
10. Selezionare **Rimuovere istanza** e confermare la decisione.  

Per rimuovere un ambiente Human Resources da un ambiente Power Apps esistente, completare le operazioni seguenti. Si noti che la necessità di coinvolgere il supporto e contattare il team Human Resources DevOps è temporanea fino a che questa funzionalità è attivata direttamente in LCS.

1. Contattare il Supporto per avviare una richiesta di rimozione.
2. Il team di supporto avvierà una richiesta di rimozione con il team Human Resources DevOps. 
3. Continuare dopo aver ricevuto conferma che l'ambiente è stato rimosso.
4. Accedere a LCS utilizzando l'account usato per iscriversi a Human Resources. 
5. Selezionare il progetto Human Resources contenente l'ambiente. 
6. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**. 
7. Selezionare l'istanza che si desidera rimuovere, che deve essere contrassegnata con lo stato di distribuzione **Eliminata**.
8. Selezionare **Rimuovere istanza** e confermare la decisione. 

## <a name="recover-a-soft-deleted-environment"></a>Ripristinare un ambiente eliminato temporaneamente

Se si elimina l'ambiente Power Apps a cui è connesso l'ambiente Human Resources, lo stato dell'ambiente Human Resources in Lifecycle Services sarà **Eliminato temporaneamente**. In questo caso, gli utenti non possono connettersi a Human Resources.

Per ripristinare l'ambiente:

1. Seguire le istruzioni in [Ripristinare l'ambiente Power Apps](/power-platform/admin/recover-environment).

2. Contattare il supporto per ripristinare l'ambiente Human Resources. Per ulteriori informazioni, vedere [Ottenere supporto](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Gli ambienti Power Apps vengono salvati solo per sette giorni dopo l'eliminazione. È necessario ripristinare l'ambiente entro il periodo di sette giorni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
