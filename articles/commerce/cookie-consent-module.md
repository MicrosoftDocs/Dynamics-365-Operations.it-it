---
title: Modulo consenso per i cookie
description: In questo argomento vengono descritti i moduli consenso per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 43f18a0963d84d486c8077bde1dad50fdd4fe85beb95dc8b22ae2f3ee724ba0f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750740"
---
# <a name="cookie-consent-module"></a>Modulo di consenso sui cookie

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli consenso per i cookie e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Il modulo consenso per i cookie richiede agli utenti del sito di fornire esplicitamente il consenso per consentire i cookie per qualsiasi funzionalità o modulo che tiene traccia dei cookie del browser. Il consenso è richiesto la prima volta che un utente del sito apre un sito in una nuova sessione del browser. Una volta ricevuto il consenso, viene tracciato e all'utente del sito non verrà chiesto nuovamente il consenso. Per ulteriori informazioni vedere [Conformità dei cookie](cookie-compliance.md).

Se non si riceve il consenso per i cookie dell'utente del sito, eventuali funzionalità o moduli che richiedono il consenso per i cookie non verranno visualizzati nella pagina. Ad esempio, il modulo checkout, il modulo condivisione social e la funzione di negozio preferito richiedono tutti il consenso dei cookie e non verranno visualizzati se non viene ricevuto il consenso dell'utente del sito. 

Un modulo consenso per i cookie può essere configurato nel frammento di intestazione della pagina in modo che possa essere applicato al caricamento della pagina. Il modulo consenso per i cookie deve includere un messaggio chiaro che informa l'utente del sito sull'utilizzo dei cookie nel sito e fornire un collegamento alla pagina sulla privacy del sito.

La figura seguente evidenzia un esempio di messaggio di consenso per i cookie con un collegamento alla pagina dell'informativa sulla privacy del sito visualizzata nell'intestazione di una pagina del sito.
![Esempio di un modulo consenso per i cookie.](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Proprietà del modulo consenso per i cookie

| Nome proprietà             | Valore                 | descrizione |
|---------------------------|-----------------------|-------------|
| RTF                  | RTF | Specifica una notifica RTF per gli utenti del sito indicante che il sito utilizza i cookie del browser e che gli utenti devono accettare l'uso dei cookie affinché il sito sia completamente funzionale. |
| Collegamenti | URL | È possibile aggiungere uno o più collegamenti alla pagina sulla privacy di un sito che descrive i tipi di cookie tracciati nel sito. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Aggiungere un modulo consenso per i cookie alle pagine del sito

Per aggiungere in modo efficiente un modulo consenso per i cookie a più pagine del sito, è possibile aggiungerlo a un frammento di intestazione di pagina condivisa. Dopo che il frammento di intestazione è stato aggiunto a tutte le pagine del sito, verrà automaticamente visualizzata una notifica di consenso per i cookie la prima volta che un utente del sito accede a qualsiasi pagina del sito.

Per ulteriori informazioni sui frammenti di intestazione e sui moduli, vedere [Modulo intestazione](author-header-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo intestazione](author-header-module.md) 

[Conformità dei cookie](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]