---
title: Assegnare utenti a ruoli di sicurezza
description: Per accedere alle app per la finanza e le operazioni, è necessario assegnare utenti a ruoli di sicurezza.
author: Peakerbl
ms.date: 02/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103870"
---
# <a name="manage-users-and-security-roles"></a>Gestire utenti e ruoli di sicurezza

[!include [banner](../../includes/banner.md)]

Per usare altri elementi oltre alle capacità comuni nelle app per la finanza e le operazioni, è necessario assegnare utenti a ruoli di sicurezza. È possibile assegnare gli utenti ai ruoli automaticamente, in base a regole e dati aziendali, escludere gli utenti dall'assegnazione automatica dei ruoli o aggiungere manualmente gli utenti ai ruoli.

## <a name="automatically-assign-users-to-roles"></a>Assegnare automaticamente utenti a ruoli
In questa procedura viene illustrato come gli amministratori di sistema possono assegnare utenti ai ruoli automaticamente, in base ai dati aziendali. 
1. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
2. Nella struttura selezionare "Supervisore contabile". Selezionare il ruolo per il quale si desidera configurare la regola. In questo esempio selezionare Supervisore contabile. 
3. Selezionare **Aggiungi regola** per aprire il menu della finestra di dialogo.
4. Nell'elenco **Seleziona query** trovare e selezionare il record desiderato. Selezionare la query da usare per questa regola.  
5. Nell'elenco **Nome regola di appartenenza**, fare clic sul collegamento nella riga selezionata.
6. Selezionare **Modifica query**. Modificare la query, se necessario.  
7. Selezionare **OK**.
8. Selezionare **Esegui assegnazione automatica ruoli**.
9. Passare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti** (idealmente in una scheda separata del browser).
10. Esaminare i ruoli assegnati ai vari utenti per confermare che la query di assegnazione ruolo è corretta. Modificare e rieseguire se necessario.

## <a name="exclude-users-from-automatic-role-assignment"></a>Escludere gli utenti dall'assegnazione automatica dei ruoli
Questa procedura spiega come escludere gli utenti dall'assegnazione automatica dei ruoli.

1. Chiudi la pagina.
2. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
3. Nella struttura selezionare "Supervisore contabile". Selezionare un ruolo. In questo esempio selezionare Supervisore contabile.  
4. Nel menu **Utenti assegnati al ruolo**, selezionare **Assegna/escludi utenti manualmente**.
5. Nell'elenco **Assegna o escludi utenti da ruolo**, contrassegnare la riga selezionata. Selezionare un utente.  
6. Nel **Riquadro azioni**, selezionare **Escludi da ruolo**.
7. Selezionare **Escludi da ruolo** per escludere gli utenti selezionati dal ruolo. Per rimuovere le esclusioni, selezionare gli utenti per i quali si desidera rimuovere le esclusioni, quindi fare clic su **Reimposta stato**. Quando si rimuove un'esclusione reimpostando lo stato dell'utente, il ruolo utente viene assegnato automaticamente. Tuttavia, l'utente non viene assegnato immediatamente al ruolo o non viene escluso dal ruolo quando si reimposta lo stato. Invece, l'utente viene assegnato al ruolo o viene rimosso dal ruolo alla successiva esecuzione delle regole di assegnazione automatica dei ruoli.  

## <a name="manually-assign-users-to-roles"></a>Assegnare manualmente gli utenti ai ruoli
Gli utenti che vengono assegnati manualmente ai ruoli di sicurezza devono anche essere rimossi manualmente dall'amministratore. Questi utenti non vengono rimossi dai ruoli tramite le regole di assegnazione automatica dei ruoli.

1. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
2. Nella struttura selezionare un ruolo e nel menu **Utenti assegnati al ruolo** selezionare **Assegna/escludi utenti manualmente**.
4. In **Assegna o escludi utenti da ruolo** gli utenti a cui non è stato assegnato il ruolo sono elencati con **Modalità di assegnazione** impostato su **Nessuna**. Selezionare uno o più utenti a cui deve essere assegnato il ruolo.
5. Nel **riquadro azioni** selezionare **Assegna a ruolo**. **Modalità assegnazione** viene aggiornato in **Manuale** e agli utenti è ora assegnato un nuovo ruolo.

## <a name="manually-remove-users-from-roles"></a>Rimuovere manualmente gli utenti dai ruoli
Gli utenti che vengono assegnati manualmente ai ruoli di sicurezza devono anche essere rimossi manualmente dall'amministratore. Questi utenti non vengono rimossi dai ruoli tramite le regole di assegnazione automatica dei ruoli.

1. Passare **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Assegna utenti a ruoli**.
2. Per rimuovere un utente, attenersi alla seguente procedura:
   1. Nella struttura, selezionare un ruolo. 
   2. Nell'area **Utenti assegnati al ruolo** selezionare l'utente da rimuovere.
   3. Selezionare **Rimuovi** e l'utente viene rimosso dal ruolo.
3. Per rimuovere più utenti, attenersi alla seguente procedura:
   1. Nella struttura, selezionare un ruolo. 
   2. Nell'area **Utenti assegnati al ruolo**, selezionare **Assegna/escludi utenti manualmente**.
   3. Nella pagina **Assegna o escludi utenti da ruolo**, la colonna **Modalità di assegnazione** degli utenti a cui non è stato assegnato il ruolo è impostata su **Nessuna**. Selezionare gli utenti da escludere dal ruolo.
   4. Nel **Riquadro azioni**, selezionare **Escludi da ruolo**. La colonna **Modalità assegnazione** viene impostata su **Manuale** e gli utenti sono esclusi dal ruolo.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

