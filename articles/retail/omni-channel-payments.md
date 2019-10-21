---
title: Panoramica sui pagamenti omnicanale
description: In questo argomento viene fornita una panoramica dei pagamenti omnicanale in Dynamics 365 Retail.
author: rubendel
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 8.1.3
ms.openlocfilehash: b16b0cedaa2b908d2707eb7076f82f3513d00b62
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017576"
---
# <a name="omni-channel-payments-overview"></a>Panoramica sui pagamenti omnicanale

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dei pagamenti omnicanale in Dynamics 365 Retail. Include un elenco completo degli scenari supportati, informazioni su funzionalità, impostazione e risoluzione dei problemi nonché descrizioni di problemi tipici.

## <a name="key-terms"></a>Termini importanti

| Termine | Descrizione |
|---|---|
| Token  | Una stringa di dati che un sistema di elaborazione dei pagamenti fornisce come riferimento. I token possono rappresentare numeri di carte di pagamento, autorizzazioni di pagamento e acquisizioni di pagamento precedenti. I token sono importanti in quanto consentono di mantenere dati riservati al di fuori del sistema POS. Talvolta sono denominati *riferimenti*. |
| Token carta di credito | Un token che un sistema di elaborazione dei pagamenti fornisce per l'archiviazione nel sistema POS. Un token carta di credito può essere utilizzato solo dall'esercente che lo riceve. I token carta di credito sono a volte denominati *riferimenti di carte di credito*. |
| Token di autorizzazione | Un ID univoco che un sistema di elaborazione dei pagamenti fornisce come parte della risposta che invia a un sistema POS dopo questo esegue una richiesta di autorizzazione. Un token di autorizzazione può essere utilizzato successivamente se al sistema di elaborazione viene richiesto di eseguire azioni come lo storno o l'annullamento dell'autorizzazione. Tuttavia, è utilizzato soprattutto per acquisire fondi quando un ordine viene evaso o una transazione viene finalizzata. I token di autorizzazione sono a volte denominati *riferimenti di autorizzazione*. |
| Token di acquisizione | Un riferimento che un sistema di elaborazione dei pagamenti fornisce a un sistema POS quando un pagamento viene finalizzato o acquisito. Il token di acquisizione può quindi essere utilizzato per fare riferimento all'acquisizione di pagamento nelle operazioni successive, ad esempio richieste di rimborso. | 
| Carta non assente | Un termine che fa riferimento alle transazioni di pagamento dove una carta fisica non viene presentata. Ad esempio, queste transazioni possono verificarsi in scenari di e-commerce o servizio clienti. Per queste transazioni, le informazioni correlate al pagamento vengono immesse manualmente su un sito Web di e-commerce, in un flusso di servizio clienti, nel POS o nel terminale di pagamento. |
| Carta presente | Un termine che fa riferimento alle transazioni di pagamento in cui una carta fisica viene presentata e utilizzata in un terminale di pagamento connesso al sistema POS di Microsoft Dynamics 365. |

## <a name="overview"></a>Panoramica

In genere, il termine *pagamenti omnicanale* descrive la possibilità di creare un ordine in un canale e di evaderlo in un altro canale. La chiave al supporto del pagamento omnicanale è mantenere i dettagli del pagamento insieme agli altri dettagli dell'ordine e quindi utilizzare tali dettagli quando l'ordine viene richiamato o elaborato in un altro canale. Un esempio classico è lo scenario "Acquista online, preleva nel punto vendita". In questo scenario, i dettagli di pagamento vengono aggiunti quando l'ordine viene creato online. Vengono quindi richiamati nel POS per addebitare la carta di pagamento del cliente al momento del ritiro. 

Tutti gli scenari descritti in questo argomento possono essere implementati mediante il kit SDK Pagamenti standard fornito con Retail. Il [connettore pagamenti di Dynamics 365 per Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3) fornisce un'implementazione predefinita di ogni scenario descritto qui. 

### <a name="prerequisites"></a>Prerequisiti

Ogni scenario descritto in questo argomento richiede un connettore pagamenti che supporta i pagamenti omnicanale. Anche il connettore Adyen predefinito può essere utilizzato in quanto supporta gli scenari resi disponibili mediante il kit SDK Pagamenti. Per ulteriori informazioni sull'implementazione di connettori pagamenti e su Retail SDK in generale, visitare l'[home page di vendita al dettaglio per professionisti IT e sviluppatori](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/dev-retail-home-page#payment-connectors).

#### <a name="supported-versions"></a>Versioni supportate

Le funzionalità di pagamento omnicanale descritte in questo argomento sono state rilasciate nella versione 8.1.3 di Microsoft Dynamics 365 for Retail. 

#### <a name="card-present-and-card-not-present-connectors"></a>Connettori "Carta presente" e "Carta non presente"

Il kit SDK di pagamenti utilizza due set di API per i pagamenti. Il primo set di API è denominato **iPaymentProcessor**. È utilizzato per implementare i connettori pagamenti "Carta non presente" che possono essere utilizzati in servizi clienti e con la piattaforma di e-commerce di Microsoft Dynamics. Per ulteriori informazioni sull'interfaccia **iPaymentProcessor**, vedere il white paper [Implementazione di un connettore pagamenti e un dispositivo di pagamento](https://download.microsoft.com/download/4/D/7/4D7C6B05-0C23-4C6C-BA13-AB62ED08AA61/The%20Guide%20to%20Implementing%20Payment%20Connector%20and%20Payment%20Device.docx) relativo ai pagamenti. 

Il secondo set di API è denominato **iNamedRequestHandler**. Supporta l'implementazione delle Integrazioni di pagamento "carta esistente" che utilizzano un terminale di pagamento. Per ulteriori informazioni sull'interfaccia **iNamedRequestHandler**, vedere [Creare un'integrazione di pagamento per un terminale di pagamento](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension). 

### <a name="setup-and-configuration"></a>Impostazione e configurazione

I seguenti componenti e passaggi di impostazione sono necessari:

- **integrazione e-commerce :** un'integrazione con Retail è necessaria per supportare gli scenari in cui un ordine ha origine da una vetrina virtuale online. Per ulteriori informazioni sul kit SDK Retail e-commerce, vedere [Kit SDK della piattaforma e-commerce](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/ecommerce-platform-sdk). In un ambiente dimostrativo, la vetrina virtuale di riferimento supporta scenari di pagamento omnicanale. 
- **Configurazione pagamenti online:** l'impostazione del canale online deve includere un connettore pagamenti che è stato aggiornato per supportare i pagamenti omnicanale. In alternativa, è possibile utilizzare il connettore pagamenti predefinito. Per informazioni su come configurare il connettore pagamenti Adyen per punti vendita online, vedere [Connector pagamenti Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3#e-commerce). Oltre alla procedura di impostazione e-commerce descritta in quell'argomento, il parametro **Consenti salvataggio informazioni di pagamento in e-commerce** deve essere impostato su **True** nelle impostazioni per il connettore Adyen. 
- **Configurazione pagamenti omnicanale:** nel back office, andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di vendita al dettaglio**. Quindi, nella scheda **Pagamenti omnicanale**, impostare l'opzione **Usa pagamenti omnicanale** su **Sì**.
- **Servizi di pagamento:** il servizio clienti utilizza il connettore pagamenti predefinito nella pagina **Servizi di pagamento** per elaborare i pagamenti. Per supportare gli scenari, ad esempio "Acquista nel servizio clienti, preleva nel punto vendita", questo connettore pagamenti predefinito deve essere un connettore pagamenti Adyen o un connettore pagamenti che soddisfa i requisiti di implementazione dei pagamenti omnicanale.
- **Servizio EFT:** i pagamenti mediante un terminale di pagamento devono essere impostati nella Scheda dettaglio **Servizio EFT** del profilo hardware. Il connettore Adyen supporta gli scenari di pagamenti omnicanale. Anche altri connettori pagamenti che supportano l'interfaccia **iNamedRequestHandler** possono essere utilizzati se supportano i pagamenti omnicanale.
- **Disponibilità connettori pagamenti:** quando un ordine viene richiamato, le righe del metodo di pagamento richiamate insieme all'ordine includono il nome del connettore pagamenti utilizzato per creare le autorizzazioni associate a tale ordine. Quando l'ordine viene evaso, il kit SDK di pagamenti tenta di utilizzare lo stesso connettore utilizzato per creare l'autorizzazione originale. Di conseguenza, un connettore pagamenti con le stesse proprietà esercente deve essere disponibile per l'acquisizione. 
- **Tipi di carta:** per un corretto funzionamento degli scenari omnicanale, ogni canale deve avere la stessa impostazione per i tipi di metodi di pagamento utilizzabile per l'omnicanale. Questa impostazione include gli ID metodo di pagamento e gli ID tipo di carta. Ad esempio, se l'ID del tipo di metodo di pagamento **Carte** è **2** nell'impostazione del punto vendita online, deve avere lo stesso ID nell'impostazione del punto vendita al dettaglio. Lo stesso requisito si applica agli ID tipi di carta. Se il numero di carta **12** è impostato su **VISA** nel punto vendita online, lo stesso ID deve essere impostato per il punto vendita al dettaglio. 

### <a name="basic-principle-supporting-omni-channel-payments"></a>Principio di base per il supporto di pagamenti omnicanale

I connettori pagamenti e i sistemi di elaborazione dei pagamenti utilizzano token, o riferimenti, per fare riferimento alle interazioni correlate ai pagamenti con carta di credito. Ad esempio, quando viene richiesta un'autorizzazione di pagamento, viene fornito un riferimento a tale autorizzazione. Di conseguenza, è possibile fare riferimento all'autorizzazione in seguito, quando i fondi vengono acquisiti al momento dell'evasione. Questa autorizzazione è specifica all'esercente, al connettore pagamenti e al sistema di elaborazione dei pagamenti. 

Se un ordine creato online viene prelevato presso il punto vendita, gli stessi dettagli relativi al pagamento di quell'ordine devono essere richiamati e utilizzati. Quando vengono forniti i dettagli originali nell'ambito della richiesta di acquisizione di un pagamento a fronte dell'autorizzazione originale, il sistema di elaborazione dei pagamenti sarà in grado di gestire la richiesta e acquisire il pagamento. 

Per fare riferimento correttamente all'ordine online, deve essere disponibile anche un connettore pagamenti "carta non presente" che supporta lo stesso sistema di elaborazione. In questo caso, il sistema POS può avere un sistema di elaborazione per pagamenti "carta presente", ma anche accedere ad altri connettori pagamenti in modo da evadere ordini creati in altri canali utilizzando differenti sistemi di elaborazione dei pagamenti. 

## <a name="supported-scenarios"></a>Scenari supportati

I seguenti scenari di pagamento omnicanale sono supportati:

- Acquista online, preleva nel punto vendita
- Acquista nel servizio clienti, preleva nel punto vendita
- Acquista nel punto vendita A, preleva nel punto vendita B
- Acquista nel punto vendita A, spedisci a cliente

Sono supportate anche variazioni di questi scenari. Ad esempio, un ordine online può includere le righe che verranno spedite al cliente e quelle che saranno prelevate in un punto vendita. Tutte le opzioni di evasione degli ordini sono supportate tramite pagamenti omnicanale. 

Nelle sezioni seguenti vengono descritte le procedure per ogni scenario e viene indicato come eseguire lo scenario utilizzando dati dimostrativi. 

### <a name="buy-online-pick-up-in-store"></a>Acquista online, preleva nel punto vendita

Prima di iniziare, assicurarsi che i seguenti prerequisiti siano soddisfatti:

- Si dispone di una vetrina virtuale di riferimento in cui il connettore pagamenti Adyen viene configurato.
- L'opzione **Pagamenti omnicanale** nella pagina **Parametri condivisi di vendita al dettaglio** è impostata su **True**.
- Il connettore pagamenti Adyen è configurato per il registratore di cassa POS di Houston.

Attenersi alla seguente procedura per eseguire lo scenario.

1. Nella vetrina virtuale di riferimento, creare un ordine per il prelievo nel punto vendita. Assicurarsi di selezionare il punto vendita **Houston**. 
2. Eseguire la procedura di check out e pagare utilizzando un numero di carta di credito di prova. È possibile trovare numeri di carta di credito di prova nella [pagina dei numeri di carta di credito di prova Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description).
3. In Retail, utilizzare il processo batch **Sincronizza ordini** e la programmazione distribuzione **P-001** per creare gli ordini nel back office.
4. Nel POS, nella pagina di benvenuto, selezionare l'operazione **Ordini da prelevare** per visualizzare gli ordini per il prelievo nel punto vendita. 
5. Selezionare una o più righe dall'ordine creato nella vetrina virtuale di riferimento, quindi selezionare **Preleva**.

    L'ordine viene recuperato dal back office. 

6. Quando i dettagli della riga ordine vengono recuperati dal back office e viene rilevato un pagamento con carta che può essere utilizzato per l'omnicanale, viene segnalato che un metodo di pagamento è disponibile.
7. Selezionare **Usa metodo di pagamento disponibile** per completare la transazione utilizzando i dettagli della scheda immessi nella vetrina virtuale di riferimento.

    Le righe ordine vengono caricate nella pagina delle transazioni e il saldo esigibile è 0 (zero). 

8. Selezionare la scheda **Pagamenti** per visualizzare la riga del metodo di pagamento acquisita dall'ordine online. 
9. Selezionare qualsiasi metodo di pagamento per completare la transazione. 

### <a name="buy-in-call-center-pick-up-in-store"></a>Acquista nel servizio clienti, preleva nel punto vendita

1. In Retail, nella pagina **Servizio clienti**, immettere **Karen Berg** nella barra di ricerca, quindi selezionare **Cerca**. 
3. Selezionare **Karen Berg** nei risultati della ricerca.
4. Dopo il caricamento di Karen nella pagina **Servizio clienti**, selezionare **Nuovo ordine cliente**.
5. Nella nuova pagina degli ordini cliente, selezionare **Intestazione** per visualizzare l'intestazione dell'ordine. 
6. Nella pagina **Intestazione ordine**, impostare il sito su **Centrale** e il magazzino su **Houston**.
7. Nella scheda **Fornisci**, impostare il campo **Modalità di consegna** su **60** per il prelievo cliente.
8. Selezionare **Righe** e quindi aggiungere una o più righe all'ordine. 
9. Selezionare **Completa** per immettere il flusso di completamento dell'ordine.
10. Scorrere fino alla sezione dei pagamenti, selezionare **Aggiungi**, quindi selezionare una riga in cui il tipo di metodo di pagamento è impostato su **Carte**. 
11. Selezionare il segno più (**+**) per aggiungere un pagamento con carta. 
12. Immettere i dettagli di un numero di carta di credito di prova trovato nella [pagina dei numeri di carta di credito di prova Adyen](https://docs.adyen.com/development-resources/test-cards/test-card-numbers/#description), quindi selezionare **OK**.

    > [!NOTE]
    > Se la marca della carta immessa differisce da quella selezionata all'inizio del pagamento, il pagamento verrà comunque effettuato. Tuttavia, verrà registrato nei conti che vengono mappati alla marca della carta selezionata nel passaggio 10.

12. Scegliere di nuovo **OK** per chiudere la finestra di dialogo **Pagamenti completamento ordine**.
13. Nella pagina **Riepilogo ordine cliente**, seleziona **Invia**.
14. Nel POS, nella pagina di benvenuto, selezionare l'operazione **Ordini da prelevare** per visualizzare gli ordini per il prelievo nel punto vendita. 
15. Selezionare una o più righe dall'ordine creato nella vetrina virtuale di riferimento, quindi selezionare **Preleva**.

    L'ordine viene recuperato dal back office. 

16. Quando i dettagli della riga ordine vengono recuperati dal back office e viene rilevato un pagamento con carta che può essere utilizzato per l'omnicanale, viene segnalato che un metodo di pagamento è disponibile.
17. Selezionare **Usa metodo di pagamento disponibile** per completare la transazione utilizzando i dettagli della scheda immessi nella vetrina virtuale di riferimento.

    Le righe ordine vengono caricate nella pagina delle transazioni e il saldo esigibile è 0 (zero).

18. Selezionare la scheda **Pagamenti** per visualizzare la riga del metodo di pagamento acquisita dall'ordine online. 
19. Selezionare qualsiasi metodo di pagamento per completare la transazione. 

### <a name="buy-in-store-a-pick-up-in-store-b"></a>Acquista nel punto vendita A, preleva nel punto vendita B

1. Avviare il POS per il punto vendita di Houston.
2. Nella pagina **Transazione**, aggiungere Karen Berg alla transazione mediante il tastierino numerico per immettere **2001**.
3. Aggiungere una o più righe alla transazione.
4. Selezionare **Ordini** per visualizzare le opzioni relative agli ordini.
5. Selezionare **Preleva tutto**, quindi quando verrà richiesto, selezionare **Ordine cliente**.
6. Nella barra di ricerca, immettere **Seattle**quindi selezionare il punto vendita **Seattle** per il prelievo. 
7. Selezionare **OK** per accettare la data corrente come data di prelievo.
9. Selezionare **Pagamento con carta** per avviare il pagamento.
10. Scegliere il pagamento con carta per l'importo dovuto per il deposito. 
11. Completare il pagamento del deposito nel terminale di pagamento. 
12. Dopo il pagamento del deposito, selezionare l'opzione per utilizzare la stessa carta per l'evasione e attendere il completamento dell'ordine. 
13. Avviare il POS per il punto vendita di Seattle.
14. Nel POS, nella pagina di benvenuto, selezionare l'operazione **Ordini da prelevare** per visualizzare gli ordini per il prelievo nel punto vendita. 
15. Selezionare una o più righe dall'ordine creato nella vetrina virtuale di riferimento, quindi selezionare **Preleva**.

    L'ordine viene recuperato dal back office. 

16. Quando i dettagli della riga ordine vengono recuperati dal back office e viene rilevato un pagamento con carta che può essere utilizzato per l'omnicanale, viene segnalato che un metodo di pagamento è disponibile.
17. Selezionare **Usa metodo di pagamento disponibile** per completare la transazione utilizzando i dettagli della scheda immessi nella vetrina virtuale di riferimento.

    Le righe ordine vengono caricate nella pagina delle transazioni e il saldo esigibile è 0 (zero).

18. Selezionare la scheda **Pagamenti** per visualizzare la riga del metodo di pagamento acquisita dall'ordine online. 
19. Selezionare qualsiasi metodo di pagamento per completare la transazione. 

### <a name="buy-in-store-a-ship-to-customer"></a>Acquista nel punto vendita A, spedisci a cliente

1. Avviare il POS per il punto vendita di Houston.
2. Nella pagina **Transazione**, aggiungere Karen Berg alla transazione mediante il tastierino numerico per immettere **2001**.
3. Aggiungere una o più righe alla transazione.
4. Selezionare **Ordini** per visualizzare le opzioni relative agli ordini.
5. Selezionare **Preleva tutto**, quindi quando verrà richiesto, selezionare **Ordine cliente**.
6. Nella barra di ricerca, immettere **Seattle**quindi selezionare il punto vendita **Seattle** per il prelievo. 
7. Selezionare **OK** per accettare la data corrente come data di prelievo.
8. Selezionare **Pagamento con carta** per avviare il pagamento.
9. Scegliere il pagamento con carta per l'importo dovuto per il deposito. 
10. Completare il pagamento del deposito nel terminale di pagamento. 
11. Dopo il pagamento del deposito, selezionare l'opzione per utilizzare la stessa carta per l'evasione e attendere il completamento dell'ordine.

Quando l'ordine viene prelevato, imballato e fatturato nel back office, i dettagli del pagamento specificati nel POS verranno utilizzati per acquisire i fondi per la merce spedita al cliente. 

## <a name="scenario-details"></a>Dettagli dello scenario

Oltre agli scenari di base appena descritti, sono stati apportati vari miglioramenti al kit SDK di pagamenti per supportare pagamenti omnicanale. 

### <a name="pos"></a>POS

#### <a name="single-swipedip-for-customer-orders"></a>Singolo passaggio di carta per ordini cliente

Prima dell'implementazione della funzionalità Pagamenti omnicanale, quando si creavano ordini cliente che includevano depositi nel POS, ai clienti veniva richiesto di passare la loro carta due volte: una volta per pagare il deposito e una volta per eseguire la tokenizzazione della carta per l'evasione dell'ordine. Quando la funzionalità di tokenizzazione omnicanale è attivata, i clienti devono passare la loro carta una sola volta per pagare il deposito e autorizzare l'importo dovuto che verrà evaso in un secondo momento. Al momento dell'evasione, i fondi autorizzati vengono acquisiti. Prima dell'implementazione della funzionalità di tokenizzazione omnicanale, solo un token carta di credito ricorrente veniva creato per l'evasione dell'ordine. Di conseguenza, i fondi per l'evasione in sospeso non erano autorizzati e poiché non erano mantenuti per quell'acquisto specifico, era meno probabile che potessero essere acquisiti in un secondo momento.

> [!NOTE]
> Un singolo passaggio della carta non è supportato nella versione 8.1.3 di Retail. Gli ordini cliente nella versione 8.1.3 utilizzano lo stesso flusso utilizzato prima dell'implementazione della funzionalità di tokenizzazione omnicanale. 

### <a name="cards-that-cant-issue-recurring-card-tokens"></a>Carte che non possono generare token carte di credito ricorrenti

Alcune carte non possono essere utilizzate per i pagamenti omnicanale in quanto non supportano l'emissione di token carte di credito ricorrenti. Quando un ordine viene creato nel POS, se il deposito viene pagato mediante una scheda che non supporta token carta di credito ricorrenti, viene utilizzato il flusso di tokenizzazione di carte precedente. Di conseguenza, un cliente che intende fornire un pagamento che verrà utilizzato per l'evasione dell'ordine deve presentare una seconda carta. Se la seconda carta non supporta token carta di credito ricorrenti, l'azione di tokenizzazione verrà declinata e al cassiere viene richiesto di richiedere al cliente un'altra carta. 

### <a name="using-a-different-card"></a>Utilizzo di un'altra carta

Un cliente che si reca al punto vendita per il prelievo dell'ordine ha la possibilità di utilizzare un'altra carta. Quando il cassiere vede la richiesta **Usa metodo di pagamento disponibile** al momento del prelievo dell'ordine, può chiedere al cliente se desidera utilizzare la stessa scheda. Se il cliente ha perso la carta utilizzata per creare l'ordine e desidera pagare l'ordine utilizzando un'altra carta, il cassiere può selezionare **Usa metodo di pagamento diverso**. Se il cliente ritorna in seguito per prelevare altri articoli per lo stesso ordine e l'autorizzazione della scheda originale è ancora valida, il cassiere può ancora chiedere al cliente se desidera utilizzare quella carta.

### <a name="invalid-authorizations"></a>Autorizzazioni non valide

Se la carta utilizzata per creare un ordine non è più valida, quando i prodotti vengono selezionati per il prelievo, la richiesta di acquisizione del pagamento non riuscirà. Il connettore pagamenti POS tenterà quindi di creare una nuova autorizzazione e acquisizione utilizzando gli stessi dettagli della carta. Se la nuova autorizzazione o acquisizione ha esito negativo, al cassiere verrà notificato che il pagamento non è stato elaborato. Il cassiere deve quindi ottenere un nuovo pagamento dal cliente. 

### <a name="multiple-available-payments"></a>Molteplici pagamenti disponibili

Quando viene prelevato un ordine con più metodi di pagamento e più righe, il cassiere dapprima vede la richiesta **Usa metodo di pagamento disponibile**. Se sono disponibili più carte, quando il cassiere seleziona **Usa metodo di pagamento disponibile**, le righe del pagamento con carta verranno acquisite fino al raggiungimento del saldo per le merci attualmente prelevate. Il cassiere non avrà l'opzione di selezionare la carta che deve essere utilizzata per le merci che vengono prelevate. 

## <a name="related-topics"></a>Argomenti correlati

- [Domande frequenti sui pagamenti](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/payments-retail)
- [Connettore pagamenti di Dynamics 365 per Adyen](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/adyen-connector?tabs=8-1-3)
