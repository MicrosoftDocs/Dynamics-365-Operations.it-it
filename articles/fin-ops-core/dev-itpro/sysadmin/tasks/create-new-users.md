---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00da7c69ff18abd02ca0cd7984e9b2de5e453a0c
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103327"
---
# <a name="create-new-users"></a>Creare nuovi utenti

[!include [banner](../../includes/banner.md)]

Prima di poter accedere alle app per la finanza e le operazioni, devi essere aggiunto alla pagina **Utenti** (**Amministrazione di sistema \> Utenti \> Utenti**). Gli utenti includono dipendenti interni della tua organizzazione o clienti e fornitori esterni. Gli utenti possono essere importati o aggiunti manualmente. Tutti gli utenti devono disporre di una licenza corretta per un utilizzo conforme.

Per informazioni su come acquistare e ottenere la licenza per le app per la finanza e le operazioni, vedere [Guida alle licenze Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Assegnare una licenza a un utente
Gli amministratori di sistema possono [assegnare licenze agli utenti](/office365/admin/subscriptions-and-billing/assign-licenses-to-users) nell'[interfaccia di amministrazione di Microsoft 365](/office365/admin/admin-overview/about-the-admin-center).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Aggiungere un utente esterno in Azure AD e assegnare una licenza 
Gli utenti esterni devono essere rappresentati nella directory del tenant (Azure Active Directory (Azure AD)) in modo che possano essere assegnate loro le licenze. Tali utenti esterni devono essere aggiunti al tenant in Azure AD come utenti guest e devono quindi esservi assegnate le licenze appropriate. Un requisito per le app per la finanza e le operazioni prevede che l'azienda dell'utente ospite debba utilizzare Azure AD. Per ulteriori informazioni, vedere [Aggiungere utenti di collaborazione B2B Azure Active Directory nel portale di Azure ](/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importare nuovi utenti da Azure AD 
1. Passa a **Amministrazione sistema** \> **Utente** \> **Utenti**.
2. Nel riquadro azioni, selezionare **Importa utenti**.
3. Seleziona gli utenti da importare. L'elenco include gli utenti Azure AD che attualmente non sono utenti in questo ambiente.
4. Selezionare **Importa utenti**.
5. Selezionare **Chiudi**.

> [!NOTE]
> Il valore per il campo **Azienda** verrà impostato in base all'azienda della sessione corrente per l'amministratore. Dopo l'importazione, è necessario assegnare ruoli e organizzazioni in base alle esigenze. Per ulteriori informazioni, vedere [Assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md). A seconda delle condizioni, potrebbe anche essere necessario associare l'utente a un **Utente tipo** e aggiornare le opzioni dell'utente come la lingua.

## <a name="manually-add-a-new-user"></a>Aggiungere manualmente un nuovo utente
1. Passa ad **Amministrazione sistema** \> **Utenti** \> **Utenti**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **ID utente** immettere un identificatore univoco per l'utente.   
4. Nel campo **Nome utente** immettere il nome dell'utente.  
5. Nel campo **Provider**:
 - Per gli utenti interni, utilizza il valore predefinito. Ad esempio, il tuo tenant Azure AD con prefisso https://sts.windows.net/.  
 - Per gli utenti non Azure AD, come gli account Service-2-Service, immetti un valore di testo di base. Ad esempio: NA. Questo valore consentirà di evitare chiamate di autenticazione errate che potrebbero causare errori se viene utilizzato un valore del provider di identità valido.  
 - Per gli utenti esterni o gli ospiti, aggiungi il loro nome tenant Azure AD dopo https://sts.windows.net/.
6. Nel campo **E-mail** immetti il nome dell'entità utente/indirizzo e-mail completo dell'utente.  
7. Nel campo **Azienda** seleziona la società di avvio predefinita per l'utente. 
8. Selezionare **Salva**.

I valori per il provider di identità e l'ID di telemetria verranno aggiornati in base a una chiamata [Microsoft Graph](/graph/overview), quando il record dell'utente viene salvato. L'ID di telemetria si basa sull'ID oggetto/ identificatore di sicurezza (SID) dell'utente in Azure AD.

> [!NOTE]
> Dopo aver aggiunto un utente, è necessario assegnare ruoli e organizzazioni in base alle esigenze. Per ulteriori informazioni, vedere [Assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md). A seconda delle condizioni, potrebbe anche essere necessario associare l'utente a un **Utente tipo** e aggiornare le **opzioni dell'utente** come la lingua.

## <a name="change-a-user-id"></a>Modificare un ID utente
Per modificare un ID utente, è necessario rinominare la chiave nel database. Quando si modifica un ID utente utilizzando questa procedura, tutte le impostazioni utente correlate vengono modificate per utilizzare il nuovo ID utente. Ad esempio, le informazioni sull'utilizzo nella tabella **SysLastValue** viene aggiornata per fare riferimento al nuovo ID utente.

> [!NOTE]
> L'ID utente è la chiave primaria della tabella delle informazioni sull'utente. La ridenominazione della chiave primaria può richiedere del tempo per gli utenti esistenti poiché tutti i riferimenti alla chiave vengono aggiornati anche nel database. 

1. Selezionare **Amministrazione sistema \> Utenti \> Utenti**.
2. Seleziona un utente nell'elenco e seleziona **Opzioni\> Informazioni sui record**.
3. Seleziona **Rinomina**.
4. Immettere un valore nuovo e univoco per l?ID utente e quindi seleziona **OK**. 
5. Seleziona **Sì** per confermare.

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori opzioni per implementare gli utenti B2B, vedi [Esportare utenti B2B in Azure AD](../implement-b2b.md).

Per informazioni sugli account di sistema preconfigurati, vedi [Account di sistema preconfigurati](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
