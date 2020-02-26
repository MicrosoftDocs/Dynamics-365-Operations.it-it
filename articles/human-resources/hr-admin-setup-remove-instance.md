---
title: Rimuovere un'istanza
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009495"
---
# <a name="remove-an-instance"></a>Rimuovere un'istanza

In questo argomento viene descritto il processo di rimozione di un ambiente test drive o di produzione per Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Rimuovere un ambiente test drive

Il provisioning dei test drive di Human Resources viene effettuato con criteri di scadenza di 60 giorni. I proprietari di ambienti di test drive, tuttavia, hanno la possibilità di terminare la propria verifica in anticipo completando i passaggi seguenti. 

1. Accedere all'[Interfaccia di amministrazione di Power Apps](https://admin.businessplatform.microsoft.com/).
2. Selezionare **Ambienti**.
3. Selezionare l'ambiente test drive, che ha un criterio di denominazione simile al seguente: TestDrive - alias@domain
4. Selezionare **Elimina** e confermare la decisione. 

L'ambiente test drive esistente verrà rimosso. Quando viene rimosso, è possibile eseguire l'iscrizione a un nuovo ambiente test drive. 

## <a name="remove-a-production-environment"></a>Rimuovere un ambiente di produzione

In questo articolo si presuppone che Human Resources sia già stato acquistato tramite un provider di soluzioni cloud o un contratto Enterprise Architecture (EA). 

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
4.  Accedere a LCS utilizzando l'account usato per iscriversi a Human Resources. 
5. Selezionare il progetto Human Resources contenente l'ambiente. 
6. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**. 
7. Selezionare l'istanza che si desidera rimuovere, che deve essere contrassegnata con lo stato di distribuzione **Non riuscita**.
8. Selezionare **Rimuovere istanza** e confermare la decisione. 
