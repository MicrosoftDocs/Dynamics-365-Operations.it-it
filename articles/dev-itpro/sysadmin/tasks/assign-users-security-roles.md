---
title: Assegnare gli utenti ai ruoli di sicurezza
description: Per accedere a Microsoft Dynamics 365 for Finance and Operations, edizione Enterprise, gli utenti devono essere assegnati a ruoli di sicurezza.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55cb085bb5170aa4894a2240a12f6ca451b922fb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556711"
---
# <a name="assign-users-to-security-roles"></a>Assegnare gli utenti ai ruoli di sicurezza

[!include [task guide banner](../../includes/task-guide-banner.md)]

Per accedere a Microsoft Dynamics 365 for Finance and Operations, edizione Enterprise, gli utenti devono essere assegnati a ruoli di sicurezza. In questa procedura viene illustrato come gli amministratori di sistema possono assegnare utenti ai ruoli automaticamente, in base ai dati aziendali. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="automatically-assign-users-to-roles"></a>Assegnare automaticamente utenti a ruoli
1. Passare ad Amministrazione sistema > Sicurezza > Assegna utenti a ruoli.
2. Nella struttura selezionare "Supervisore contabile".
    * Selezionare il ruolo per il quale si desidera configurare la regola. In questo esempio selezionare Supervisore contabile.  
3. Fare clic su Aggiungi regola per aprire la finestra di dialogo a discesa.
4. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare la query da usare per questa regola.  
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Fare clic su Modifica query.
    * Modificare la query, se necessario.  
7. Fare clic su OK.

## <a name="exclude-users-from-automatic-role-assignment"></a>Escludere gli utenti dall'assegnazione automatica dei ruoli
1. Chiudere la pagina.
2. Passare ad Amministrazione sistema > Sicurezza > Assegna utenti a ruoli.
3. Nella struttura selezionare "Supervisore contabile".
    * Selezionare un ruolo. In questo esempio selezionare Supervisore contabile.  
4. Fare clic su Assegna/escludi utenti manualmente.
5. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare un utente.  
6. Fare clic su Escludi da ruolo.
    * Fare clic su Escludi da ruolo per escludere gli utenti selezionati dal ruolo. Per rimuovere le esclusioni, selezionare gli utenti per i quali si desidera rimuovere le esclusioni, quindi fare clic su Reimposta stato. Quando si rimuove un'esclusione reimpostando lo stato dell'utente, il ruolo utente viene assegnato di nuovo automaticamente. Tuttavia, l'utente non viene assegnato immediatamente al ruolo o non viene escluso dal ruolo quando si reimposta lo stato. Invece, l'utente viene assegnato al ruolo o viene rimosso dal ruolo alla successiva esecuzione delle regole di assegnazione automatica dei ruoli.  

