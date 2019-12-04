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
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a><span data-ttu-id="3d2a7-103">Utente non trovato nello strumento di selezione persone in Attract o Onboard</span><span class="sxs-lookup"><span data-stu-id="3d2a7-103">User not found in People Picker in Attract or Onboard</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="3d2a7-104">Problema</span><span class="sxs-lookup"><span data-stu-id="3d2a7-104">Issue</span></span>

<span data-ttu-id="3d2a7-105">Alcuni utenti validi in Microsoft Azure Active Directory (Azure AD) per il tenant non sono visualizzati durante la ricerca del nome nello strumento di selezione persone in Dynamics 365 Talent: Attract o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="3d2a7-106">Causa</span><span class="sxs-lookup"><span data-stu-id="3d2a7-106">Cause</span></span>

<span data-ttu-id="3d2a7-107">Alcuni tipi di utenti non sono attualmente supportati in Attract e Onboard.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="3d2a7-108">Verificare che l'utente non sia un utente guest B2B Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="3d2a7-109">L'informazione "Tipo utente" si trova nel pannello Azure Active Directory nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="3d2a7-110">Per ulteriori informazioni su Azure B2B, vedere [Che cos'è l'accesso utente guest in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="3d2a7-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="3d2a7-111">Per alcuni utenti non B2B, è possibile che la proprietà "Tipo di utente" sia incompleta nell'oggetto **Utente**.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="3d2a7-112">Ciò può essere verificato e risolto utilizzando il modulo Azure AD Powershell.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="3d2a7-113">Per ulteriori informazioni, vedere [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="3d2a7-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="3d2a7-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="3d2a7-114">Resolution</span></span>

<span data-ttu-id="3d2a7-115">Per completare questi passaggi e risolvere il problema, sarà necessario disporre delle autorizzazioni di "amministratore globale" sul tenant Azure Active Directory o delle autorizzazioni per **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="3d2a7-116">Per verificare il "tipo di utente" per l'utente interessato:</span><span class="sxs-lookup"><span data-stu-id="3d2a7-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="3d2a7-117">Il comando restituisce le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="3d2a7-118">Annotare la proprietà **UserType** dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="3d2a7-119">Se la proprietà **UserType** è vuota, ad esempio non è "Member" o "Guest", aggiornare **UserType** utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
