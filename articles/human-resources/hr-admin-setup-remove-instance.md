---
title: Rimuovere un'istanza
description: Questo articolo illustra il processo di rimozione di un ambiente di prova o di produzione per Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ce676c93e133cc04ad9c49417ed2ca0d6791e93
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178474"
---
# <a name="remove-an-instance"></a>Rimuovere un'istanza

_**Si applica a**: Human Resources nell'infrastruttura autonoma_ 

> [!NOTE]
> A partire da luglio 2022, non sarà possibile eseguire il provisioning dei nuovi ambienti Human Resources nell'infrastruttura Human Resources autonoma, né potranno essere creati nuovi progetti Microsoft Dynamics Lifecycle Services (LCS) sull'infrastruttura stessa. I clienti potranno distribuire gli ambienti Human Resources nell'infrastruttura di finanza e operazioni. Per ulteriori informazioni, vedere [Provisioning di Human Resources nell'infrastruttura di finanza e operazioni](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> L'infrastruttura delle app per la finanza e le operazioni supporta l'eliminazione di un ambiente. Per ulteriori informazioni su come eliminare un ambiente, vedere [Eliminare un ambiente](../fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure.md#delete-an-environment).

Questo articolo spiega il processo di rimozione di un ambiente di prova o di produzione per Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Rimuovere un ambiente test drive

Il provisioning dei test drive di Human Resources viene effettuato con criteri di scadenza di 60 giorni. I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti. 

1. Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain
4. Selezionare **Elimina** e confermare la decisione. 

L'ambiente test drive esistente verrà rimosso. Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive. 

## <a name="remove-a-production-environment"></a>Rimuovere un ambiente di produzione

In questo articolo si presuppone che Human Resources sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA). 

Poiché un unico ambiente Human Resources è contenuto in singolo ambiente Power Apps, è possibile valutare due opzioni per la rimozione di un ambiente: 
- **Rimuovere l'intero ambiente Power Apps.** Questa opzione è preferibile se si è creato un ambiente Power Apps appositamente per il provisioning di Human Resources e l'implementazione è appena stata iniziata, oppure se non si hanno integrazioni stabilite.  
- **Rimuovere solo Human Resources.** Questa opzione è appropriata quando si è stabilito un ambiente Power Apps compilato con i dati usati in Microsoft Power Apps e Power Automate.


> [!Important]
> Prima di rimuovere l'ambiente Power Apps, assicurarsi che non sia utilizzato per integrazioni di dati al di fuori dell'ambito di Human Resources. Inoltre si noti che, gli ambienti Power Apps predefiniti non possono essere rimossi. 

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

Se si elimina l'ambiente Power Apps a cui è connesso l'ambiente Human Resources, lo stato dell'ambiente Human Resources in LCS sarà **Eliminato temporaneamente**. In questo caso, gli utenti non possono connettersi a Human Resources.

Per ripristinare l'ambiente:

1. Seguire le istruzioni in [Ripristinare l'ambiente Power Apps](/power-platform/admin/recover-environment).

2. Contattare il supporto per ripristinare l'ambiente Human Resources. Per ulteriori informazioni, vedere [Ottenere supporto](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Gli ambienti Power Apps vengono salvati solo per sette giorni dopo l'eliminazione. È necessario ripristinare l'ambiente entro il periodo di sette giorni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
