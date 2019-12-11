---
title: Modulo Checkout
description: In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697085"
---
# <a name="checkout-module"></a>Modulo Checkout

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come aggiungere un modulo Checkout a una pagina e impostare le proprietà necessarie.

## <a name="overview"></a>Panoramica

Un modulo Checkout è un contenitore speciale che ospita tutti i moduli necessari per creare un ordine. Un modulo Checkout può includere moduli che gestiscono l'indirizzo di spedizione, i metodi di spedizione, le informazioni di fatturazione, il riepilogo dell'ordine e altre informazioni correlate a un ordine cliente. Presenta un flusso dettagliato che un cliente utilizza per immettere tutte le informazioni pertinenti per effettuare un acquisto.

Un modulo Checkout esegue il rendering dei dati in base all'ID carrello. Questo ID carrello viene salvato come cookie del browser. Un ID carrello è necessario per eseguire il rendering delle informazioni del modulo Checkout, ad esempio gli articoli nell'ordine, l'importo totale e gli sconti.

## <a name="checkout-module-properties"></a>Proprietà del modulo Checkout

Un modulo Checkout include un set di moduli. Una proprietà larghezza consente di specificare se gli elementi nel modulo Checkout devono essere limitati alla larghezza del modulo oppure visualizzati a schermo intero.

Un modulo Checkout include molteplici slot, ad esempio uno slot **Informazioni checkout**, uno slot **Riepilogo ordine** e un slot **Effettua ordine**. Ogni slot supporta un set di moduli che sono visualizzati in uno specifico layout nella pagina. Ad esempio, lo slot **Informazioni checkout** contiene tutti i moduli necessari per attivare un checkout, ad esempio i moduli per l'indirizzo di spedizione e il metodo di pagamento. Lo slot **Riepilogo ordine** mostra il riepilogo di un ordine e supporta l'azione di esecuzione dell'ordine. Anche lo slot **Effettua ordine** supporta l'azione di esecuzione dell'ordine. I moduli per effettuare gli ordini possono essere definiti in due slot per ottimizzare il processo di esecuzione di ordini da varie piattaforme.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Moduli che è possibile utilizzare nel modulo Checkout

- **Indirizzo di spedizione** - Questo modulo consente a un cliente di aggiungere o selezionare l'indirizzo di spedizione per un ordine. Se il cliente è connesso, sono visualizzati tutti gli indirizzi salvati in precedenza per tale cliente. Il cliente può quindi scegliere tra questi indirizzi. Il cliente può anche aggiungere un nuovo indirizzo. L'indirizzo di spedizione viene utilizzato per tutti gli articoli nell'ordine che devono essere spediti. Non può essere personalizzato per singoli articoli. I formati dell'indirizzo di spedizione sono definiti per ogni paese e le regole specifiche del paese sono applicate tramite questo modulo. Sebbene questo modulo non fornisca la convalida dell'indirizzo, questa può essere implementata mediante la personalizzazione. Se l'ordine include solo articoli che verranno prelevati nel punto vendita, questo modulo viene automaticamente nascosto.
- **Opzioni di consegna** - Questo modulo consente a un cliente di selezionare un'opzione di consegna per un ordine. Le opzioni di consegna sono basate sull'indirizzo di spedizione. Se l'indirizzo di spedizione viene modificato, le opzioni di consegna devono essere recuperate di nuovo. Se l'ordine include solo articoli che verranno prelevati nel punto vendita, questo modulo viene automaticamente nascosto.
- **Contenitore sezione checkout** - Questo modulo è un contenitore in cui è possibile includere più moduli allo scopo di creare una sezione nel flusso di checkout. Ad esempio, è possibile inserire tutti i moduli relativi al pagamento in tale contenitore per visualizzarli come un'unica sezione. Questo modulo influisce solo sul layout del flusso.
- **Gift card** - Questo modulo consente a un cliente di pagare un ordine utilizzando una gift card. Supporta solo le gift card di Microsoft Dynamics 365 Commerce. Una o più gift card possono essere applicate a un ordine. Se il saldo della gift card non copre l'importo nel carrello, la gift card può essere combinata con un altro metodo di pagamento. Le gift card possono essere utilizzate solo se il cliente è connesso.
- **Punti fedeltà** - Questo modulo consente a un cliente di pagare un ordine utilizzando i punti fedeltà. Fornisce un riepilogo dei punti disponibili e dei punti in scadenza e consente al cliente di selezionare il numero di punti da utilizzare. Se il cliente non è connesso o non è un membro del programma fedeltà, oppure se l'importo totale nel carrello è 0 (zero), questo modulo viene automaticamente nascosto.
- **Carta di credito** - Questo modulo consente a un cliente di pagare un ordine utilizzando una carta di credito. Se l'importo totale nel carrello è coperto dai punti fedeltà o da una gift card oppure è 0 (zero), questo modulo viene automaticamente nascosto. L'integrazione di una carta di credito viene fornita dal connettore di pagamento Adyen. Per ulteriori informazioni su come utilizzare questo connettore, vedere [Connettore pagamenti Ayden](https://).
- **Indirizzo di fatturazione** - Questo modulo consente a un cliente di immettere le informazioni di fatturazione. Tali informazioni vengono elaborate da Adyen insieme alle informazioni sulla carta di credito, . Questo modulo include un'opzione che consente ai clienti di utilizzare il proprio indirizzo di fatturazione come indirizzo di spedizione.
- **Informazioni contatto** - Questo modulo consente a un cliente di aggiungere o modificare le informazioni di contatto (indirizzo di posta elettronica) per un ordine.
- **Effettua ordine** - Questo modulo consente a un cliente di effettuare un ordine.
- **Blocco ricco di contenuti** - Questo modulo contiene qualsiasi messaggio gestito dal sistema di gestione dei contenuti. Ad esempio, potrebbe contenere un messaggio indicante "Per problemi relativi all'ordine, contattare il numero verde di Fabrikam". 
- **Riepilogo ordine** - Questo modulo visualizza la scomposizione dei costi di un ordine.
- **Voci ordine** - Questo modulo visualizza un riepilogo degli articoli che verranno inclusi in un ordine.

## <a name="retail-server-interaction"></a>Interazione con Retail Server

La maggior parte delle informazioni di checkout, come l'indirizzo di spedizione e il metodo di spedizione, è archiviata nel carrello ed elaborata nell'ambito dell'ordine. La sola eccezione è costituita dalle informazioni sulla carta di credito. Queste informazioni vengono elaborate direttamente utilizzando il connettore pagamenti Adyen. Il pagamento è autorizzato ma non addebitato.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Aggiungere un modulo Checkout a una nuova pagina e impostare le proprietà necessarie

Per aggiungere un modulo Checkout a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Frammento \> Nuovo frammento** e denominare il nuovo frammento **Frammento check out**.
1. Aggiungere un modulo Checkout al frammento.
1. Aggiungere un'intestazione al modulo Checkout.
1. Nello slot **Informazioni check out**, aggiungere i moduli Indirizzo di spedizione, Opzioni di consegna, Contenitore sezione checkout e Informazioni contatto. Ora lo slot **Informazioni check out** dovrebbe includere quattro sezioni.
1. Nel modulo contenitore sezione check out, aggiungere i moduli Gift card, Punti fedeltà e Carta di credito. In questo modo, si garantisce la visualizzazione di tutti i metodi di pagamento in un'unica sezione.
1. Nello slot **Riepilogo ordine**, aggiungere i moduli Riepilogo ordine, Effettua ordine e Blocco ricco di contenuti.
1. Nel modulo Blocco ricco di contenuti, aggiungere il testo seguente: **Per domande relative all'ordine, contattare il numero verde di Fabrikam**.
1. Nello slot **Effettua ordine**, aggiungere un modulo Effettua ordine.
1. Selezionare **Salva**. È possibile che l'anteprima di alcuni moduli non sia visualizzata in quanto non hanno un contesto carrello.
1. Archiviare il frammento e pubblicarlo.
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
