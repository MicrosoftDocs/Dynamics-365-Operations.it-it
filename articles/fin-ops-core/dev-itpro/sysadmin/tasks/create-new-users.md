---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 02/06/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6d884dfe30be5684a90925d4d2d9ab7eebca5b44
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029811"
---
# <a name="create-new-users"></a>Creare nuovi utenti

[!include [task guide banner](../../includes/task-guide-banner.md)]

Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associare un utente a una licenza (solo nuovi tipi di licenza)
Per i clienti in uno dei nuovi tipi di licenza aggiunti nell'ottobre 2019, gli utenti devono essere associati a una licenza. Gli utenti associati a una licenza vengono aggiunti automaticamente come utenti del sistema che non hanno un ruolo al loro primo accesso.

Gli amministratori di sistema possono [assegnare licenze a utenti](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide) nell'[interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Associare un utente esterno a una licenza (solo nuovi tipi di licenza)
Gli utenti esterni al tenant in cui è stato distribuito l'ambiente devono essere rappresentati nella directory del tenant host ( Azure Active Directory (Azure AD)) di modo che possano essere assegnate le licenze. Tali utenti esterni devono essere aggiunti al tenant in Azure AD come utenti guest e devono quindi esservi assegnate le licenze appropriate. Per ulteriori informazioni, vedere [Aggiungere utenti di collaborazione B2B Azure Active Directory nel portale di Azure ](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Aggiungere un nuovo utente
1. Selezionare **Amministrazione sistema \> Utenti \> Utenti**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **ID utente** immettere un identificatore univoco per l'utente. È necessario un ID utente.  
4. Nel campo **Nome utente** immettere il nome dell'utente.  
5. Nel campo **Dominio** immettere il dominio dell'utente.  
6. Nel campo **Alias**, immettere l'alias dell'utente.  
7. Nel campo **Società**, selezionare la società desiderata. 
8. Nella Scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli** per assegnare utenti a ruoli di sicurezza. Per ulteriori informazioni, vedere [Assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md).
9. Selezionare **OK**.
10. Selezionare **Salva**.

## <a name="import-users"></a>Importa utenti
1. Nel riquadro azioni, selezionare **Importa utenti**.
2. Nell'elenco contrassegnare la riga selezionata.
3. Selezionare **Importa utenti**.
4. Selezionare **Chiudi**.

