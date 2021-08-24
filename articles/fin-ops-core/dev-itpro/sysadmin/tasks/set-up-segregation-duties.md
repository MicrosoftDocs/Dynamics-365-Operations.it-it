---
title: Impostare la separazione dei compiti
description: È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c06ce9325d7b0894ba53d6b9782f495a48280d45e538b048d883ab86f05dabf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755750"
---
# <a name="set-up-segregation-of-duties"></a>Impostare la separazione dei compiti

[!include [banner](../../includes/banner.md)]

È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi. Questo concetto è denominato separazione dei compiti. Ad esempio, non è possibile che la stessa persona confermi l'entrata delle merci ed elabori il pagamento al fornitore. La separazione dei compiti consente di ridurre il rischio di frode e aiuta anche a rilevare errori o irregolarità. È inoltre possibile utilizzare la separazione dei compiti per applicare i criteri di controllo interno. Completare la procedura indicata di seguito per creare una regola. È necessario essere un amministratore di sistema per completare la procedura.

1. Scegliere **Amministrazione sistema** > **Sicurezza** > **Separazione dei compiti** > **Regole di separazione dei compiti**.
2. Fare clic su **Nuovo**.
3. Digitare un valore per la regola nel campo **Nome**.
4. Nel campo **Primo compito** fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato. Selezionare il primo compito che è controllato dalla regola.
6. Nel campo **Secondo compito** fare clic sul pulsante a discesa per aprire la ricerca. 
7. Nell'elenco trovare e selezionare il record desiderato. Selezionare il secondo compito che è controllato dalla regola.
10. Selezionare un'opzione nel campo **Gravità**. Selezionare la gravità del rischio che si verifica quando entrambi i compiti vengono eseguiti dallo stesso utente o ruolo.  
11. Digitare un valore nel campo **Rischio di sicurezza**. Immettere una descrizione del rischio di sicurezza.  
12. Digitare un valore nel campo **Riduzione dei rischi di sicurezza**. Immettere una descrizione delle azioni prese per attenuare il rischio di sicurezza. Ad esempio, è possibile attenuare il rischio effettuando revisioni più dettagliati del processo, svolgendo una revisione manageriale mensile o condividendo le risorse con altri reparti.     
13. Fare clic su **Salva**.

> [!IMPORTANT] 
> Il rispetto delle regole per la separazione dei compiti non viene verificato quando si crea una regola. È possibile creare una regola che crei un conflitto per i ruoli esistenti. Anche le assegnazioni di ruoli utente esistenti possono essere in conflitto con la nuova regola. È necessario convalidare la conformità dopo aver creato o modificato una regola. Per altre informazioni, vedere [Identificare e risolvere conflitti di separazione dei compiti](identify-resolve-conflicts-segregation-duties.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]