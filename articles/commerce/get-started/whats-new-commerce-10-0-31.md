---
title: Anteprima di Dynamics 365 Commerce 10.0.31 (febbraio 2023)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 05ccd9794ffeba6a09d6fec0a57ffad2b59707ad
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709859"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Anteprima di Dynamics 365 Commerce 10.0.31 (febbraio 2023)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo elenca le funzionalità nuove o modificate nella versione di anteprima 10.0.31 di Microsoft Dynamics 365 Commerce. Questa versione ha il numero di build 10.0.1406 ed è disponibile con il seguente programma:

- **Anteprima della versione:** ottobre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** gennaio 2023
- **Disponibilità generale della versione (aggiornamento automatico):** febbraio 2023

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---|---|---|---|
| Codici errore | Commerce ha introdotto riferimenti agli errori standardizzati da includere negli errori di checkout dei canali online presentati agli acquirenti online.| [Codici errore del modulo di checkout](../checkout-module-error-codes.md)  | In base all'impostazione predefinita |
| Pagamenti | [Abilitare Apple Pay con Dynamics 365 Payment Connector per Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | I clienti di e-commerce possono utilizzare Apple Pay nel carrello e nelle pagine di checkout quando utilizzano dispositivi o browser supportati. | Consenso esplicito per gli sviluppatori |
| Pagamenti  |  Commerce ha aggiunto la capacità di limitare il modo in cui gli utenti interagiscono con i token di pagamento ricorrenti nell'interfaccia utente di Commerce headquarters. I moduli di pagamento come **Ordini cliente per servizio clienti**, non mostrano più il token di pagamento ricorrente utilizzato in precedenza da un cliente per utilizzarlo in una nuova transazione. Solo un determinato input "carta su file" nella schermata **Pagamenti clienti** in Commerce o in accordo con un cliente durante il pagamento tramite un ordine clientw, verrà presentato agli utenti del call center o di Commerce headquarters durante l'elaborazione di un pagamento per una nuova transazione. | [Limitare l'utilizzo dei token di pagamento](../dev-itpro/limit-token-usage.md)  |  Gestione funzionalità<p>*Limita l'utilizzo del token di pagamento al contesto dell'ordine*  |
| POS | [Creare da ordini fornitore da POS](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  L'operazione migliorata di magazzino in ingresso nell'app POS consente agli utenti di creare, modificare e confermare richieste ordini fornitore. |  Gestione funzionalità<p>*Possibilità di creare una richiesta ordine fornitore nel POS*   |



## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Commerce 10.0.31 include gli aggiornamenti della piattaforma. Per altre informazioni, vedere [Aggiornamenti della piattaforma per la versione 10.0.31 delle app per la finanza e le operazioni (febbraio 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ognuno degli aggiornamenti che fanno parte della versione 10.0.31, accedi a Microsoft Dynamics Lifecycle Services e visualizza l'[articolo della Knowledge Base](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-commerce-features"></a>Funzionalità di Commerce rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrive le funzionalità che sono state rimosse o deprecate per Commerce.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mesi prima della rimozione.


Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
