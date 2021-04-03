---
title: Autenticazione
description: Questo articolo fornisce informazioni generali su come eseguire l'autenticazione con l'API (Application Programming Interface) di Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 60774d162d733404166e710932291a736eb0d8b4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465536"
---
# <a name="authentication"></a>Autenticazione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo fornisce informazioni generali su come eseguire l'autenticazione con l'API (Application Programming Interface) di Microsoft Dynamics 365 Human Resources.

## <a name="overview"></a>Panoramica

L'API dati per Human Resources è un'implementazione OData. Per ulteriori informazioni, vedere [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

L'applicazione in uso deve autenticarsi come chiamante autorizzato prima che l'API gestisca le richieste dall'applicazione.

## <a name="fundamentals"></a>Elementi fondamentali

Per chiamare l'API dati, l'applicazione deve acquisire un token di accesso dalla piattaforma di identità Microsoft. Il token di accesso contiene informazioni sull'applicazione e l'autorizzazione che deve chiamare le risorse in Human Resources.

### <a name="access-token"></a>Token di accesso

I token di accesso emessi dalla piattaforma di identità Microsoft sono token Web JSON (JavaScript Object Notation) con codifica base64. Contengono informazioni (attestazioni) che l'API dati (e altre API Web protette dalla piattaforma di identità Microsoft) utilizzano per convalidare il chiamante e assicurarsi che questi disponga delle autorizzazioni corrette per eseguire l'operazione richiesta. Durante le chiamate, è possibile considerare i token di accesso come opachi. Bisogna sempre trasmettere i token di accesso su un canale sicuro, come Transport Layer Security (TLS) e Hypertext Transfer Protocol Secure (HTTPS).

Di seguito è riportato un esempio di token di accesso emesso dalla piattaforma di identità Microsoft.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Per chiamare l'API dati, si allega il token di accesso come token di connessione all'intestazione di autorizzazione nella richiesta HTTP. Ecco un esempio.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Registrare una nuova applicazione mediante il portale di Azure

1. Accedere al [portale di Microsoft Azure](https://portal.azure.com) con un account aziendale o scolastico o un account Microsoft personale.

2. Se l'account fornisce accesso a più di un tenant, selezionare l'account nell'angolo in alto a destra e impostare la sessione del portale sul tenant Azure Active Directory ( Azure AD) desiderato.

3. Nel riquadro sinistro, selezionare il servizio **Azure Active Directory**, quindi selezionare **Registrazioni app \> Nuova registrazione**.

4. Quando viene visualizzata la pagina **Registra un'applicazione**, inserire le informazioni di registrazione dell'applicazione:

    - **Nome**: immettere un nome applicazione significativo che verrà mostrato agli utenti dell'app.
    - **Tipi di account supportati** : seleziona i tipi di account che l'app dovrebbe supportare.

        | Tipi di conto supportati | Descrizione |
        |-------------------------|-------------|
        | Account solo in questa directory organizzativa | Selezionare questa opzione se si sta creando un'app line-of-business. Questa opzione non è disponibile a meno che non si stia registrando l'app in una directory.<p>Questa opzione è mappata a **Solo Azure AD a singolo tenant**.</p><p>Questa opzione è quella predefinita a meno che non si stia registrando l'app al di fuori di una directory. In tal caso, l'opzione predefinita è **Azure AD multi-tenant e account Microsoft personali**.</p> |
        | Account in qualsiasi directory organizzativa | Selezionare questa opzione per tutti i clienti aziendali ed educativi.<p>Questa opzione è mappata a **Solo Azure AD multi-tenant**.</p><p>Se l'app è stata registrata come **Solo Azure AD a singolo tenant**, è possibile usare il pannello **Autenticazione** per aggiornarla a **Solo Azure AD multi-tenant** e poi di nuovo a **Solo Azure ADa singolo tenant**.</p> |
        | Account in qualsiasi directory organizzativa e account Microsoft personali | Selezionare questa opzione per il più ampio gruppo di clienti.<p>Questa opzione è mappata **Azure AD multi-tenant e account Microsoft personali**.</p><p>Se l'app è stata registrata come **Azure AD multi-tenant e account Microsoft personali**, non è possibile modificare questa impostazione nell'interfaccia utente. Invece, è necessario utilizzare l'editor del manifesto dell'applicazione per modificare i tipi di account supportati.</p> |

    - **URI di reindirizzamento (facoltativo)** - Selezionare il tipo di app che si sta creando: **Web** o **Client pubblico (mobile e desktop)**. Quindi immettere l'URI di reindirizzamento (o l'URL di risposta) per l'app.

        - Per le app Web, fornire l'URL di base dell'app. Ad esempio, `http://localhost:31544` potrebbe essere l'URL di un'app Web in esecuzione sul computer locale. Gli utenti quindi utilizzano questo URL per accedere a un'app client Web.
        - Per le app client pubbliche, fornire l'URI che Azure AD utilizza per restituire risposte token. Immettere un valore specifico alla propria app, ad esempio `myapp://auth`.

        Per vedere esempi specifici di app Web o app native, vedere le guide introduttive in [Piattaforma di identità Microsoft (precedentemente nota come Azure Active Directory per gli sviluppatori)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).

5. Sotto **Autorizzazioni API**, selezionare **Aggiungi un'autorizzazione**. Quindi, nella scheda **API utilizzate dalla mia organizzazione**, cercare **Dynamics 365 Human Resources** e aggiungere l'autorizzazione **user\_impersonation** all'app. L'ID applicazione per Human Resources è f9be0c49-aa22-4ec6-911a-c5da515226ff. Utilizzare questo ID per assicurarsi di aver scelto l'applicazione corretta.

6. Selezionare **Registro**.

   [![Registrazione di una nuova app nel portale di Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD assegna un ID applicazione univoco (ID client) all'app e visualizza la pagina **Panoramica** per l'app. Per aggiungere più funzionalità all'app, è possibile selezionare altre opzioni di configurazione, come le opzioni per il branding e per i certificati e i segreti.

## <a name="retrieving-an-access-token"></a>Recupero di un token di accesso

Le specifiche su come recuperare un token di accesso per chiamare l'API dati di Human Resources dipenderanno dalle tecnologie utilizzate per sviluppare l'applicazione client. Ad esempio, si potrebbe eseguire il [testing con un'utilità di terze parti](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (come Postman), lo sviluppo di un'applicazione console C# o di un servizio Web oppure la creazione di un client javascript/TypeScript.

Esempio di applicazione client C#:
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

Dopo aver recuperato un token di accesso, lo si passerà all'intestazione di autorizzazione come token di connessione con ogni richiesta inviata all'API dati, come descritto sopra.


[!INCLUDE[footer-include](../includes/footer-banner.md)]