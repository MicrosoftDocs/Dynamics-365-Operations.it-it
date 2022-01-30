---
title: Panoramica del sito di e-commerce
description: Questo argomento fornisce una panoramica del supporto per i siti di e-commerce in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c7f679e8d11b0ec01e912a4ad64f02e50b20f299
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984571"
---
# <a name="e-commerce-site-overview"></a>Panoramica del sito di e-commerce

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica del supporto per i siti di e-commerce in Microsoft Dynamics 365 Commerce. Include informazioni su come vengono inizializzati e gestiti i punti vendita online di e-commerce in Dynamics 365 Commerce. Fornisce inoltre i collegamenti a ulteriori informazioni sui negozi online e informazioni su come impostare e configurare un sito di e-commerce. Sebbene questo argomento copra molti concetti di base, non tratta tutto ciò che è necessario per impostare un sito di e-commerce di produzione. Argomenti più avanzati possono essere trovati nella documentazione di Dynamics 365 Commerce.

## <a name="online-store-channel"></a>Canale punto vendita online

Prima di poter creare un sito in Dynamics 365 Commerce, deve essere impostato almeno un canale punto vendita online. Per ulteriori informazioni, vedere [Impostare un canale online](channel-setup-online.md). 

In Dynamics 365 Commerce, si utilizza un canale punto vendita online per stabilire i prodotti, i prezzi, le lingue, i metodi di pagamento, le modalità di consegna, i centri di evasione e altri aspetti dell'esperienza online che devono essere disponibili per i clienti.

Solo un canale punto vendita online deve essere impostato prima di poter iniziare a usare Dynamics 365 Commerce. Tuttavia, un singolo sito e-commerce può fornire l'esperienza online per più negozi online. Ad esempio, se più negozi online sono impostati per supportare diverse aree geografiche, è possibile utilizzare un singolo set di pagine e-commerce per fornire le esperienze uniche definite da ciascun negozio. Per ulteriori informazioni su come configurare un sito per supportare più negozi online, vedere [Associare un sito online a un canale](associate-site-online-store.md).

Dopo aver configurato un negozio online, può essere associato al sito Dynamics 365 Commerce che fungerà da vetrina online. Per ulteriori informazioni sui negozi online e su come configurarli, vedere [Impostare i negozi online](/dynamics365/unified-operations/retail/online-stores).

## <a name="deploy-a-new-e-commerce-tenant"></a>Distribuire un nuovo tenant di e-commerce

Durante l'inizializzazione di un sito di e-commerce, viene richiesto un nome di dominio. Per ulteriori informazioni sui domini in Commerce, vedere [Configurare il nome di dominio](configure-your-domain-name.md) e [Domini in Dynamics 365 Commerce](domains-commerce.md). Per distribuire un nuovo tenant di e-commerce utilizzando [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide), seguire i passaggi in [Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md). Dopo che il tenant e-commerce è stato impostato in LCS, verrà fornito un collegamento al generatore di siti di Commerce. È quindi possibile utilizzare il generatore di siti di Commerce per inizializzare e configurare i siti di e-commerce.

## <a name="initialize-your-e-commerce-site"></a>Inizializzare il sito e-commerce

Quando si avvia il generatore di siti Commerce da LCS, la pagina **Siti** viene visualizzata. Questa pagina include due siti preconfigurati, **predefinito** e **fabrikam**, come mostrato nell'esempio nella figura seguente.

![Pagina Siti nel generatore di siti di Commerce.](media/e-commerce-site-01.png)

Quando si seleziona uno di questi siti, viene chiesto di selezionare un nome di dominio, un canale punto vendita online predefinito, una lingua supportata per il canale selezionato e un percorso. Se viene utilizzato un solo canale, è possibile lasciare vuoto il percorso. Più lingue o canali punto vendita online possono essere configurati in un secondo momento nel generatore di siti di Commerce. Ogni canale o lingua aggiuntivo richiederà un percorso univoco. Ad esempio, sono disponibili due canali online associati a un singolo sito e il nome di dominio del sito è `www.fabrikam.com`. In questo caso, il percorso per un canale può essere il valore predefinito che non ha percorso (`https://www.fabrikam.com`) e il secondo canale può essere impostato su un nuovo percorso, ad esempio **site2**, che avrà l'URL `https://www.fabrikam.com/site2`. La figura seguente mostra un esempio di una finestra di dialogo di inizializzazione del sito nel generatore di siti di Commerce.

![Finestra di dialogo di inizializzazione del sito nel generatore di siti di Commerce.](media/e-commerce-site-02.png)

La pagina **Siti** include anche un pulsante **Nuovo sito**. La finestra di dialogo che appare quando si seleziona questo pulsante è simile alla finestra di dialogo di inizializzazione del sito, ma viene utilizzata per creare un nuovo sito. I nuovi siti sono vuoti. Non includono gli stessi modelli, frammenti, pagine e immagini predefiniti forniti con i siti **predefinito** e **fabrikam**. Tuttavia, se necessario, è possibile aprire un ticket di supporto per richiedere che una copia del contenuto predefinito venga aggiunta a un nuovo sito vuoto. Per ulteriori informazioni, vedere [Creare un sito di e-commerce](create-ecommerce-site.md).

Dopo che un nuovo sito è stato inizializzato, viene visualizzata la pagina **Home** del generatore del sito di Commerce. Questa pagina include i collegamenti ad azioni comuni e contenuti della guida, come mostrato nell'esempio nella figura seguente.

![Collegamenti nella home page nel generatore di siti di Commerce.](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Modificare i canali punto vendita online o aggiungere canali punto vendita online a un sito di e-commerce

Dopo aver creato un sito di e-commerce, è possibile cambiare il canale a cui è associato seguendo i passaggi in [Associare un sito di e-commerce a un canale online](associate-site-online-store.md). L'esempio nella figura seguente mostra come modificare un numero di unità operativa del canale (OUN) nella pagina **Canali** (**Impostazioni del sito \> Canali**). Dopo aver finito di apportare la modifica, assicurarsi di selezionare **Salva e pubblica**. In questo modo, ci si assicura che la modifica venga pubblicata.

![Pagina Canali nel generatore di siti di Commerce.](media/e-commerce-site-04.png)

È possibile aggiungere nuovi canali selezionando **Aggiungi un canale**. Per aggiungere nuove lingue a un canale, selezionare il canale, quindi selezionare **Aggiungi impostazioni locali** nella finestra di dialogo del canale che appare. Prima che le impostazioni locali possano essere visualizzate nella finestra di dialogo, devono essere preconfigurate per il canale punto vendita online in Commerce headquarters.

![Finestra di dialogo Canale nel generatore di siti di Commerce.](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Configurare un tenant di Azure B2C

Dynamics 365 Commerce utilizza Azure Active Directory (Azure AD) business-to-consumer (B2C) per supportare le credenziali dell'utente e i flussi di autenticazione. Per informazioni su come configurare il tenant di Azure B2C, vedere [Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md), [Impostare pagine personalizzate per gli accessi degli utenti](custom-pages-user-logins.md) e [Configurare più tenant B2C in un ambiente Commerce](configure-multi-b2c-tenants.md).

## <a name="overview-of-the-default-site-pages"></a>Panoramica delle pagine del sito predefinite

I siti **predefinito** e **fabrikam** includono modelli, frammenti e pagine preconfigurati per aiutare a iniziare. Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Panoramica della home page](quick-tour-home-page.md)
- [Panoramica della pagina dei dettagli del prodotto](quick-tour-pdp.md)
- [Panoramica delle pagine di checkout e del carrello](quick-tour-cart-checkout.md)
- [Panoramica delle pagine di gestione del conto](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Gestire le impostazioni del sito

Per ulteriori informazioni su come gestire le impostazioni del sito vedere gli argomenti elencati di seguito.

- [Gestire utenti e ruoli di e-commerce](manage-ecommerce-users-roles.md)
- [Considerazioni SEO (ottimizzazione del motore di ricerca) per il proprio sito](/search-engine-optimization-considerations.md)
- [Gestire i criteri di sicurezza del contenuto (CSP)](manage-csp.md)
- [Selezionare un tema per il sito](select-site-theme.md)

## <a name="manage-site-content"></a>Gestire il contenuto del sito

Per ulteriori informazioni su come gestire il contenuto del sito vedere gli argomenti elencati di seguito.

- [Glossario del modello di pagina](page-elements-overview.md)
- [Stato e ciclo di vita documento](document-states-overview.md)
- [Modelli e layout](templates-layouts-overview.md)
- [Utilizzare i frammenti](work-with-fragments.md)
- [Utilizzare i moduli](work-with-modules.md)
- [Panoramica della gestione cespiti digitali](dam-overview.md)
- [Panoramica della libreria moduli](starter-kit-overview.md)

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]