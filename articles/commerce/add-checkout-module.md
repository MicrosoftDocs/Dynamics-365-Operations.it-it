---
title: Modulo Checkout
description: In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025392"
---
# <a name="checkout-module"></a>Modulo Checkout


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.

## <a name="overview"></a>Panoramica

Un modulo Checkout è un contenitore speciale che ospita tutti i moduli necessari per creare un ordine. Presenta un flusso dettagliato che un cliente utilizza per immettere tutte le informazioni pertinenti per effettuare un acquisto. Acquisisce l'indirizzo di spedizione, il metodo di spedizione e le informazioni di fatturazione. Fornisce inoltre un riepilogo dell'ordine e altre informazioni relative a un ordine cliente.

Un modulo Checkout esegue il rendering dei dati in base all'ID carrello. Questo ID carrello viene salvato come cookie del browser. Un ID carrello è necessario per eseguire il rendering delle informazioni del modulo Checkout, ad esempio gli articoli nell'ordine, l'importo totale e gli sconti.

## <a name="checkout-module-properties"></a>Proprietà del modulo Checkout

Un modulo Checkout mostra un riepilogo dell'ordine e fornisce la funzionalità per effettuare un ordine. Per raccogliere tutte le informazioni sul cliente necessarie prima di effettuare un ordine, è necessario aggiungere moduli aggiuntivi al modulo Checkout. Pertanto, i rivenditori hanno la flessibilità di aggiungere moduli personalizzati al flusso di checkout o di escludere moduli, in base alle loro esigenze.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduli che è possibile utilizzare nel modulo Checkout

- **Indirizzo di spedizione** - Questo modulo consente a un cliente di aggiungere o selezionare l'indirizzo di spedizione per un ordine. Se il cliente è connesso, sono visualizzati tutti gli indirizzi salvati in precedenza per tale cliente. Il cliente può quindi scegliere tra questi indirizzi. Il cliente può anche aggiungere un nuovo indirizzo. L'indirizzo di spedizione viene utilizzato per tutti gli articoli nell'ordine che devono essere spediti. Non può essere personalizzato per singoli articoli. I formati dell'indirizzo di spedizione sono definiti per ogni paese e le regole specifiche del paese sono applicate tramite questo modulo. Sebbene questo modulo non fornisca la convalida dell'indirizzo, questa può essere implementata mediante la personalizzazione. Se l'ordine include solo articoli che verranno prelevati nel punto vendita, questo modulo viene automaticamente nascosto.
- **Opzioni di consegna** - Questo modulo consente a un cliente di selezionare un'opzione di consegna per un ordine. Le opzioni di consegna sono basate sull'indirizzo di spedizione. Se l'indirizzo di spedizione viene modificato, le opzioni di consegna devono essere recuperate di nuovo. Se l'ordine include solo articoli che verranno prelevati nel punto vendita, questo modulo viene automaticamente nascosto.
- **Contenitore sezione checkout** - Questo modulo è un contenitore in cui è possibile includere più moduli allo scopo di creare una sezione nel flusso di checkout. Ad esempio, è possibile inserire tutti i moduli relativi al pagamento in tale contenitore per visualizzarli come un'unica sezione. Questo modulo influisce solo sul layout del flusso.
- **Gift card** - Questo modulo consente a un cliente di pagare un ordine utilizzando una gift card. Supporta solo le gift card di Microsoft Dynamics 365 Commerce. Una o più gift card possono essere applicate a un ordine. Se il saldo della gift card non copre l'importo nel carrello, la gift card può essere combinata con un altro metodo di pagamento. Le gift card possono essere utilizzate solo se il cliente è connesso.
- **Punti fedeltà** - Questo modulo consente a un cliente di pagare un ordine utilizzando i punti fedeltà. Fornisce un riepilogo dei punti disponibili e dei punti in scadenza e consente al cliente di selezionare il numero di punti da utilizzare. Se il cliente non è connesso o non è un membro del programma fedeltà, oppure se l'importo totale nel carrello è 0 (zero), questo modulo viene automaticamente nascosto.
- **Pagamento** - Questo modulo consente a un cliente di pagare un ordine utilizzando una carta di credito. Se l'importo totale nel carrello è coperto dai punti fedeltà o da una gift card oppure è 0 (zero), questo modulo viene automaticamente nascosto. L'integrazione di una carta di credito per questo modulo viene fornita dal connettore di pagamento Adyen. Per ulteriori informazioni su come utilizzare questo connettore, vedere [Connettore pagamenti di Dynamics 365 per Adyen](dev-itpro/adyen-connector.md).
- **Indirizzo di fatturazione** - Questo modulo consente a un cliente di immettere le informazioni di fatturazione. Tali informazioni vengono elaborate da Adyen insieme alle informazioni sulla carta di credito, . Questo modulo include un'opzione che consente ai clienti di utilizzare il proprio indirizzo di fatturazione come indirizzo di spedizione.
- **Informazioni contatto** - Questo modulo consente a un cliente di aggiungere o modificare le informazioni di contatto (indirizzo di posta elettronica) per un ordine.
- **Blocco di testo** - Questo modulo contiene qualsiasi messaggio gestito dal sistema di gestione dei contenuti. Ad esempio, potrebbe contenere un messaggio indicante "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam". 

## <a name="commerce-scale-unit-interaction"></a>Interazione con Commerce Scale Unit

La maggior parte delle informazioni di checkout, come l'indirizzo di spedizione e il metodo di spedizione, è archiviata nel carrello ed elaborata nell'ambito dell'ordine. La sola eccezione è costituita dalle informazioni sulla carta di credito. Queste informazioni vengono elaborate direttamente utilizzando il connettore pagamenti Adyen. Il pagamento è autorizzato ma non addebitato.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Aggiungere un modulo Checkout a una nuova pagina e impostare le proprietà necessarie

Per aggiungere un modulo Checkout a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Frammento \> Nuovo frammento** e denominare il nuovo frammento **Frammento check out**.
1. Aggiungere un modulo Checkout al frammento.
1. Aggiungere un'intestazione al modulo Checkout.
1. Aggiungere Indirizzo di spedizione, Opzioni di consegna, Contenitore sezione checkout e Informazioni contatto. 
1. Nella sezione Check out del modulo contenitore, aggiungere i moduli Gift card, Punti fedeltà e Pagamento. In questo modo, si garantisce la visualizzazione di tutti i metodi di pagamento in un'unica sezione.
1. Salvare il frammento e visualizzarne l'anteprima. È possibile che l'anteprima di alcuni moduli che non hanno un contesto carrello non sia visualizzata.
1. Completare la modifica del frammento e pubblicarlo.
1. Creare un modello che utilizza il nuovo frammento checkout.
1. Creare una pagina checkout che utilizza il nuovo modello.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica starter kit](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Casella acquisti](add-buy-box.md)

[Modulo Carrello](add-cart-module.md)

[Modulo Conferma ordine](order-confirmation-module.md)

[Modulo Intestazione](author-header-module.md)

[Modulo Piè di pagina](author-footer-module.md)
