---
title: Abilitare la ricerca degli ordini per checkout guest
description: Questo argomento descrive come abilitare la ricerca degli ordini per il checkout come guest in Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: a2a10b122faae354b0ea002e43a9bd60157f6216
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891502"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Abilitare la ricerca degli ordini per checkout guest

[!include [banner](includes/banner.md)]

Questo argomento descrive come abilitare la ricerca degli ordini per il checkout come guest in Microsoft Dynamics 365 Commerce.

La funzione di ricerca degli ordini per il checkout come guest consente ai clienti che effettuano acquisti come guest di cercare i propri ordini. La funzionalità di ricerca degli ordini è utile quando i clienti desiderano eseguire azioni come controllare lo stato di evasione dei prodotti di un ordine, verificare l'indirizzo a cui è stato spedito un ordine, riordinare un prodotto o confermare il negozio in cui un ordine verrà ritirato.

I clienti che effettuano ordini come utenti registrati possono vedere i dettagli dell'ordine quando effettuano l'accesso, ma i clienti che utilizzano il checkout come guest per effettuare ordini non possono farlo. Tuttavia, quando la funzione di ricerca degli ordini per i checkout come guest è abilitata, fornisce un modulo che i clienti possono utilizzare per cercare gli ordini che hanno effettuato come guest. In questo modulo, i clienti inseriscono l'ID di conferma dell'ordine e (facoltativamente) l'indirizzo e-mail che hanno specificato al momento del checkout.

Inoltre, un collegamento o un pulsante che indirizza il cliente direttamente alla pagina dei dettagli dell'ordine può essere incluso in qualsiasi messaggio di posta elettronica transazionale relativo all'ordine. Questo collegamento o pulsante funzionerà per gli ordini effettuati sia da utenti registrati che da utenti guest.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Attivare le funzionalità necessarie in Commerce Headquarters

Per abilitare la ricerca degli ordini per il checkout come guest, è necessario attivare le funzionalità seguenti in **Aree di lavoro \> Gestione funzionalità** in Commerce Headquarters.

| Funzionalità | Scopo |
|---------|---------|
| Funzionalità di scelta dei dettagli dell'ordine di ricerca utente anonimo Retail | Questa funzionalità espone l'interfaccia utente nei parametri di Commerce che consente di abilitare l'API di ricerca degli ordini per gli utenti non autenticati e di configurare la modalità di visualizzazione dei dati personali. |
| Abilita la generazione di un ID riferimento canale più sicuro | Questa funzionalità genera un ID di riferimento del canale di 12 caratteri più sicuro (ID di conferma dell'ordine) che può essere passato nella stringa di query quando viene cercato un ordine. |
| Genera un formato ID di riferimento canale coerente nei canali | Questa funzionalità genera un ID di riferimento del canale sicuro per gli ordini effettuati tramite un sito di e-commerce, il punto vendita al dettaglio (POS) o un call center. Prima di attivare questa funzionalità, è necessario attivare la funzionalità **Abilita generazione di un ID riferimento canale più sicuro**. |

Dopo aver attivato la funzionalità **Opzioni dettagli ricerca ordini utenti anonimi Retail**, è necessario abilitare l'API che supporta la ricerca di ordini da parte di utenti non autenticati in Commerce Headquarters. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Ordini cliente**. Nella pagina **Ordini cliente**, nella Scheda dettaglio **Ricerca ordini** impostare l'opzione **Abilita ricerca ordini non autenticati** su **Sì**, come illustrato nella figura seguente.

## <a name="manage-the-display-of-personal-data"></a>Gestire la visualizzazione dei dati personali

Nella Scheda dettaglio **Ricerca ordine** della pagina **Ordini cliente** in Commerce Headquarters è presente il campo **Includi dati personali nella ricerca di ordini guest** che consente di indicare se le informazioni personali vengono mostrate ai clienti. Tali informazioni includono l'indirizzo di spedizione e le ultime quattro cifre del numero della carta di credito del cliente. Per impostazione predefinita, le informazioni personali non vengono mostrate ai clienti quando è abilitata la ricerca degli ordini da parte di utenti non autenticati. Nella tabella seguente vengono descritte le opzioni disponibili.

| Opzione | Risultato |
|--------|--------|
| Mai | Valore predefinito. Nessuna informazione personale viene visualizzata nelle ricerche di ordini. Quando gli utenti registrati che hanno effettuato l'accesso cercano un ordine che hanno creato durante l'accesso, saranno in grado di vedere le proprie informazioni personali. |
| Solo ordini guest | Le informazioni personali vengono mostrate nelle ricerche degli ordini che i clienti hanno creato come guest. Se un ordine è stato creato da un utente registrato, tale utente deve accedere per visualizzare le proprie informazioni personali. |
| Tutti gli ordini | Le informazioni personali vengono visualizzate in tutte le ricerche di ordini. |

> [!NOTE]
> Queste opzioni determinano quando i dati personali, come l'indirizzo e le ultime quattro cifre del numero della carta di credito del cliente, vengono mostrati agli utenti guest anonimi. Per aiutare a proteggere la privacy dei clienti registrati, consigliamo di selezionare l'opzione **Solo ordini guest**. Tuttavia, l'opzione più sicura è **Mai**.

Dopo aver modificato il valore del campo **Includi dati personali nella ricerca di ordini guest**, è necessario eseguire il processo 1070 (**Configurazione canale**) in Commerce Headquarters andando a **Retail e Commerce \> Retail e Commerce IT \> Programmazione della distribuzione**.

## <a name="configure-the-order-lookup-module"></a>Configurare il modulo di ricerca degli ordini

Il modulo di ricerca degli ordini nella libreria del modulo Commerce viene utilizzato per eseguire il rendering del modulo che consente agli utenti guest di cercare gli ordini. Il modulo di ricerca degli ordini può essere incluso nello slot del corpo di qualsiasi pagina che non richiede l'accesso del cliente. Per informazioni su come configurare il modulo, vedere [Modulo ricerca degli ordini](order-lookup-module.md).

## <a name="configure-the-order-details-page"></a>Configurare la pagina dei dettagli dell'ordine

Prima che gli utenti guest possano visualizzare i dettagli dell'ordine, la pagina dei dettagli dell'ordine sul tuo sito di e-commerce deve essere configurata in modo che non richieda l'accesso. Per disattivare il requisito di accesso per la pagina dei dettagli dell'ordine, apri la pagina in Creazione di siti di Commerce, seleziona il riquadro **Pagina predefinita (richiesto)** nella visualizzazione ad albero e deseleziona la casella di controllo **Richiede l'accesso?** nella parte inferiore del riquadro delle proprietà a destra.

## <a name="add-a-link-to-order-details-in-transactional-emails"></a>Aggiungere un collegamento ai dettagli dell'ordine nelle e-mail transazionali

Nelle e-mail relative agli ordini, puoi fornire un collegamento o un pulsante che indirizzi i clienti alla pagina dei dettagli del loro ordine. Per aggiungere questo collegamento o pulsante, crea un collegamento ipertestuale HTML che punta alla pagina dei dettagli dell'ordine sul tuo sito di e-commerce e passa l'ID di conferma dell'ordine e l'indirizzo e-mail del cliente come parametri URL, come mostrato nell'esempio seguente.

`<a href="https://[domain]/[orderdetailspage]?confirmationId=%orderconfirmationid%&propertyName=email&propertyValue=%customeremailaddress%" target="_blank">View my order status</a>`

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo ricerca degli ordini](order-lookup-module.md)

[Impostare un profilo di notifica tramite posta elettronica](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
