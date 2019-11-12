---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
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
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570523"
---
# <a name="create-new-users"></a>Creare nuovi utenti

[!include [task guide banner](../../includes/task-guide-banner.md)]

Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associare un utente a una licenza (solo nuovi tipi di licenza)
Per i clienti in uno dei nuovi tipi di licenza aggiunti nell'ottobre 2019, gli utenti devono essere associati a una licenza. Gli utenti associati a una licenza vengono aggiunti automaticamente come utenti del sistema che non hanno un ruolo al loro primo accesso. Gli utenti non associati a una licenza ricevono un messaggio di avviso.

Gli amministratori di sistema possono [assegnare licenze a utenti](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide) nell'[interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).

## <a name="add-a-new-user"></a>Aggiungere un nuovo utente
1. Selezionare **Amministrazione sistema \> Utenti \> Utenti**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **ID utente** immettere un identificatore univoco per l'utente. È necessario un ID utente.  
4. Nel campo **Nome utente** immettere il nome dell'utente.  
5. Nel campo **Dominio** immettere il dominio dell'utente.  
6. Nel campo **Alias**, immettere l'alias dell'utente.  
7. Nel campo **Società**, selezionare la società desiderata. 
8. Nella Scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli** per [assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md).
9. Selezionare **OK**.
10. Selezionare **Salva**.

## <a name="import-users"></a>Importa utenti
1. Nel riquadro azioni, selezionare **Importa utenti**.
2. Nell'elenco contrassegnare la riga selezionata.
3. Selezionare **Importa utenti**.
4. Selezionare **Chiudi**.

