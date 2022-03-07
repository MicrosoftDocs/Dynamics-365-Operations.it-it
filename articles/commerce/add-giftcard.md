---
title: Modulo Gift card
description: Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5a4aaf8e072f6547fe1dcf6fa156d2e144fd03ed806a2dc809a2cedb991461f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728341"
---
# <a name="gift-card-module"></a>Modulo gift card

[!include [banner](includes/banner.md)]

Questo argomento tratta i moduli Gift card e descrive come aggiungerli alle pagine del sito in Microsoft Dynamics 365 Commerce.

I moduli di gift card possono essere utilizzati nei moduli di pagamento per accettare gift card, una forma di pagamento comune utilizzata per le transazioni di e-commerce. Il moduli Gift card supporta gift card Dynamics 365, SVS e Givex. Le gift card SVS e Givex vengono riscattate tramite il fornitore di pagamenti Adyen. Per ulteriori informazioni sul supporto per gift card esterne come SVS e Givex, vedere [Supporto per gift card esterne](./dev-itpro/gift-card.md).

> [!NOTE]
> Il supporto per il riscatto di gift card SVS e Givex durante il flusso di completamento della transazione è disponibile in Dynamics 365 Commerce versione 10.0.11. 

Sono disponibili due moduli di gift card:

- **Gift card** - Questo modulo può essere utilizzato in una pagina di checkout per riscattare una gift card come offerta. 
- **Controllo del saldo della gift card** - Questo modulo può essere utilizzato in qualsiasi pagina per controllare il saldo di una gift card. Questo modulo è disponibile in Commerce versione 10.0.14 e successive.

> [!NOTE]
> Il supporto per il modulo di controllo del saldo della gift card regalo è disponibile in Dynamics 365 Commerce versione 10.0.14.

L'immagine seguente mostra un esempio di un moduli Gift card in una pagina checkout.

![Esempio di un modulo Gift card.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Proprietà del modulo

- **Mostra campi aggiuntivi** - Questa proprietà definisce quali campi devono essere visualizzati per le gift card oltre al numero della gift card, che viene sempre visualizzato per impostazione predefinita. Ad esempio, alcune gift card supportano la visualizzazione di un numero di identificazione personale (PIN) e altre supportano la visualizzazione di un PIN e la data di scadenza. In alternativa, questa proprietà può essere impostata su "Nessuno", che visualizza solo il numero della gift card e nessun campo aggiuntivo.

    Sono supportati i valori seguenti:

    - PIN
    - Data di scadenza
    - PIN e Data di scadenza 
    - Nessuna priorità

- **Abilita per utenti guest**: quando questa proprietà è abilitata, gli utenti guest possono riscattare o controllare i saldi delle gift card. Questa proprietà richiede l'abilitazione dell'accesso anonimo (guest) per gift card in Commerce. Per ulteriori informazioni, vedi [Abilitare i pagamenti con gift card per il checkout come guest](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> La proprietà **Abilita per utenti guest** è disponibile a partire dalla versione 10.0.21 di Commerce. Richiede l'installazione del pacchetto della libreria di moduli di Commerce versione 9.31.

## <a name="site-settings-for-gift-card-modules"></a>Impostazioni del sito per i moduli Gift card

In Creazione di siti Web di Commerce sotto **Impostazioni del sito \> Estensioni**, è disponibile un'impostazione del moduli Gift card chiamata **Tipo di gift card supportato**. Questa impostazione supporta tre valori:
- **Gift card Dynamics 365** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Dynamics 365. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card SVS e gift card Givex** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Givex e SVS. Questa impostazione è supportata per gli utenti anonimi che hanno effettuato l'accesso al sito di e-Commerce.
- **Gift card Dynamics 365, SVS e Givex** - Quando si applica questa impostazione, il modulo Gift card consente solo il riscatto di gift card Dynamics 365, SVS e Givex. Questa impostazione è supportata solo per gli utenti che hanno effettuato l'accesso al sito di e-Commerce.

> [!IMPORTANT]
> Queste impostazioni sono disponibili in Dynamics 365 Commerce versione 10.0.11 e sono richiesti solo se è necessario il supporto per le gift card SVS o Givex. Se stai aggiornando da una versione precedente di Dynamics 365 Commerce, devi aggiornare manualmente il file appsettings.json. Per istruzioni sull'aggiornamento del file appsettings.json, vedi [Aggiornamenti dell'SDK e della libreria dei moduli](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Estendere le gift card interne per l'uso in punti vendita e-commerce

Per impostazione predefinita, le gift card interni non sono ottimizzati per l'utilizzo in punti vendita di e-commerce. Pertanto, prima di consentire l'utilizzo delle gift card interne per il pagamento, è necessario configurarle con estensioni che contribuiscano a renderle più sicure. Di seguito sono riportate le aree delle  gift card che dovresti estendere prima di consentire l'utilizzo delle  gift card interne nella produzione:

- **Numero della  gift card** - Le sequenze numeriche vengono utilizzate per generare numeri di  gift card per  gift card interne. Poiché le sequenze numeriche possono essere facilmente previste, è necessario estendere la generazione di numeri di gift card in modo che vengano utilizzate stringhe casuali e crittograficamente sicure per i numeri di  gift card emesse.
- **GetBalance** - L'API **GetBalance** viene utilizzata per cercare i saldi delle  gift card. Per impostazione predefinita, l'API è pubblica. Se non è necessario un PIN per cercare i saldi delle gift card, c'è il rischio che attacchi di forza bruta possano utilizzare l'API **GetBalance** per tentare di cercare i numeri delle gift card che hanno saldi. Implementando sia i requisiti del PIN per  gift card interni sia la limitazione dell'API, puoi contribuire a mitigare il rischio.
- **PIN** - Per impostazione predefinita, le  gift card interne non supportano i PIN. È necessario estendere le gift card interni in modo che sia necessario un PIN per cercare i saldi. Questa funzionalità può essere utilizzata anche per bloccare le gift card dopo tentativi errati consecutivi di inserire il PIN.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Abilitare i pagamenti con gift card per il checkout come guest

Per impostazione predefinita, i pagamenti con gift card non sono abilitati per il checkout come guest (anonimo). Per abilitarli, attenersi alla procedura seguente.

1. In Commerce Headquarters vai a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> POS \> Operazioni POS**.
1. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) l'intestazione della griglia, quindi seleziona **Inserisci colonne**.
1. Nella finestra di dialogo **Inserisci colonne** selezionare la casella di controllo **AllowAnonymousAccess**.
1. Selezionare **Aggiornamento**.
1. Per le operazioni **520** (Saldo goft card) e **214**, impostare il valore **AllowAnonymousAccess** su **1**.
1. Selezionare **Salva**.
1. Eseguire il processo Retail Scheduler **1090** per sincronizzare le modifiche nel database del canale. 

## <a name="add-a-gift-card-module-to-a-page"></a>Aggiungere un moduli Gift card a una pagina

Per istruzioni su come aggiungere un moduli Gift card a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Supporto per gift card esterne](./dev-itpro/gift-card.md)

[SDK e aggiornamenti libreria dei moduli](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
