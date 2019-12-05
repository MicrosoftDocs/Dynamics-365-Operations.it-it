---
title: Utente non trovato nello strumento di selezione persone in Attract o Onboard
description: In questo argomento viene illustrato come procedere quando gli utenti nel tenant della società non sono visualizzati nello strumento di selezione persone in Dynamics 365 Talent - Attract o Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a6d916f87ca30aa7405a51841e56ab31bbe31ac8
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832606"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a>Utente non trovato nello strumento di selezione persone in Attract o Onboard

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Problema

Alcuni utenti validi in Microsoft Azure Active Directory (Azure AD) per il tenant non sono visualizzati durante la ricerca del nome nello strumento di selezione persone in Dynamics 365 Talent: Attract o Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Causa

Alcuni tipi di utenti non sono attualmente supportati in Attract e Onboard. Verificare che l'utente non sia un utente guest B2B Azure AD. L'informazione "Tipo utente" si trova nel pannello Azure Active Directory nel portale di Azure.

Per ulteriori informazioni su Azure B2B, vedere [Che cos'è l'accesso utente guest in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

Per alcuni utenti non B2B, è possibile che la proprietà "Tipo di utente" sia incompleta nell'oggetto **Utente**. Ciò può essere verificato e risolto utilizzando il modulo Azure AD Powershell. Per ulteriori informazioni, vedere [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Risoluzione

Per completare questi passaggi e risolvere il problema, sarà necessario disporre delle autorizzazioni di "amministratore globale" sul tenant Azure Active Directory o delle autorizzazioni per **User.ReadWrite.All**.

Per verificare il "tipo di utente" per l'utente interessato:

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
Il comando restituisce le informazioni seguenti.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Annotare la proprietà **UserType** dell'utente. Se la proprietà **UserType** è vuota, ad esempio non è "Member" o "Guest", aggiornare **UserType** utilizzando il comando seguente.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
