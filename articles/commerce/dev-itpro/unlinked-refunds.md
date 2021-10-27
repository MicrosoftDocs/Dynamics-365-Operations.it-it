---
title: Elabora rimborsi non collegati al Connettore di pagamento Dynamics 365 Commerce per Adyen
description: Questo argomento descrive come funzionano i rimborsi non collegati quando viene utilizzato il Connettore pagamenti di Microsoft Dynamics 365 per Adyen.
author: BrianShook
ms.date: 10/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: BrShoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c137dcf7d35031a293c88d8c4f5dc1e5f3d9e2f9
ms.sourcegitcommit: a21a664cd35b95c8600c5af0aac588a64e892902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623923"
---
# <a name="process-unlinked-refunds-with-the-dynamics-365-commerce-payment-connector-for-adyen"></a>Elabora rimborsi non collegati al Connettore di pagamento Dynamics 365 Commerce per Adyen

[!include [banner](../includes/banner.md)]

Questo argomento descrive come funzionano i rimborsi non collegati quando viene utilizzato il [Connettore pagamenti di Microsoft Dynamics 365 per Adyen](adyen-connector.md). Esamina inoltre la capacità di elaborare un rimborso rispetto a un nuovo metodo di pagamento nel punto vendita (POS) o nel call center.

Il connettore pagamenti di Dynamics 365 per Adyen supporta la possibilità di elaborare i rimborsi utilizzando un metodo di pagamento diverso da quello utilizzato per la transazione originale. Anche se ti consigliamo di utilizzare [rimborsi collegati](linked-refunds.md) per elaborare un rimborso rispetto al metodo di pagamento di origine fornito, in alcuni scenari sono necessari rimborsi con un metodo diverso. Ad esempio, la carta utilizzata per il pagamento originale potrebbe essere scaduta o persa oppure potrebbe essere stata annullata dall'utente.

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere completati prima che il connettore pagamenti di Dynamics 365 per Adyen possa elaborare i rimborsi non collegati:

- Impostare i [metodi di pagamento](../payment-methods.md).
- Impostare i [pagamenti multicanale](../omni-channel-payments.md).

## <a name="additional-configuration"></a>Configurazione aggiuntiva

Il connettore pagamenti di Dynamics 365 per Adyen fornisce un'implementazione predefinita di ogni scenario di rimborso supportato descritto nella sezione successiva. I clienti che non utilizzano l'implementazione predefinita del connettore pagamenti di Dynamics 365 per Adyen devono configurare il connettore che supporta la tokenizzazione delle carte di credito.

## <a name="supported-refund-scenarios"></a>Scenari di rimborso supportati

Dynamics 365 Commerce supporta rimborsi delle transazioni precedentemente approvate e confermate. I rimborsi possono consistere in un rimborso completo o in un rimborso parziale della transazione. I rimborsi non possono superare l'intero importo dell'autorizzazione di pagamento originale. I rimborsi non collegati sono supportati solo in POS e call center.

## <a name="enable-unlinked-refunds-functionality"></a>Abilita la funzionalità di rimborso non collegato

Per abilitare la funzionalità di rimborsi non collegati in Commerce Headquarters, segui questi passaggi.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio**.
1. Nella scheda **Pagamenti multicanale**, impostare l'opzione **Usa pagamenti multicanale** su **Sì**.

### <a name="supported-payment-method-variants"></a>Varianti metodo di pagamento supportate

Le seguenti varianti del metodo di pagamento supportano immediatamente i rimborsi non collegati:

- Carte
- Portafoglio

Non tutte le varianti del metodo di pagamento supportano i rimborsi non collegati. La tabella seguente fornisce un elenco di metodi di pagamento comuni e mostra la capacità di supporto di ciascun metodo per i rimborsi collegati e non collegati.

| Metodo di pagamento        | Rimborso collegato | Rimborso non collegato |
|-----------------------|:-------------:|:---------------:|
| amexcommercial        | Sì           | Sì             |
| amexconsumer          | Sì           | Sì             |
| amexcorporate         | Sì           | Sì             |
| amexdebit             | Sì           | Sì             |
| amexprepaid           | Sì           | Sì             |
| amexprepaidreloadable | Sì           | Sì             |
| amexsmallbusiness     | Sì           | Sì             |
| individua              | Sì           | Sì             |
| maestro               | Sì           | Sì             |
| maestrouk             | Sì           | Sì             |
| mc                    | Sì           | Sì             |
| mcalphabankbonus      | Sì           | Sì             |
| mcprepaidanonymous    | Sì           | Sì             |
| visa                  | Sì           | Sì             |
| visaalphabankbonus    | Sì           | Sì             |
| visacheckout          | Sì           | Sì             |
| visadankort           | Sì           | Sì             |
| visahipotecario       | Sì           | Sì             |
| visasaraivacard       | Sì           | Sì             |
| vpay                  | Sì           | Sì             |
| givex                 | **No**        | Sì             |
| svs                   | **No**        | Sì             |
| cup                   | Sì           | Sì             |
| diners                | Sì           | Sì             |
| interac               | **No**        | Sì             |
| jcb                   | Sì           | Sì             |
| jcb_applepay          | Sì           | Sì             |
| unionpay              | Sì           | Sì             |

### <a name="process-an-unlinked-refund-in-pos"></a>Elabora un rimborso non collegato in POS

Un cliente restituisce un articolo a un cassiere POS entro il periodo consentito per i resi e dispone di una ricevuta valida. Durante l'elaborazione per il reso, la finestra di dialogo **Pagamento reso** include un'opzione **Scegli un metodo di pagamento**. Il cassiere può quindi selezionare un metodo di pagamento tra i metodi di pagamento supportati per i rimborsi (carte e portafoglio).

### <a name="process-an-unlinked-refund-in-call-center"></a>Elabora un rimborso non collegato in call center

Quando un rimborso non collegato viene elaborato a fronte di un ordine nel call center, un dipendente del call center seleziona un metodo di pagamento diverso dal metodo di origine. Al dipendente viene quindi richiesto di ottenere un numero di identificazione personale (PIN) di sostituzione dell'amministratore. Il PIN è necessario prima che il diverso metodo di pagamento possa essere elaborato per il rimborso.

#### <a name="set-up-an-administrator-override-pin-for-call-center"></a>Imposta un PIN di sostituzione dell'amministratore per il call center

Per impostare un PIN di sostituzione dell'amministratore per il call center in Commerce Headquarters, segui questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione canale \> Impostazione servizio clienti** oppure cerca "Autorizzazioni di sostituzione".
1. Seleziona il ruolo a cui concedere le autorizzazioni di elaborazione dei rimborsi non collegati.
1. Nella scheda dettaglio **Rimborsi**, imposta l'opzione **Consenti pagamento alternativo** su **Sì**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Dynamics 365 Payment Connector per Adyen](adyen-connector.md)

[Rimborsi collegati di transazioni precedentemente approvate e confermate](linked-refunds.md)
