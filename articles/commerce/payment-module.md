---
title: Modulo pagamento
description: In questo argomento viene descritto il modulo di pagamento e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 85b5d8306eb4e9f2a4b9df13d95ab88020c3591e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000667"
---
# <a name="payment-module"></a>Modulo pagamento

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo di pagamento e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo di pagamento consente ai clienti di pagare gli ordini utilizzando una carta di credito o di debito. L'integrazione di pagamento per questo modulo viene fornita dal connettore pagamenti di Dynamics 365 per Adyen. Per ulteriori informazioni su come configurare il connettore pagamenti, vedere [Connettore pagamenti di Dynamics 365 per Adyen](dev-itpro/adyen-connector.md).  

A partire dalla versione Commerce 10.0.14, il modulo di pagamento è stato anche integrato con il connettore di pagamento Dynamics 365 per PayPal per consentire ai clienti di pagare gli ordini utilizzando PayPal. Per ulteriori informazioni su come configurare il connettore pagamenti Dynamics 365 per PayPal, vedere [Connettore pagamenti di Dynamics 365 per PayPal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Connettore pagamenti di Dynamics 365 per Adyen 

Il modulo di pagamento ospita le informazioni di pagamento fornite tramite Adyen in un frame inline HTML (iframe). Il modulo di pagamento interagisce con Commerce Scale Unit per recuperare le informazioni di pagamento di Adyen. Come parte dell'interazione con Commerce Scale Unit, il modulo di pagamento può consentire la pubblicazione delle informazioni sull'indirizzo di fatturazione nell'iframe tramite Adyen o come modulo separato. Nel tema Fabrikam, l'indirizzo di fatturazione è abilitato come modulo separato. Questo approccio consente una maggiore flessibilità di formattazione, perché le righe dell'indirizzo possono essere visualizzate in modo che assomiglino alle righe dell'indirizzo di spedizione.

Il modulo di pagamento consente inoltre ai clienti registrati di salvare le proprie informazioni di pagamento. Le informazioni di pagamento e l'indirizzo di fatturazione vengono salvati e gestiti tramite il connettore di pagamento Adyen.

Il modulo di pagamento copre eventuali addebiti sugli ordini che non sono già coperti da punti fedeltà o da una carta regalo. Se il totale di un ordine è completamente coperto da punti fedeltà o crediti di carte regalo, il modulo di pagamento verrà nascosto e il cliente potrà effettuare l'ordine senza di esso.

Il connettore pagamenti Adyen supporta inoltre l'autenticazione avanzata del cliente (SCA). Parte della direttiva aggiornata relativa ai servizi di pagamento (PSD2) dell'Unione europea (UE) richiede che gli acquirenti online siano autenticati al di fuori della loro esperienza di acquisto online quando utilizzano una modalità di pagamento elettronico. Durante il flusso di checkout, i clienti vengono reindirizzati al proprio sito bancario e quindi, dopo l'autenticazione, vengono reindirizzati nuovamente al flusso di checkout di Commerce. Durante questo reindirizzamento, le informazioni che un cliente ha inserito nel flusso di checkout (ad esempio, l'indirizzo di spedizione, le opzioni di consegna, le informazioni sulla carta regalo e le informazioni sulla fedeltà) persisteranno. Prima di poter attivare la funzione del connettore di pagamento Adyen, il connettore di pagamento deve essere configurato per SCA in Commerce headquarters. Per ulteriori informazioni, vedere [Autenticazione avanzata del cliente (SCA) tramite Adyen](adyen_redirect.md). Questa funzione è stata abilitata nella versione 10.0.12 di Commerce.

> [!NOTE]
> Per il connettore pagamenti Adyen, il modulo iframe nel modulo di pagamento può essere visualizzato solo se si aggiunge l'URL di Adyen all'elenco dei siti consentiti. Per completare questo passaggio, aggiungere **\*.adyen.com** alle direttive **child-src**, **connect-src**, **img-src**, **script-src** e **style-src** dei criteri di sicurezza dei contenuti del sito. Per altre informazioni, vedere [Gestire i criteri di sicurezza del contenuto](manage-csp.md). 

L'immagine seguente mostra un esempio di moduli Gift card, Punti fedeltà e Pagamento Adyen in una pagina checkout.

![Esempio di moduli Gift card, Punti fedeltà e Pagamento Adyen in una pagina checkout](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Connettore pagamenti di Dynamics 365 per PayPal

A partire dalla versione Commerce 10.0.14, il modulo di pagamento è anche integrato con il connettore di pagamento Dynamics 365 per PayPal. Per ulteriori informazioni su come configurare questo connettore pagamenti, vedere [Connettore pagamenti di Dynamics 365 per PayPal](paypal.md).
 
Nella pagina checkout è possibile configurare i connettori Adyen e PayPal. Il modulo di pagamento è stato migliorato con proprietà aggiuntive per aiutare a identificare con quale connettore dovrebbe funzionare. Per i dettagli, vedere le proprietà del modulo **Tipi di metodo di pagamento supportati** e **Pagamento principale** nella tabella seguente.
  
Quando il modulo di pagamento è configurato per utilizzare il connettore di pagamento PayPal, viene visualizzato un pulsante PayPal nella pagina checkout. Quando viene richiamato dal cliente, il modulo di pagamento visualizza un iframe contenente le informazioni di PayPal. Il cliente può accedere e fornire le proprie informazioni di PayPal all'interno di questo iframe per completare la transazione. Quando un cliente sceglie di pagare con PayPal, il saldo rimanente dell'ordine verrà addebitato tramite PayPal.

Il connettore di pagamento PayPal non richiede un modulo dell'indirizzo di fatturazione perché tutte le informazioni relative alla fatturazione vengono gestite da PayPal all'interno del suo iframe. Tuttavia, sono richiesti l'indirizzo di spedizione e i moduli delle opzioni di consegna.

La figura seguente mostra un esempio di due moduli di pagamento su una pagina checkout, uno configurato con il connettore di pagamento Adyen e l'altro con il connettore di pagamento PayPal.
![Esempio di moduli di pagamento Adyen e PayPal in una pagina checkout](./media/ecommerce-paypal.png)

La figura seguente mostra un esempio dell'iframe PayPal richiamato utilizzando il pulsante PayPal. 
![Esempio di iframe Paypal in una pagina di pagamento](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Proprietà del modulo Pagamento

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione | Testo dell'intestazione | Un'intestazione facoltativa per il modulo di pagamento. |
| Altezza dell'iframe | Pixel | L'altezza dell'iframe, in pixel. L'altezza può essere modificata secondo le esigenze. |
| Mostra indirizzo di fatturazione | **True** o **False** | Se questa proprietà è impostata su **True**, l'indirizzo di fatturazione verrà fornito da Adyen all'interno dell'iframe del modulo di pagamento. Se è impostata su **False**, l'indirizzo di fatturazione non verrà fornito da Adyen e un utente di Commerce dovrà configurare un modulo per mostrare l'indirizzo di fatturazione nella pagina di check out. Per il connettore di pagamento PayPal, questo campo non ha alcun impatto, poiché l'indirizzo di fatturazione è completamente gestito all'interno di PayPal. |
| Ignora stile pagamenti | Codice Cascading Style Sheets (CSS) | Poiché il modulo di pagamento è ospitato in un iframe, la capacità di stile è limitata. È possibile ottenere uno stile utilizzando questa proprietà. Per sostituire gli stili del sito, è necessario incollare il codice CSS come valore di questa proprietà. La creazione di siti CSS e gli stili non si applicano a questo modulo. |
|Tipi di metodi di pagamento supportati| String| Se sono configurati più connettori di pagamento, è necessario fornire la stringa del tipo di offerta supportata come definito nella configurazione del connettore di pagamento di Commerce headquarters (vedere l'immagine seguente). Se vuoto, il valore predefinito è il connettore di pagamento Adyen. Aggiunto nella versione Commerce 10.0.14.|
|Pagamento primario|  **True** o **False** | Se **Vero**, eventuali messaggi di errore verranno generati dal connettore di pagamento principale nella pagina di pagamento. Se sono configurati entrambi i connettori di pagamento Adyen e PayPal, impostare Adyen su **Vero**, in quanto è stato aggiunto nella versione Commerce 10.0.14.|

La figura seguente mostra un esempio del valore **Tipi di metodo di pagamento supportati** impostato su "PayPal" nella configurazione del connettore di pagamento in Commerce headquarters.
![Esempio di tipi di metodo di pagamento supportati in Commerce headquarters](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Indirizzo fatturazione

È possibile utilizzare un modulo dell'indirizzo di fatturazione nella pagina di pagamento se le righe dell'indirizzo di fatturazione del connettore di pagamento Adyen non corrispondono all'aspetto del resto del sito. 

Per utilizzare un modulo di indirizzo di fatturazione nella pagina di pagamento quando il modulo di pagamento è integrato con il connettore di pagamento Adyen, impostare la proprietà **Mostra indirizzo di fatturazione** su **Falso** in modo che un modulo di indirizzo di fatturazione dedicato possa essere utilizzato al posto dell'indirizzo di fatturazione Adyen predefinito. In questo caso, l'autore del sito dovrebbe includere un modulo dell'indirizzo di fatturazione nella pagina di pagamento. Il connettore di pagamento Adyen consente inoltre di utilizzare l'indirizzo di spedizione come indirizzo di fatturazione per ridurre al minimo il numero di passaggi per l'utente del sito.

Simile ai moduli di pagamento, la proprietà **Tipi di metodo di pagamento supportati** è stata aggiunta al modulo dell'indirizzo di fatturazione nella versione Commerce 10.0.14. Il valore di questa proprietà deve essere identico al valore fornito nel modulo di pagamento per garantire che funzionino insieme. Per il connettore di pagamento Adyen, sia il modulo di pagamento che il modulo dell'indirizzo di fatturazione devono lasciare questo valore vuoto (lo stato predefinito). Per il connettore PayPal, non è richiesto un modulo di indirizzo di fatturazione dedicato. Per altri tipi di connettori di pagamento, la stringa deve essere fornita come configurato in Commerce headquarters.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Aggiungere un modulo di pagamento a una pagina di checkout e impostare le proprietà necessarie

Un modulo di pagamento può essere aggiunto solo a un modulo checkout. Per ulteriori informazioni su come configurare un modulo di pagamento per una pagina di checkout, vedere [Modulo checkout](add-checkout-module.md).

Se sono necessari entrambi i connettori di pagamento Adyen e PayPal, aggiungere entrambi i moduli alla sezione dei pagamenti. Assicurarsi che il valore della proprietà **Tipi di metodo di pagamento supportati** sia configurato per PayPal e lasciarlo vuoto per Adyen. Inoltre, impostare la proprietà **Pagamento principale** su **Vero** per Adyen.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo di informazioni sul ritiro](pickup-info-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)

[Connettore pagamenti di Dynamics 365 per Adyen](dev-itpro/adyen-connector.md)

[Connettore pagamenti di Dynamics 365 per PayPal](paypal.md)

[Autenticazione avanzata del cliente tramite Adyen](adyen_redirect.md)
