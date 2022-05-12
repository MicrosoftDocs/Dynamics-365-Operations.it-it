---
title: Configurare il metodo di pagamento del conto cliente per i siti Web di e-commerce B2B
description: Questo argomento descrive come configurare il metodo di pagamento del conto cliente in Microsoft Dynamics 365 Commerce. Descrive inoltre in che modo i limiti di credito influiscono sull'acquisizione del pagamento in acconto nei siti di e-commerce business-to-business (B2B).
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a8fdeb109204557f0e44457e23a60224e662474f
ms.sourcegitcommit: 96e2fb26efd2cd07bbf97518b5c115e17b77a0a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2022
ms.locfileid: "8616834"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurare il metodo di pagamento del conto cliente per i siti Web di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come configurare il metodo di pagamento del conto cliente in Microsoft Dynamics 365 Commerce. Descrive inoltre in che modo i limiti di credito influiscono sull'acquisizione del pagamento in acconto nei siti di e-commerce business-to-business (B2B).

I rivenditori possono accettare diversi tipi di pagamento per i prodotti venduti e i servizi forniti in un canale di e-commerce. Ogni tipo di pagamento accettato da un rivenditore deve essere configurato in Dynamics 365 Commerce quando si imposta il sistema. Il metodo di pagamento del conto cliente (o "in acconto") deve essere supportato sui siti di e-commerce B2B. 

## <a name="prerequisites"></a>Prerequisiti

1. Aggiungi il metodo di pagamento del conto cliente in Commerce headquarters.
2. Associa il metodo di pagamento del conto cliente al canale di e-commerce.
3. Assicurati che la proprietà **Consenti in acconto** sia abilitato per il cliente in **Retail e Commerce \> Clienti \> Tutti i clienti \> Impostazioni predefinite pagamento** in Commerce headquarters.

    > [!NOTE]
    > Se tutti i clienti devono essere autorizzati ad avere il metodo di pagamento in acconto abilitato, è possibile impostare la proprietà **Consenti in acconto** su **Sì** per il cliente predefinito del canale associato al sito B2B. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce 

Per abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **Impostazioni sito \> Estensioni**.
1. Imposta la proprietà **Abilita pagamenti conto cliente** su **Abilitato per clienti B2B**. 
1. Selezionare **Salva e pubblica**.

> [!NOTE]
> Le nuove impostazioni del sito avranno effetto solo dopo l'aggiornamento del file app.settings.json. Per ulteriori informazioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B

Per abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B, segui questi passaggi.

1. In Creazione di siti di Commerce, trova e modifica la pagina di pagamento o il frammento che contiene il modulo di pagamento per il sito di e-commerce B2B.
1. Nello slot **Contenitore sezione checkout**, seleziona **Aggiungi modulo**, quindi aggiungi un modulo **Pagamento conto cliente**.
1. Posiziona il modulo **Pagamento conto cliente** selezionando i puntini di sospensione (**...**), quindi selezionando **Sposta su** o **Sposta giù** come necessario.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato

Per verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato, segui questi passaggi.

1. Accedi al sito di e-commerce.
1. Aggiungi un prodotto al carrello.
1. Vai alla pagina di pagamento. Dovresti vedere il nuovo metodo di pagamento **Conto cliente**.

## <a name="work-with-credit-limits"></a>Utilizzare limiti di credito

Quando le funzionalità per i pagamenti del conto cliente sono abilitate sul sito B2B, le organizzazioni in genere desiderano mostrare informazioni sui limiti di credito e sui saldi dei limiti di credito durante il processo di acquisizione dell'ordine. Il limite di credito per un cliente è definito dalla proprietà **Limite di credito** nella Scheda dettaglio **Credito e riscossioni** del record cliente in Commerce headquarters. Tuttavia, negli scenari B2B, un ordine effettuato da un cliente deve spesso essere fatturato sul conto dell'organizzazione a cui appartiene il cliente. Pertanto, è necessario impostare la proprietà **Conto fattura** nella Scheda dettaglio **Fattura e consegna** del record cliente sull'ID conto cliente dell'organizzazione. Quindi, quando il cliente effettua un ordine sul sito B2B, l'ordine verrà fatturato all'organizzazione. Il sito B2B utilizzerà anche il limite di credito dell'organizzazione anziché il limite di credito definito nel record cliente.

Il calcolo e il saldo del limite di credito visualizzati sul sito Web B2B dipendono dall'impostazione della proprietà **Tipo di limite di credito** in Commerce headquarters. La posizione di questa proprietà varia, a seconda che la funzionalità **Gestione crediti** è abilitata nell'area di lavoro **Gestione funzionalità**:

- Se la funzionalità **Gestione crediti** è abilitata, la proprietà si trova nella Scheda dettaglio **Limiti di credito** in **Credito e riscossioni \> Impostazioni \> Parametri credito e riscossioni \> Credito**. 
- Se la funzionalità **Gestione crediti** è disabilitata, la proprietà si trova sotto **Posizione finanziaria** in **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti \> Posizione finanziaria**.

I valori che la proprietà **Tipo di limite di credito** supporta sono **Nessuno**, **Saldo**, **Saldo+Documento di trasporto o entrata prodotti** e **Saldo + Tutto**. Per ulteriori informazioni su questi valori, vedi [Valori del tipo di limite di credito](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Consigliamo di impostare la proprietà **Tipo di limite di credito** su **Saldo + scontrino di imballaggio o scontrino prodotto**, di modo che gli ordini cliente aperti non contribuiscano al calcolo del saldo. Quindi, se i clienti effettuano ordini futuri, tali ordini influiscono sul loro saldo corrente.

Un'altra proprietà che influisce sull'ordine in acconto è la proprietà **Limite di credito obbligatorio**, che si trova nella Scheda dettaglio **Credito e riscossioni** del record cliente. Impostando questa proprietà su **Sì** per specifici clienti, è possibile forzare il sistema a verificare il loro limite di credito, anche se la proprietà **Tipo di limite di credito** è stata impostata su **Nessuno** per specificare che il limite di credito non deve essere verificato per alcun cliente.

Attualmente, un cliente che utilizza il metodo di pagamento acconto non può pagare più del saldo residuo per un ordine. Ad esempio, se il credito residuo di un cliente è $1.000, ma l'importo dell'ordine è $1.200, il cliente può pagare solo $1.000 utilizzando il metodo di pagamento in acconto. Il cliente deve utilizzare un altro metodo di pagamento per pagare il saldo. In una versione futura, una configurazione di Commerce consentirà agli utenti di spendere oltre il limite di credito quando effettuano gli ordini.

Il modulo **Credito e riscossioni** ha nuove funzionalità di gestione del credito. Per attivare queste funzionalità, abilitare la funzionalità **Gestione crediti** nell'area di lavoro **Gestione funzionalità**. Una delle nuove funzionalità consente di sospendere gli ordini cliente in base a regole di blocco. L'utente tipo che si occupa della gestione dei crediti può quindi rilasciare o rifiutare gli ordini dopo un'ulteriore analisi. Tuttavia, la possibilità di sospendere gli ordini cliente non è applicabile agli ordini di Commerce, poiché gli ordini cliente spesso prevedono un pagamento anticipato e la funzionalità **Gestione crediti** non supporta completamente gli scenari di pagamento anticipato. 

Indipendentemente dal fatto che la funzionalità **Gestione crediti** è abilitata o meno, se il saldo di un cliente supera il limite di credito durante l'evasione dell'ordine, gli ordini cliente non verranno sospesi. Invece, Commerce genererà un messaggio di avviso o un messaggio di errore, a seconda del valore del campo **Messaggio in caso di superamento del limite di credito** nella Scheda dettaglio **Limiti di credito**.

La proprietà **Escludi da gestione crediti** che impedisce la sospensione degli ordini cliente di Commerce si trova nell'intestazione dell'ordine cliente (**Vendita al dettaglio e commercio \> Clienti\> Tutti gli ordini cliente**). Se questa proprietà è impostata su **Sì** (il valore predefinito) per gli ordini cliente di Commerce, gli ordini verranno esclusi dal flusso di lavoro sospeso della gestione dei crediti. Sebbene la proprietà sia denominata **Escludi dalla gestione del credito**, il limite di credito definito verrà comunque utilizzato durante l'evasione dell'ordine. Gli ordini non verranno sospesi.

La possibilità di sospendere gli ordini cliente di Commerce in base a regole di blocco è pianificata per le future versioni di Commerce. Fino a che non sarà supportata, se devi forzare gli ordini cliente di Commerce a passare attraverso i nuovi flussi di gestione del credito, puoi personalizzare i seguenti file XML nella soluzione Visual Studio. Nei file, modifica la logica in modo che il flag **CredManExcludeSalesOrder** sia impostato su **No**. In questo modo, la proprietà **Escludi da gestione crediti** sarà impostata su **No** per impostazione predefinita per gli ordini cliente di Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Se il flag **CredManExcludeSalesOrder** è impostato su **No** e un cliente B2B può acquistare da punti vendita utilizzando l'applicazione POS, la registrazione delle transazioni cash and carry potrebbe non riuscire. Ad esempio, esiste una regola di blocco sul tipo di pagamento in contanti e il cliente B2B ha acquistato alcuni articoli nel punto vendita utilizzando contanti. In questo caso, l'ordine cliente risultante non verrà fatturato correttamente perché verrà sospeso. Pertanto, la registrazione avrà esito negativo. Per questo motivo, consigliamo di eseguire test end-to-end dopo aver implementato questa personalizzazione.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare un sito di e-commerce B2B](set-up-b2b-site.md)

[Gestire partner commerciali B2B utilizzando gerarchie di clienti](partners-customer-hierarchies.md)

[Gestione degli utenti partner commerciali sui siti di e-commerce B2B](manage-b2b-users.md)

[Impostare limiti di quantità di prodotti per i siti di e-commerce B2B](quantity-limits.md)

[SDK e aggiornamenti libreria dei moduli](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
