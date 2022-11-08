---
title: Codici di riferimento degli errori del modulo di checkout
description: Questo articolo descrive i codici di riferimento degli errori del modulo di checkout mostrati nei messaggi di errore rivolti all'utente in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 952cb932522b4e0bb91be985e4f8974cb6cd8bc0
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728247"
---
# <a name="checkout-module-error-reference-codes"></a>Codici di riferimento degli errori del modulo di checkout

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Questo articolo descrive i codici errore del modulo di checkout mostrati nei messaggi di errore rivolti all'utente in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ha introdotto riferimenti agli errori standardizzati che possono essere inclusi negli errori di checkout dei canali online presentati ai clienti online. In Commerce versione 10.0.31 e successive, i messaggi di errore nel modulo di checkout includono codici errore e non mostrano informazioni non necessarie al cliente online. I codici errore si riferiscono agli errori descritti in dettaglio in questo articolo.

A seconda dell'errore riscontrato, la tabella in questo articolo include i dettagli seguenti:

- Una descrizione della condizione che ha causato l'errore o dettagli aggiuntivi
- Informazioni da considerare nell'ambiente o nelle configurazioni del connettore di pagamento
- Informazioni a cui è possibile fare riferimento in un caso di supporto, se è necessaria ulteriore assistenza

## <a name="prerequisites"></a>Prerequisiti

Per abilitare i codici di riferimento degli errori del modulo di pagamento elencati di seguito, nel generatore siti per il tuo sito, vai a **Impostazioni sito \> Estensioni**, e nella sezione **Carrello e pagamento** seleziona **Abilita messaggistica di visualizzazione errori canale online avanzata**. 

## <a name="checkout-module-error-reference-codes"></a>Codici di riferimento degli errori del modulo di checkout

Utilizzare la tabella seguente per ottenere maggiori dettagli sui riferimenti ai codici errore forniti dai clienti o riscontrati nel punto vendita online. Scorri verso destra per visualizzare la colonna **Descrizione dell'errore**.

| Codice errore | Codice errore correlati a Dynamics | Descrizione errore |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | Il pagamento non è stato autorizzato. ID tipo di carta in **TokenizedPaymentCard** mancante oppure l'ID tipo di carta fornito non è supportato. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Rifiutato. Il pagamento non è stato autorizzato. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | Il pagamento non è stato autorizzato. Informazioni aggiuntive richieste dal cliente. |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Si è verificato un errore. Non è stato possibile ottenere il risultato di accettazione del pagamento con carta. Prova a ripetere l'operazione o contatta l'amministratore di sistema. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | Impossibile effettuare il pagamento a causa della mancanza delle proprietà di pagamento dell'esercente. Contatta l'amministratore di sistema. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | Impossibile recuperare il servizio di pagamento per l'operazione. Controlla la configurazione del tuo metodo di pagamento per il tipo di pagamento selezionato. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | Un pagamento su conto cliente è già stato applicato e ne è consentito solo uno per transazione. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountLimitSignDifferentFromAmountDue | Il limite del conto cliente differisce dall'importo dovuto. Prova un metodo di pagamento diverso o contatta l'assistenza clienti. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | Il pagamento del conto cliente supera il totale dovuto per gli articoli elencati. Riprova più tardi o contatta il supporto clienti per assistenza. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | Il pagamento per il conto cliente richiede il conto personale o un conto di abbinamento fatture su una riga di metodo di pagamento. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | Impossibile elaborare un pagamento del conto cliente in questo momento. Valore limite importo base superato. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Al cliente non è consentito pagare in acconto. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Si è verificato un errore. Non è stato possibile annullare il pagamento. Riprova. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Si è verificato un errore durante l'elaborazione del pagamento. Riprova più tardi. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | L'importo del pagamento del programma fedeltà supera l'importo consentito per la carta fedeltà utilizzata in questa transazione. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | L'importo del rimborso del programma fedeltà supera l'importo consentito per la carta fedeltà utilizzata in questa transazione. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | Impossibile trovare il numero della carta fedeltà. Attiva il numero della carta fedeltà o immetti un numero di carta diverso e riprova. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | Il numero della carta fedeltà non è disponibile. Immetti un numero di carta diverso e riprova. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Questa carta fedeltà non è qualificata per il riscatto dei punti fedeltà in questa transazione. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | Si è verificato un errore relativo al numero della gift card. Prova una gift card diversa o contatta l'assistenza clienti. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | L'importo supera il saldo sulla carta regalo. Immetti un importo diverso e riprova. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | La transazione non può contenere più di una riga pagamento fedeltà. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | Le informazioni di pagamento sono mancanti o errate. Verifica le informazioni di pagamento e poi riprova. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | Impossibile elaborare l'ordine in questo momento. Riprova più tardi. |
| CCR025     | Timeout del front-end per l'API di checkout | L'operazione front-end è scaduta. Conferma se l'ordine è stato elaborato in Dynamics 365 Commerce Headquarters. |
| CCR026     | Importo autorizzato originale modificato | L'importo dell'ordine è cambiato rispetto all'importo dell'autorizzazione originale elaborato con il gateway di pagamento. Ciò potrebbe essere dovuto alla scadenza temporizzata di un buono sconto, una promozione o un articolo in saldo. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Si è verificato un errore durante l'elaborazione di un pagamento. Il riferimento fornito all'API del carrello ha un riferimento diverso da quello previsto (da notare la potenziale incoerenza durante il processo di checkout). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | Si è verificato un errore relativo al metodo di pagamento tentato. Contatta l'assistenza per rivedere le impostazioni del tuo conto o riprova con un metodo di pagamento diverso. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](dev-itpro/payments-retail.md)

[Modulo checkout](add-checkout-module.md)

[Modulo pagamento](payment-module.md)
