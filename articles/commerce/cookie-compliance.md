---
title: Conformità cookie
description: Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/21/2021
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
ms.openlocfilehash: 8eb610eb819dee09a30368257e36dc88f855e985
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088389"
---
# <a name="cookie-compliance"></a>Conformità dei cookie

[!include [banner](includes/banner.md)]

Questo argomento descrive le considerazioni sulla conformità dei cookie e i criteri predefiniti inclusi in Microsoft Dynamics 365 Commerce.

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
| \_msdyn365___muid_                            | Utilizzato se Sperimentazione è attivato per l'ambiente; utilizzato come ID utente per scopi di sperimentazione. |
| \_msdyn365___exp_                             | Utilizzato se Sperimentazione è attivato per l'ambiente; utilizzato per misurare il bilanciamento del carico delle prestazioni.         |
| d365mkt                                       | Utilizzato se il rilevamento basato sulla posizione per tenere traccia dell'indirizzo IP di un utente per i suggerimenti sulla posizione del negozio è abilitato nel generatore di siti di Commerce in **Impostazioni sito > Generale > Abilita rilevamento del punto vendita basato sull'ubicazione**.      |

Se un utente del sito seleziona qualsiasi collegamento ai social media in un sito, anche i cookie nella tabella seguente verranno monitorati nel suo browser.


| Dominio                      | Cookie               | descrizione                                                  | Origine                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | Sincronizzazione ID LinkedIn Ads                                      | Feed di LinkedIn e Insight Tag                                |
| .linkedin.com               | li_sugr                  | Identificatore del browser                                           | LinkedIn Insight Tag se l'indirizzo IP non si trova in un paese designato |
| .linkedin.com               | BizographicsOptOut       | Determina lo stato di rifiuto esplicito per il tracciamento di terze parti.              | Controlli dei guest di LinkedIn e pagine di rifiuto esplicito del settore           |
| .linkedin.com               | \_guid                    | Identificatore del browser per Google Ads.                            | Feed di LinkedIn                                                |
| .linkedin.com               | li_oatml                 | Identificatore indiretto dell'utente con finalità di monitoraggio delle conversioni, retargeting e analisi. | LinkedIn Ads e Insight Tag                                |
| Vari domini di prima parte | li_fat_id                | Identificatore indiretto dell'utente con finalità di monitoraggio delle conversioni, retargeting e analisi. | LinkedIn Ads e Insight Tag                                |
| .adsymptotic.com            | U                        | Identificatore del browser                                           | LinkedIn Insight Tag se l'indirizzo IP non si trova in un paese designato |
| .linkedin.com                | bcookie                  | Cookie identificativo del browser                                            | Richieste a LinkedIn                                         |
| .linkedin.com                | bscookie                 | Cookie del browser sicuro                                        | Richieste a LinkedIn                                         |
| .linkedin.com               | lang                     | Definisce le impostazioni locali e la lingua predefinite.                                 | Richieste a LinkedIn                                         |
| .linkedin.com                | lidc                     | Utilizzato per il routing.                                             | Richieste a LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Cookie di Adobe Audience Manager                                                     | Impostato per la sincronizzazione dell'ID                                              |
| .linkedin.com               | \_ga                      | Cookie di Google Analytics                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Cookie di Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Cookie di Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | Il cookie contiene l'ID utente dell'utente attualmente connesso.  |   Facebook                                                           |
| .facebook.com               | datr                     | Utilizzato per identificare il browser Web utilizzato per connettersi a Facebook indipendentemente dall'utente connesso. | Facebook                                                             |
| .facebook.com               | wd                       | Memorizza le dimensioni della finestra del browser e viene utilizzato da Facebook per ottimizzare il rendering della pagina. | Facebook                                                             |
| .facebook.com               | xs                       | Numero a due cifre che rappresenta il numero di sessione. La seconda parte del valore è un segreto di sessione. |  Facebook                                                            |
| .facebook.com               | fr                       | Contiene un browser e un ID utente univoci, utilizzati per pubblicità mirata. |  Facebook                                                            |
| .facebook.com               | sb                       | Usato per migliorare i suggerimenti di amici di Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | Il cookie contiene l'ID utente dell'utente attualmente connesso.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | Il cookie contiene l'ID utente dell'utente attualmente connesso.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | Il cookie contiene pagine quando l'utente seleziona il pulsante Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | Il cookie contiene pagine quando l'utente seleziona il pulsante Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Contiene un ID utente e il timestamp della creazione del cookie. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | Il cookie contiene pagine quando l'utente seleziona il pulsante Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | Il cookie contiene pagine quando l'utente seleziona il pulsante Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Archiviazione locale            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Lavoratori di servizi          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consenso per i cookie dell'utente del sito in un sito di e-commerce 

Se una funzionalità o un modulo del sito di e-commerce utilizza un cookie non essenziale, è necessario ottenere il consenso dell'utente del sito prima che il cookie venga tracciato. Per consentire agli utenti del sito di fornire il consenso per i cookie sul sito di e-commerce, un autore del sito deve aggiungere e configurare un modulo consenso per i cookie nel modulo intestazione della pagina per garantire che il consenso venga richiesto e ricevuto. È necessario fornire il consenso dell'utente del sito prima che una funzionalità o un modulo che utilizza un cookie non essenziale possa essere visualizzato su una pagina del sito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzionalità e capacità di accessibilità](accessibility.md)

[Panoramica sulla conformità](compliance-overview.md)

[Aggiungere una pagina dell'Informativa sulla privacy](add-privacy-page.md)

[Sostituire gli ID utente associati alle modifiche al contenuto monitorato](replace-IDs-tracked-changes.md)

[Modulo consenso per i cookie](cookie-consent-module.md) 
 
[Modulo intestazione](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
