---
title: Identificare e risolvere conflitti di separazione dei compiti
description: Questo articolo illustra come identificare e risolvere conflitti di separazione dei compiti
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd36db5df2b6871d410bb1feaae825909ec9b3ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883479"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificare e risolvere conflitti di separazione dei compiti

[!include [banner](../../includes/banner.md)]

Questo articolo illustra come identificare e risolvere conflitti di separazione dei compiti È possibile impostare le regole per separare i compiti che devono essere eseguiti da utenti diversi. Questo concetto è denominato separazione dei compiti. Quando la definizione di un ruolo di sicurezza o le assegnazioni ruoli di un utente violano le regole, il conflitto viene annotato. Tutti i conflitti devono essere risolti dall'amministratore. Completare la procedura riportata di seguito per identificare e risolvere i conflitti.

Dopo aver aggiunto una regola, verificare che tutti i ruoli esistenti siano conformi. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Verificare se i ruoli e i compiti esistenti sono conformi alle nuove regole di separazione dei compiti
1. Scegliere **Amministrazione sistema** > **Sicurezza** > **Separazione dei compiti** > **Regole di separazione dei compiti**.
3. Selezionare **Convalida compiti e ruoli**. Se i ruoli esistenti violano le regole, verrà visualizzato un messaggio contenente il nome del ruolo, il ruolo e i nomi dei compiti in conflitto. I ruoli in conflitto devono essere modificati utilizzando **Configurazione della sicurezza** e non possono includere compiti in conflitto. Se nessun ruolo viola la regola selezionata, verrà visualizzato un messaggio per indicare che tutti i ruoli sono conformi.   

> [!NOTE]
> La convalida viene eseguita solo per la regola selezionata. È importante convalidare la conformità per ciascuna regola.   

Quando crei o modifichi un ruolo, le regole per la separazione dei compiti vengono applicate automaticamente. Non è possibile assegnare compiti in conflitto a un ruolo.

Successivamente, verifica che tutte le assegnazioni di ruolo esistenti siano conformi.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verificare se le assegnazioni utente-ruolo sono conformi alle nuove regole di separazione dei compiti
1. Scegliere **Amministrazione sistema > Sicurezza > Separazione dei compiti > Verifica conformità delle assegnazioni utente-ruolo**.
2. Selezionare **OK**. I risultati della convalida vengono visualizzati in una notifica. I conflitti vengono registrati nella pagina **Conflitti di separazione dei compiti non risolti**.   

Quando assegni utenti ai ruoli, le regole per la separazione dei compiti vengono applicate automaticamente. Se si tenta di assegnare un utente a ruoli che contengono compiti in conflitto, viene visualizzato un messaggio di errore. È quindi necessario risolvere il conflitto negando o consentendo l'assegnazione di un ruolo aggiuntivo. Il ruolo aggiuntivo verrà assegnato dopo che l'assegnazione è consentita. 

> [!NOTE]
> I conflitti non sono attualmente verificati per gli utenti a cui sono assegnati ruoli in base ai gruppi di dominio Active Directory.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Visualizzare e risolvere assegnazioni di ruoli utente in conflitto
1. Scegliere **Amministrazione sistema** > **Sicurezza** > **Separazione dei compiti** > **Conflitti di separazione dei compiti non risolti**. 
2. Selezionare un conflitto, quindi selezionare una delle azioni seguenti: 

  - **Nega assegnazione**: consente di negare l'assegnazione dell'utente al ruolo di sicurezza aggiuntivo. Se l'utente rifiuta un'assegnazione ruoli automatica, viene contrassegnato come escluso dal ruolo. All'utente escluso non viene concesso l'accesso associato al ruolo e l'utente non può essere assegnato al ruolo fino a che l'amministratore non elimina l'esclusione. 
-  **Consenti assegnazione**: consente di ignorare il conflitto e di assegnare l'utente a entrambi il ruolo di sicurezza aggiuntivo. Se si ignora un conflitto, è necessario immettere un motivo nel campo **Motivo per ignorare**. Tutte le assegnazioni di ruolo sostituite possono essere visualizzate nella pagina **Conflitti di separazione dei compiti**.  

> [!NOTE]
> Se sono elencati più conflitti per lo stesso utente, selezionare il record utente e valutare i ruoli assegnati nella pagina **Utenti**. Per evitare questo conflitto, convalidare ogni regola dopo che è stata aggiunta o modificata.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]