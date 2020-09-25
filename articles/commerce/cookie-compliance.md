---
title: Conformità cookie
description: Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 4f54b9b8130a167dbecdb13fccd7039f827f6ed0
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761323"
---
# <a name="cookie-compliance"></a><span data-ttu-id="02cc6-103">Conformità cookie</span><span class="sxs-lookup"><span data-stu-id="02cc6-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02cc6-104">Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02cc6-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="02cc6-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="02cc6-105">Overview</span></span>

<span data-ttu-id="02cc6-106">La privacy è un fattore importante quando vengono utilizzate tecnologie di tracciabilità che interessano i clienti di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="02cc6-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="02cc6-107">A causa degli standard di conformità della privacy come il Regolamento generale sulla protezione dei dati (GDPR) nell'Unione Europea (UE), le linee guida elettroniche sulla privacy devono essere prese in considerazione per qualsiasi sito che attivo oggi.</span><span class="sxs-lookup"><span data-stu-id="02cc6-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="02cc6-108">Poiché molti siti di e-Commerce sono accessibili a livello globale per impostazione predefinita, è importante rivedere gli standard di conformità per il proprio sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="02cc6-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="02cc6-109">Per ulteriori informazioni sui principi di base utilizzati da Microsoft per la conformità dei cookie, visitare il [Centro di protezione di Microsoft ](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="02cc6-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="02cc6-110">Su questo sito, puoi anche ottenere ulteriori informazioni sulle aree di conformità e della privacy.</span><span class="sxs-lookup"><span data-stu-id="02cc6-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="02cc6-111">La seguente tabella mostra l'attuale elenco di riferimento dei cookie inseriti dai siti Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02cc6-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="02cc6-112">Nome del cookie</span><span class="sxs-lookup"><span data-stu-id="02cc6-112">Cookie name</span></span>                               | <span data-ttu-id="02cc6-113">Uso</span><span class="sxs-lookup"><span data-stu-id="02cc6-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="02cc6-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="02cc6-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="02cc6-115">Archivia cookie di autenticazione Microsoft Azure Active Directory (Azure AD) per Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="02cc6-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="02cc6-116">Archivia le informazioni principali dell'utente crittografate (nome, cognome, e-mail).</span><span class="sxs-lookup"><span data-stu-id="02cc6-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="02cc6-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="02cc6-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="02cc6-118">Archivia l'ID carrello utilizzato per ottenere un elenco di prodotti aggiunti all'istanza del carrello.</span><span class="sxs-lookup"><span data-stu-id="02cc6-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="02cc6-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="02cc6-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="02cc6-120">Tracciamento del consenso per la conformità dei cookie.</span><span class="sxs-lookup"><span data-stu-id="02cc6-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="02cc6-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="02cc6-121">ai_session</span></span>                                  | <span data-ttu-id="02cc6-122">Rileva quante sessioni di attività dell'utente hanno incluso determinate pagine e funzionalità dell'app.</span><span class="sxs-lookup"><span data-stu-id="02cc6-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="02cc6-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="02cc6-123">ai_user</span></span>                                     | <span data-ttu-id="02cc6-124">Rileva quante persone hanno utilizzato l'app e le sue funzionalità.</span><span class="sxs-lookup"><span data-stu-id="02cc6-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="02cc6-125">Gli utenti vengono conteggiati utilizzando ID anonimi.</span><span class="sxs-lookup"><span data-stu-id="02cc6-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="02cc6-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="02cc6-126">b2cru</span></span>                                       | <span data-ttu-id="02cc6-127">Archivia l'URL di reindirizzamento in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="02cc6-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="02cc6-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="02cc6-128">JSESSIONID</span></span>                                  | <span data-ttu-id="02cc6-129">Utilizzato dal connettore di pagamento Adyen per archiviare la sessione utente.</span><span class="sxs-lookup"><span data-stu-id="02cc6-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="02cc6-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="02cc6-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="02cc6-131">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="02cc6-131">Authentication</span></span>                                               |
| <span data-ttu-id="02cc6-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="02cc6-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="02cc6-133">Utilizzato per mantenere lo stato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="02cc6-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="02cc6-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="02cc6-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="02cc6-135">Token CRSF (cross-site request forgery) utilizzato per la protezione da CRSF.</span><span class="sxs-lookup"><span data-stu-id="02cc6-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="02cc6-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="02cc6-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="02cc6-137">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="02cc6-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="02cc6-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="02cc6-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="02cc6-139">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="02cc6-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="02cc6-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="02cc6-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="02cc6-141">Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="02cc6-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="02cc6-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="02cc6-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="02cc6-143">Utilizzato per mantenere la sessione SSO.</span><span class="sxs-lookup"><span data-stu-id="02cc6-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="02cc6-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="02cc6-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="02cc6-145">Utilizzato per tenere traccia delle transazioni (il numero di schede aperte autenticate rispetto a un sito business-to-consumer (B2C)), inclusa la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="02cc6-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="02cc6-146">Consenso per i cookie dell'utente del sito in un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="02cc6-146">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="02cc6-147">Se una funzionalità o un modulo del sito di e-commerce utilizza un cookie non essenziale, è necessario ottenere il consenso dell'utente del sito prima che il cookie venga tracciato.</span><span class="sxs-lookup"><span data-stu-id="02cc6-147">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="02cc6-148">Per consentire agli utenti del sito di fornire il consenso per i cookie sul sito di e-commerce, un autore del sito deve aggiungere e configurare un modulo consenso per i cookie nel modulo intestazione della pagina per garantire che il consenso venga richiesto e ricevuto.</span><span class="sxs-lookup"><span data-stu-id="02cc6-148">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="02cc6-149">È necessario fornire il consenso dell'utente del sito prima che una funzionalità o un modulo che utilizza un cookie non essenziale possa essere visualizzato su una pagina del sito.</span><span class="sxs-lookup"><span data-stu-id="02cc6-149">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02cc6-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="02cc6-150">Additional resources</span></span>

[<span data-ttu-id="02cc6-151">Funzionalità e capacità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="02cc6-151">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="02cc6-152">Panoramica sulla conformità</span><span class="sxs-lookup"><span data-stu-id="02cc6-152">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="02cc6-153">Aggiungere una pagina dell'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="02cc6-153">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="02cc6-154">Sostituire gli ID utente associati alle modifiche al contenuto monitorato</span><span class="sxs-lookup"><span data-stu-id="02cc6-154">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="02cc6-155">Modulo consenso per i cookie</span><span class="sxs-lookup"><span data-stu-id="02cc6-155">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="02cc6-156">Modulo intestazione</span><span class="sxs-lookup"><span data-stu-id="02cc6-156">Header module</span></span>](author-header-module.md)
