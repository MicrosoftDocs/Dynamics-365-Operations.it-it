---
title: Modulo pagamento
description: In questo argomento viene descritto il modulo di pagamento e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
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
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 4267391edaf70ec645933b2c5c08a72735f52894
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818328"
---
# <a name="payment-module"></a>Modulo pagamento

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo di pagamento e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Il modulo di pagamento consente ai clienti di pagare gli ordini utilizzando una carta di credito o di debito. L'integrazione di pagamento per questo modulo viene fornita dal connettore pagamenti di Dynamics 365 per Adyen. Per ulteriori informazioni su come configurare il connettore pagamenti, vedere [Connettore pagamenti di Dynamics 365 per Adyen](dev-itpro/adyen-connector.md).

Il modulo di pagamento ospita le informazioni di pagamento fornite tramite Adyen in un frame inline HTML (iframe). Il modulo di pagamento interagisce con Commerce Scale Unit per recuperare le informazioni di pagamento di Adyen. Come parte dell'interazione con Commerce Scale Unit, il modulo di pagamento può consentire la pubblicazione delle informazioni sull'indirizzo di fatturazione nell'iframe o come modulo separato. Nel tema Fabrikam, l'indirizzo di fatturazione viene visualizzato in un modulo separato. Questo approccio consente una maggiore flessibilità di formattazione, perché le righe dell'indirizzo possono essere visualizzate in modo che assomiglino alle righe dell'indirizzo di spedizione.

Il modulo di pagamento consente inoltre ai clienti registrati di salvare le proprie informazioni di pagamento. Le informazioni di pagamento e l'indirizzo di fatturazione vengono salvati e gestiti tramite il connettore di pagamento Adyen.

Il modulo di pagamento copre eventuali addebiti sugli ordini che non sono già coperti da punti fedeltà o da una carta regalo. Se il totale di un ordine è completamente coperto da punti fedeltà o crediti di carte regalo, il modulo di pagamento verrà nascosto e il cliente potrà effettuare l'ordine senza di esso.

Il connettore pagamenti Adyen supporta inoltre l'autenticazione avanzata del cliente (SCA). Parte della direttiva relativa ai servizi di pagamento 2.0 (PSD2.0) dell'Unione europea (UE) richiede che gli acquirenti online siano autenticati al di fuori della loro esperienza di acquisto online quando utilizzano una modalità di pagamento elettronico. Durante il flusso di check out, i clienti vengono reindirizzati al loro sito bancario. Quindi, dopo l'autenticazione, vengono reindirizzati al flusso di check out di Commerce. Durante questo reindirizzamento, le informazioni che un cliente ha inserito nel flusso di checkout (ad esempio, l'indirizzo di spedizione, le opzioni di consegna, le informazioni sulla carta regalo e le informazioni sulla fedeltà) persisteranno. Prima di poter attivare questa funzione, il connettore di pagamento deve essere configurato per SCA in Commerce headquarters. Per ulteriori informazioni, vedere [Autenticazione avanzata del cliente (SCA) tramite Adyen](adyen_redirect.md).

L'immagine seguente mostra un esempio di moduli Gift card, Punti fedeltà e Pagamento in una pagina checkout.

![Esempio di moduli Gift card, Punti fedeltà e Pagamento in una pagina checkout](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Proprietà del modulo Pagamento

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione | Testo dell'intestazione | Un'intestazione facoltativa per il modulo di pagamento. |
| Altezza dell'iframe | Pixel | L'altezza dell'iframe, in pixel. L'altezza può essere modificata secondo le esigenze. |
| Mostra indirizzo di fatturazione | **True** o **False** | Se questa proprietà è impostata su **True**, l'indirizzo di fatturazione verrà fornito da Adyen all'interno dell'iframe del modulo di pagamento. Se è impostata su **False**, l'indirizzo di fatturazione non verrà fornito da Adyen e un utente di Commerce dovrà configurare un modulo per mostrare l'indirizzo di fatturazione nella pagina di check out. |
| Ignora stile pagamenti | Codice Cascading Style Sheets (CSS) | Poiché il modulo di pagamento è ospitato in un iframe, la capacità di stile è limitata. È possibile ottenere uno stile utilizzando questa proprietà. Per sostituire gli stili del sito, è necessario incollare il codice CSS come valore di questa proprietà. La creazione di siti CSS e gli stili non si applicano a questo modulo. |

## <a name="billing-address"></a>Indirizzo di fatturazione

Il modulo di pagamento consente ai clienti di fornire un indirizzo di fatturazione per le informazioni di pagamento. Inoltre, consente loro di utilizzare il proprio indirizzo di spedizione come indirizzo di fatturazione, per rendere il flusso di pagamento più semplice e veloce. Se la proprietà **Mostra indirizzo di fatturazione** è impostata su **False**, il modulo di pagamento dovrebbe essere configurato nella pagina di check out.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Aggiungere un modulo di pagamento a una pagina di checkout e impostare le proprietà necessarie

Un modulo di pagamento può essere aggiunto solo a un modulo checkout. Per ulteriori informazioni su come configurare un modulo di pagamento per una pagina di checkout, vedere [Modulo checkout](add-checkout-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo carrello](add-cart-module.md)

[Modulo icona carrello](cart-icon-module.md)

[Modulo checkout](add-checkout-module.md)

[Modulo indirizzo di spedizione](ship-address-module.md)

[Modulo opzioni di consegna](delivery-options-module.md)

[Modulo Dettagli ordini](order-confirmation-module.md)

[Modulo gift card](add-giftcard.md)

[Connettore pagamenti di Dynamics 365 per Adyen](dev-itpro/adyen-connector.md)

[Autenticazione avanzata del cliente tramite Adyen](adyen_redirect.md)
