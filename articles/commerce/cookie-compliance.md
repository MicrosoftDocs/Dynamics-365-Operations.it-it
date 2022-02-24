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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413356"
---
# <a name="cookie-compliance"></a>Conformità cookie

[!include [banner](includes/banner.md)]

Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La privacy è un fattore importante quando vengono utilizzate tecnologie di tracciabilità che interessano i clienti di e-Commerce. A causa degli standard di conformità della privacy come il Regolamento generale sulla protezione dei dati (GDPR) nell'Unione Europea (UE), le linee guida elettroniche sulla privacy devono essere prese in considerazione per qualsiasi sito che attivo oggi. Poiché molti siti di e-Commerce sono accessibili a livello globale per impostazione predefinita, è importante rivedere gli standard di conformità per il proprio sito di e-Commerce.

Per ulteriori informazioni sui principi di base utilizzati da Microsoft per la conformità dei cookie, visitare il [Centro di protezione di Microsoft ](https://www.microsoft.com/trust-center). Su questo sito, puoi anche ottenere ulteriori informazioni sulle aree di conformità e della privacy.

La seguente tabella mostra l'attuale elenco di riferimento dei cookie inseriti dai siti Dynamics 365 Commerce.

| Nome del cookie                               | Uso                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Archivia cookie di autenticazione Microsoft Azure Active Directory (Azure AD) per Single Sign-On (SSO). Archivia le informazioni principali dell'utente crittografate (nome, cognome, e-mail). |
| &#95;msdyn365___cart&#95;                           | Archivia l'ID carrello utilizzato per ottenere un elenco di prodotti aggiunti all'istanza del carrello. |
| &#95;msdyn365___ucc&#95;                            | Tracciamento del consenso per la conformità dei cookie.                          |
| ai_session                                  | Rileva quante sessioni di attività dell'utente hanno incluso determinate pagine e funzionalità dell'app. |
| ai_user                                     | Rileva quante persone hanno utilizzato l'app e le sue funzionalità. Gli utenti vengono conteggiati utilizzando ID anonimi. |
| b2cru                                       | Archivia l'URL di reindirizzamento in modo dinamico.                              |
| JSESSIONID                                  | Utilizzato dal connettore di pagamento Adyen per archiviare la sessione utente.       |
| OpenIdConnect.nonce.&#42;                       | Autenticazione                                               |
| x-ms-cpim-cache:.&#42;                          | Utilizzato per mantenere lo stato della richiesta.                      |
| x-ms-cpim-csrf                              | Token CRSF (cross-site request forgery) utilizzato per la protezione da CRSF.     |
| x-ms-cpim-dc                                | Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata. |
| x-ms-cpim-rc.&#42;                              | Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata. |
| x-ms-cpim-slice                             | Utilizzato per instradare le richieste all'istanza del server di autenticazione di produzione appropriata. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Utilizzato per mantenere la sessione SSO.                        |
| x-ms-cpim-trans                             | Utilizzato per tenere traccia delle transazioni (il numero di schede aperte autenticate rispetto a un sito business-to-consumer (B2C)), inclusa la transazione corrente. |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consenso per i cookie dell'utente del sito in un sito di e-commerce 

Se una funzionalità o un modulo del sito di e-commerce utilizza un cookie non essenziale, è necessario ottenere il consenso dell'utente del sito prima che il cookie venga tracciato. Per consentire agli utenti del sito di fornire il consenso per i cookie sul sito di e-commerce, un autore del sito deve aggiungere e configurare un modulo consenso per i cookie nel modulo intestazione della pagina per garantire che il consenso venga richiesto e ricevuto. È necessario fornire il consenso dell'utente del sito prima che una funzionalità o un modulo che utilizza un cookie non essenziale possa essere visualizzato su una pagina del sito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzionalità e capacità di accessibilità](accessibility.md)

[Panoramica sulla conformità](compliance-overview.md)

[Aggiungere una pagina dell'Informativa sulla privacy](add-privacy-page.md)

[Sostituire gli ID utente associati alle modifiche al contenuto monitorato](replace-IDs-tracked-changes.md)

[Modulo consenso per i cookie](cookie-consent-module.md) 
 
[Modulo intestazione](author-header-module.md)
