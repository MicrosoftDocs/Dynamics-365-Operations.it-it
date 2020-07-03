---
title: Conformità cookie
description: Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446915"
---
# <a name="cookie-compliance"></a><span data-ttu-id="707a9-103">Conformità cookie</span><span class="sxs-lookup"><span data-stu-id="707a9-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="707a9-104">Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="707a9-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="707a9-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="707a9-105">Overview</span></span>

<span data-ttu-id="707a9-106">La privacy è un fattore importante quando vengono utilizzate tecnologie di tracciabilità che interessano i clienti di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="707a9-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="707a9-107">A causa degli standard di conformità della privacy come il Regolamento generale sulla protezione dei dati (GDPR) nell'Unione Europea (UE), le linee guida elettroniche sulla privacy devono essere prese in considerazione per qualsiasi sito che attivo oggi.</span><span class="sxs-lookup"><span data-stu-id="707a9-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="707a9-108">Poiché molti siti di e-Commerce sono accessibili a livello globale per impostazione predefinita, è importante rivedere gli standard di conformità per il proprio sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="707a9-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="707a9-109">Per ulteriori informazioni sui principi di base utilizzati da Microsoft per la conformità dei cookie, visitare il [Centro di protezione di Microsoft ](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="707a9-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="707a9-110">Su questo sito, puoi anche ottenere ulteriori informazioni sulle aree di conformità e della privacy.</span><span class="sxs-lookup"><span data-stu-id="707a9-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="707a9-111">La seguente tabella mostra l'attuale elenco di riferimento dei cookie inseriti dai siti Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="707a9-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="707a9-112">Nome del cookie</span><span class="sxs-lookup"><span data-stu-id="707a9-112">Cookie name</span></span>                               | <span data-ttu-id="707a9-113">Uso</span><span class="sxs-lookup"><span data-stu-id="707a9-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="707a9-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="707a9-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="707a9-115">Archivia cookie di autenticazione Microsoft Azure Active Directory (Azure AD) per Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="707a9-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="707a9-116">Archivia le informazioni principali dell'utente crittografate (nome, cognome, e-mail).</span><span class="sxs-lookup"><span data-stu-id="707a9-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="707a9-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="707a9-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="707a9-118">Archivia l'ID carrello utilizzato per ottenere un elenco di prodotti aggiunti all'istanza del carrello.</span><span class="sxs-lookup"><span data-stu-id="707a9-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="707a9-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="707a9-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="707a9-120">Tracciamento del consenso per la conformità dei cookie.</span><span class="sxs-lookup"><span data-stu-id="707a9-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="707a9-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="707a9-121">ai_session</span></span>                                  | <span data-ttu-id="707a9-122">Rileva quante sessioni di attività dell'utente hanno incluso determinate pagine e funzionalità dell'app.</span><span class="sxs-lookup"><span data-stu-id="707a9-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="707a9-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="707a9-123">ai_user</span></span>                                     | <span data-ttu-id="707a9-124">Rileva quante persone hanno utilizzato l'app e le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="707a9-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="707a9-125">Gli utenti vengono conteggiati utilizzando ID anonimi.</span><span class="sxs-lookup"><span data-stu-id="707a9-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="707a9-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="707a9-126">b2cru</span></span>                                       | <span data-ttu-id="707a9-127">Archivia l'URL di reindirizzamento in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="707a9-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="707a9-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="707a9-128">JSESSIONID</span></span>                                  | <span data-ttu-id="707a9-129">Utilizzato dal connettore di pagamento Adyen per archiviare la sessione utente.</span><span class="sxs-lookup"><span data-stu-id="707a9-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="707a9-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="707a9-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="707a9-131">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="707a9-131">Authentication</span></span>                                               |
| <span data-ttu-id="707a9-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="707a9-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="707a9-133">Utilizzato per mantenere lo stato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="707a9-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="707a9-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="707a9-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="707a9-135">Token CRSF (cross-site request forgery) utilizzato per la protezione da CRSF.</span><span class="sxs-lookup"><span data-stu-id="707a9-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="707a9-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="707a9-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="707a9-137">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="707a9-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="707a9-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="707a9-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="707a9-139">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="707a9-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="707a9-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="707a9-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="707a9-141">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="707a9-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="707a9-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="707a9-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="707a9-143">Utilizzato per mantenere la sessione SSO.</span><span class="sxs-lookup"><span data-stu-id="707a9-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="707a9-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="707a9-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="707a9-145">Utilizzato per tenere traccia delle transazioni (il numero di schede aperte autenticate rispetto a un sito business-to-consumer (B2C)), inclusa la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="707a9-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="707a9-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="707a9-146">Additional resources</span></span>

[<span data-ttu-id="707a9-147">Funzionalità e capacità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="707a9-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="707a9-148">Panoramica sulla conformità</span><span class="sxs-lookup"><span data-stu-id="707a9-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="707a9-149">Aggiungere una pagina dell'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="707a9-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="707a9-150">Sostituire gli ID utente associati alle modifiche al contenuto monitorato</span><span class="sxs-lookup"><span data-stu-id="707a9-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
