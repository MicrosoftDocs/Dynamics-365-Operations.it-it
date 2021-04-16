---
title: Conformità cookie
description: Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2cc2089bc3052c0c59cb0414f8301123a9a30df2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796029"
---
# <a name="cookie-compliance"></a><span data-ttu-id="00aa9-103">Conformità dei cookie</span><span class="sxs-lookup"><span data-stu-id="00aa9-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="00aa9-104">Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="00aa9-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="00aa9-105">La privacy è un fattore importante quando vengono utilizzate tecnologie di tracciabilità che interessano i clienti di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="00aa9-105">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="00aa9-106">A causa degli standard di conformità della privacy come il Regolamento generale sulla protezione dei dati (GDPR) nell'Unione Europea (UE), le linee guida elettroniche sulla privacy devono essere prese in considerazione per qualsiasi sito che attivo oggi.</span><span class="sxs-lookup"><span data-stu-id="00aa9-106">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="00aa9-107">Poiché molti siti di e-Commerce sono accessibili a livello globale per impostazione predefinita, è importante rivedere gli standard di conformità per il proprio sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="00aa9-107">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="00aa9-108">Per ulteriori informazioni sui principi di base utilizzati da Microsoft per la conformità dei cookie, visitare il [Centro di protezione di Microsoft ](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="00aa9-108">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="00aa9-109">Su questo sito, puoi anche ottenere ulteriori informazioni sulle aree di conformità e della privacy.</span><span class="sxs-lookup"><span data-stu-id="00aa9-109">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="00aa9-110">La seguente tabella mostra l'attuale elenco di riferimento dei cookie inseriti dai siti Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="00aa9-110">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="00aa9-111">Nome del cookie</span><span class="sxs-lookup"><span data-stu-id="00aa9-111">Cookie name</span></span>                               | <span data-ttu-id="00aa9-112">Uso</span><span class="sxs-lookup"><span data-stu-id="00aa9-112">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="00aa9-113">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="00aa9-113">.AspNet.Cookies</span></span>                             | <span data-ttu-id="00aa9-114">Archivia cookie di autenticazione Microsoft Azure Active Directory (Azure AD) per Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="00aa9-114">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="00aa9-115">Archivia le informazioni principali dell'utente crittografate (nome, cognome, e-mail).</span><span class="sxs-lookup"><span data-stu-id="00aa9-115">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="00aa9-116">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="00aa9-116">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="00aa9-117">Archivia l'ID carrello utilizzato per ottenere un elenco di prodotti aggiunti all'istanza del carrello.</span><span class="sxs-lookup"><span data-stu-id="00aa9-117">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="00aa9-118">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="00aa9-118">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="00aa9-119">Tracciamento del consenso per la conformità dei cookie.</span><span class="sxs-lookup"><span data-stu-id="00aa9-119">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="00aa9-120">ai_session</span><span class="sxs-lookup"><span data-stu-id="00aa9-120">ai_session</span></span>                                  | <span data-ttu-id="00aa9-121">Rileva quante sessioni di attività dell'utente hanno incluso determinate pagine e funzionalità dell'app.</span><span class="sxs-lookup"><span data-stu-id="00aa9-121">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="00aa9-122">ai_user</span><span class="sxs-lookup"><span data-stu-id="00aa9-122">ai_user</span></span>                                     | <span data-ttu-id="00aa9-123">Rileva quante persone hanno utilizzato l'app e le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="00aa9-123">Detects how many people used the app and its features.</span></span> <span data-ttu-id="00aa9-124">Gli utenti vengono conteggiati utilizzando ID anonimi.</span><span class="sxs-lookup"><span data-stu-id="00aa9-124">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="00aa9-125">b2cru</span><span class="sxs-lookup"><span data-stu-id="00aa9-125">b2cru</span></span>                                       | <span data-ttu-id="00aa9-126">Archivia l'URL di reindirizzamento in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="00aa9-126">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="00aa9-127">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="00aa9-127">JSESSIONID</span></span>                                  | <span data-ttu-id="00aa9-128">Utilizzato dal connettore di pagamento Adyen per archiviare la sessione utente.</span><span class="sxs-lookup"><span data-stu-id="00aa9-128">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="00aa9-129">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="00aa9-129">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="00aa9-130">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="00aa9-130">Authentication</span></span>                                               |
| <span data-ttu-id="00aa9-131">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="00aa9-131">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="00aa9-132">Utilizzato per mantenere lo stato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="00aa9-132">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="00aa9-133">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="00aa9-133">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="00aa9-134">Token CRSF (cross-site request forgery) utilizzato per la protezione da CRSF.</span><span class="sxs-lookup"><span data-stu-id="00aa9-134">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="00aa9-135">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="00aa9-135">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="00aa9-136">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="00aa9-136">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="00aa9-137">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="00aa9-137">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="00aa9-138">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="00aa9-138">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="00aa9-139">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="00aa9-139">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="00aa9-140">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="00aa9-140">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="00aa9-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="00aa9-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="00aa9-142">Utilizzato per mantenere la sessione SSO.</span><span class="sxs-lookup"><span data-stu-id="00aa9-142">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="00aa9-143">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="00aa9-143">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="00aa9-144">Utilizzato per tenere traccia delle transazioni (il numero di schede aperte autenticate rispetto a un sito business-to-consumer (B2C)), inclusa la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="00aa9-144">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="00aa9-145">Consenso per i cookie dell'utente del sito in un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="00aa9-145">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="00aa9-146">Se una funzionalità o un modulo del sito di e-commerce utilizza un cookie non essenziale, è necessario ottenere il consenso dell'utente del sito prima che il cookie venga tracciato.</span><span class="sxs-lookup"><span data-stu-id="00aa9-146">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="00aa9-147">Per consentire agli utenti del sito di fornire il consenso per i cookie sul sito di e-commerce, un autore del sito deve aggiungere e configurare un modulo consenso per i cookie nel modulo intestazione della pagina per garantire che il consenso venga richiesto e ricevuto.</span><span class="sxs-lookup"><span data-stu-id="00aa9-147">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="00aa9-148">È necessario fornire il consenso dell'utente del sito prima che una funzionalità o un modulo che utilizza un cookie non essenziale possa essere visualizzato su una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="00aa9-148">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="00aa9-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="00aa9-149">Additional resources</span></span>

[<span data-ttu-id="00aa9-150">Funzionalità e capacità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="00aa9-150">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="00aa9-151">Panoramica sulla conformità</span><span class="sxs-lookup"><span data-stu-id="00aa9-151">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="00aa9-152">Aggiungere una pagina dell'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="00aa9-152">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="00aa9-153">Sostituire gli ID utente associati alle modifiche al contenuto monitorato</span><span class="sxs-lookup"><span data-stu-id="00aa9-153">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="00aa9-154">Modulo consenso per i cookie</span><span class="sxs-lookup"><span data-stu-id="00aa9-154">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="00aa9-155">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="00aa9-155">Header module</span></span>](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
