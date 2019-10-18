---
title: Assegnare gli utenti ai ruoli di sicurezza
description: Per accedere alle app Finance and Operations, è necessario assegnare utenti a ruoli di sicurezza.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180969"
---
# <a name="assign-users-to-security-roles"></a>Assegnare gli utenti ai ruoli di sicurezza

[!include [task guide banner](../../includes/task-guide-banner.md)]

Per utilizzare altri elementi oltre alle capacità comuni, è necessario assegnare utenti a ruoli di sicurezza. In questa procedura viene illustrato come gli amministratori di sistema possono assegnare utenti ai ruoli automaticamente, in base ai dati aziendali. 

## <a name="automatically-assign-users-to-roles"></a>Assegnare automaticamente utenti a ruoli
1. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
2. Nella struttura selezionare "Supervisore contabile". Selezionare il ruolo per il quale si desidera configurare la regola. In questo esempio selezionare Supervisore contabile. 
3. Fare clic su **Aggiungi regola** per aprire la finestra di dialogo a discesa.
4. Nell'elenco **Seleziona query**, trovare e selezionare il record desiderato. Selezionare la query da usare per questa regola.  
5. Nell'elenco **Nome regola di appartenenza**, fare clic sul collegamento nella riga selezionata.
6. Fare clic su **Modifica query**. Modificare la query, se necessario.  
7. Fare clic su **OK**.

## <a name="exclude-users-from-automatic-role-assignment"></a>Escludere gli utenti dall'assegnazione automatica dei ruoli
1. Chiudere la pagina.
2. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
3. Nella struttura selezionare "Supervisore contabile". Selezionare un ruolo. In questo esempio selezionare Supervisore contabile.  
4. Nel menu **Utenti assegnati al ruolo**, selezionare **Assegna/escludi utenti manualmente**.
5. Nell'elenco **Assegna o escludi utenti da ruolo**, contrassegnare la riga selezionata. Selezionare un utente.  
6. Nel **Riquadro azioni**, selezionare **Escludi da ruolo**.
    
    Fare clic su **Escludi da ruolo** per escludere gli utenti selezionati dal ruolo. Per rimuovere le esclusioni, selezionare gli utenti per i quali si desidera rimuovere le esclusioni, quindi fare clic su **Reimposta stato**. Quando si rimuove un'esclusione reimpostando lo stato dell'utente, il ruolo utente viene assegnato di nuovo automaticamente. Tuttavia, l'utente non viene assegnato immediatamente al ruolo o non viene escluso dal ruolo quando si reimposta lo stato. Invece, l'utente viene assegnato al ruolo o viene rimosso dal ruolo alla successiva esecuzione delle regole di assegnazione automatica dei ruoli.  
