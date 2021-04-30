---
title: Autenticazione
description: Questo articolo fornisce informazioni generali su come eseguire l'autenticazione con l'API (Application Programming Interface) di Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 94d76a9f6d4a3d7afcb9b85d961899880ca9fc75
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893450"
---
# <a name="authentication"></a><span data-ttu-id="e391f-103">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="e391f-103">Authentication</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e391f-104">Questo articolo fornisce informazioni generali su come eseguire l'autenticazione con l'API (Application Programming Interface) di Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e391f-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="e391f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e391f-105">Overview</span></span>

<span data-ttu-id="e391f-106">L'API dati per Human Resources è un'implementazione OData.</span><span class="sxs-lookup"><span data-stu-id="e391f-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="e391f-107">Per ulteriori informazioni, vedere [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="e391f-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="e391f-108">L'applicazione in uso deve autenticarsi come chiamante autorizzato prima che l'API gestisca le richieste dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e391f-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="e391f-109">Elementi fondamentali</span><span class="sxs-lookup"><span data-stu-id="e391f-109">Fundamentals</span></span>

<span data-ttu-id="e391f-110">Per chiamare l'API dati, l'applicazione deve acquisire un token di accesso dalla piattaforma di identità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e391f-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="e391f-111">Il token di accesso contiene informazioni sull'applicazione e l'autorizzazione che deve chiamare le risorse in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e391f-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="e391f-112">Token di accesso</span><span class="sxs-lookup"><span data-stu-id="e391f-112">Access token</span></span>

<span data-ttu-id="e391f-113">I token di accesso emessi dalla piattaforma di identità Microsoft sono token Web JSON (JavaScript Object Notation) con codifica base64.</span><span class="sxs-lookup"><span data-stu-id="e391f-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="e391f-114">Contengono informazioni (attestazioni) che l'API dati (e altre API Web protette dalla piattaforma di identità Microsoft) utilizzano per convalidare il chiamante e assicurarsi che questi disponga delle autorizzazioni corrette per eseguire l'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="e391f-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="e391f-115">Durante le chiamate, è possibile considerare i token di accesso come opachi.</span><span class="sxs-lookup"><span data-stu-id="e391f-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="e391f-116">Bisogna sempre trasmettere i token di accesso su un canale sicuro, come Transport Layer Security (TLS) e Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="e391f-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="e391f-117">Di seguito è riportato un esempio di token di accesso emesso dalla piattaforma di identità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e391f-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="e391f-118">Per chiamare l'API dati, si allega il token di accesso come token di connessione all'intestazione di autorizzazione nella richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="e391f-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="e391f-119">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="e391f-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="e391f-120">Registrare una nuova applicazione mediante il portale di Azure</span><span class="sxs-lookup"><span data-stu-id="e391f-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="e391f-121">Accedere al [portale di Microsoft Azure](https://portal.azure.com) con un account aziendale o scolastico o un account Microsoft personale.</span><span class="sxs-lookup"><span data-stu-id="e391f-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="e391f-122">Se l'account fornisce accesso a più di un tenant, selezionare l'account nell'angolo in alto a destra e impostare la sessione del portale sul tenant Azure Active Directory ( Azure AD) desiderato.</span><span class="sxs-lookup"><span data-stu-id="e391f-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="e391f-123">Nel riquadro sinistro, selezionare il servizio **Azure Active Directory**, quindi selezionare **Registrazioni app \> Nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="e391f-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="e391f-124">Quando viene visualizzata la pagina **Registra un'applicazione**, inserire le informazioni di registrazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e391f-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="e391f-125">**Nome**: immettere un nome applicazione significativo che verrà mostrato agli utenti dell'app.</span><span class="sxs-lookup"><span data-stu-id="e391f-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="e391f-126">**Tipi di account supportati** : seleziona i tipi di account che l'app dovrebbe supportare.</span><span class="sxs-lookup"><span data-stu-id="e391f-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="e391f-127">Tipi di conto supportati</span><span class="sxs-lookup"><span data-stu-id="e391f-127">Supported account types</span></span> | <span data-ttu-id="e391f-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e391f-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="e391f-129">Account solo in questa directory organizzativa</span><span class="sxs-lookup"><span data-stu-id="e391f-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="e391f-130">Selezionare questa opzione se si sta creando un'app line-of-business.</span><span class="sxs-lookup"><span data-stu-id="e391f-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="e391f-131">Questa opzione non è disponibile a meno che non si stia registrando l'app in una directory.</span><span class="sxs-lookup"><span data-stu-id="e391f-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="e391f-132">Questa opzione è mappata a **Solo Azure AD a singolo tenant**.</span><span class="sxs-lookup"><span data-stu-id="e391f-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="e391f-133">Questa opzione è quella predefinita a meno che non si stia registrando l'app al di fuori di una directory.</span><span class="sxs-lookup"><span data-stu-id="e391f-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="e391f-134">In tal caso, l'opzione predefinita è **Azure AD multi-tenant e account Microsoft personali**.</span><span class="sxs-lookup"><span data-stu-id="e391f-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="e391f-135">Account in qualsiasi directory organizzativa</span><span class="sxs-lookup"><span data-stu-id="e391f-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="e391f-136">Selezionare questa opzione per tutti i clienti aziendali ed educativi.</span><span class="sxs-lookup"><span data-stu-id="e391f-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="e391f-137">Questa opzione è mappata a **Solo Azure AD multi-tenant**.</span><span class="sxs-lookup"><span data-stu-id="e391f-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="e391f-138">Se l'app è stata registrata come **Solo Azure AD a singolo tenant**, è possibile usare il pannello **Autenticazione** per aggiornarla a **Solo Azure AD multi-tenant** e poi di nuovo a **Solo Azure ADa singolo tenant**.</span><span class="sxs-lookup"><span data-stu-id="e391f-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="e391f-139">Account in qualsiasi directory organizzativa e account Microsoft personali</span><span class="sxs-lookup"><span data-stu-id="e391f-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="e391f-140">Selezionare questa opzione per il più ampio gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="e391f-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="e391f-141">Questa opzione è mappata **Azure AD multi-tenant e account Microsoft personali**.</span><span class="sxs-lookup"><span data-stu-id="e391f-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="e391f-142">Se l'app è stata registrata come **Azure AD multi-tenant e account Microsoft personali**, non è possibile modificare questa impostazione nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e391f-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="e391f-143">Invece, è necessario utilizzare l'editor del manifesto dell'applicazione per modificare i tipi di account supportati.</span><span class="sxs-lookup"><span data-stu-id="e391f-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="e391f-144">**URI di reindirizzamento (facoltativo)** - Selezionare il tipo di app che si sta creando: **Web** o **Client pubblico (mobile e desktop)**.</span><span class="sxs-lookup"><span data-stu-id="e391f-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="e391f-145">Quindi immettere l'URI di reindirizzamento (o l'URL di risposta) per l'app.</span><span class="sxs-lookup"><span data-stu-id="e391f-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="e391f-146">Per le app Web, fornire l'URL di base dell'app.</span><span class="sxs-lookup"><span data-stu-id="e391f-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="e391f-147">Ad esempio, `http://localhost:31544` potrebbe essere l'URL di un'app Web in esecuzione sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="e391f-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="e391f-148">Gli utenti quindi utilizzano questo URL per accedere a un'app client Web.</span><span class="sxs-lookup"><span data-stu-id="e391f-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="e391f-149">Per le app client pubbliche, fornire l'URI che Azure AD utilizza per restituire risposte token.</span><span class="sxs-lookup"><span data-stu-id="e391f-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="e391f-150">Immettere un valore specifico alla propria app, ad esempio `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="e391f-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="e391f-151">Per vedere esempi specifici di app Web o app native, vedere le guide introduttive in [Piattaforma di identità Microsoft (precedentemente nota come Azure Active Directory per gli sviluppatori)](/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="e391f-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="e391f-152">Sotto **Autorizzazioni API**, selezionare **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="e391f-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="e391f-153">Quindi, nella scheda **API utilizzate dalla mia organizzazione**, cercare **Dynamics 365 Human Resources** e aggiungere l'autorizzazione **user\_impersonation** all'app.</span><span class="sxs-lookup"><span data-stu-id="e391f-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="e391f-154">L'ID applicazione per Human Resources è f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="e391f-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="e391f-155">Utilizzare questo ID per assicurarsi di aver scelto l'applicazione corretta.</span><span class="sxs-lookup"><span data-stu-id="e391f-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="e391f-156">Selezionare **Registro**.</span><span class="sxs-lookup"><span data-stu-id="e391f-156">Select **Register**.</span></span>

   <span data-ttu-id="e391f-157">[![Registrazione di una nuova app nel portale di Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e391f-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="e391f-158">Azure AD assegna un ID applicazione univoco (ID client) all'app e visualizza la pagina **Panoramica** per l'app.</span><span class="sxs-lookup"><span data-stu-id="e391f-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="e391f-159">Per aggiungere più funzionalità all'app, è possibile selezionare altre opzioni di configurazione, come le opzioni per il branding e per i certificati e i segreti.</span><span class="sxs-lookup"><span data-stu-id="e391f-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="e391f-160">Recupero di un token di accesso</span><span class="sxs-lookup"><span data-stu-id="e391f-160">Retrieving an access token</span></span>

<span data-ttu-id="e391f-161">Le specifiche su come recuperare un token di accesso per chiamare l'API dati di Human Resources dipenderanno dalle tecnologie utilizzate per sviluppare l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e391f-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="e391f-162">Ad esempio, si potrebbe eseguire il [testing con un'utilità di terze parti](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (come Postman), lo sviluppo di un'applicazione console C# o di un servizio Web oppure la creazione di un client javascript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="e391f-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="e391f-163">Esempio di applicazione client C#:</span><span class="sxs-lookup"><span data-stu-id="e391f-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="e391f-164">Dopo aver recuperato un token di accesso, lo si passerà all'intestazione di autorizzazione come token di connessione con ogni richiesta inviata all'API dati, come descritto sopra.</span><span class="sxs-lookup"><span data-stu-id="e391f-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]