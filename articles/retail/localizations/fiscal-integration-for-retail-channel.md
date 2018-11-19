---
title: Integrazione fiscale per il canale di vendita al dettaglio
description: In questo argomento viene fornita una panoramica di integrazione fiscale per Retail POS.
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: it-it
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Integrazione fiscale per il canale di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica delle funzionalità di integrazione fiscale disponibili in Microsoft Dynamics 365 for Retail. La funzionalità di integrazione fiscale è un framework progettato per supportare le leggi fiscali locali che sono destinate per impedire la frode nel settore della vendita al dettaglio. Gli scenari comuni che possono essere coperti utilizzando l'integrazione fiscale sono:

- Stampare una ricevuta fiscale e darla al cliente.
- Proteggere l'invio delle informazioni relative alle vendite e ai resi eseguiti sul POS a un servizio esterno fornito dall'autorità competente.
- Utilizzare la protezione dei dati con una firma digitale autorizzata dall'autorità competente.

In questo argomento vengono fornite indicazioni per l'impostazione di integrazione fiscale in modo che gli utenti possano eseguire le attività seguenti. 

- Configurare i connettori fiscali, ovvero dispositivi o servizi fiscali utilizzati a scopo di registrazione fiscale come il salvataggio, le firme digitali e l'invio protetto dei dati fiscali.
- Configurare il fornitore di documenti, che definisce un metodo di output e un algoritmo di generazione dei documenti fiscali.
- Configurare il processo di registrazione fiscale, ovvero definire una sequenza di passaggi e un gruppo di connettori utilizzati in ogni passaggio.
- Assegnare i processi di registrazione fiscale ai profili funzionalità POS.
- Assegnare profili tecnici del connettore a profili hardware (per i connettori fiscali locali) o a profili funzionalità POS (per altri tipi di connettori fiscali).

## <a name="fiscal-integration-execution-flow"></a>Flusso di esecuzione di integrazione fiscale
Lo scenario seguente illustra il flusso comune di esecuzione di integrazione fiscale.

1. Inizializzazione del processo di registrazione fiscale.
  
   Una volta eseguite alcune azioni in cui la registrazione fiscale è necessaria, ad esempio dopo che una transazione di vendita al dettaglio è stata terminata, il processo di registrazione fiscale viene associato al profilo funzionalità POS corrente.

1. Ricerca di un connettore fiscale.
   
   Per ciascun passaggio di registrazione fiscale incluso nel processo di registrazione fiscale, il sistema abbina l'elenco dei connettori fiscali. Questi connettori hanno un profilo funzionale incluso nel gruppo specifico di connettori, con un elenco di connettori che hanno un profilo tecnico associato al profilo hardware corrente (per un tipo di connettori che corrisponde a **Locale** solo) o con il profilo funzionalità POS corrente (per altri tipi di connettore).
   
1. Eseguire l'integrazione fiscale.

   Il sistema esegue tutte le azioni necessarie definite da un assembly collegato al connettore trovato. Ciò avviene in conformità alle impostazioni del profilo funzionale e del profilo tecnico che sono state rilevati nel passaggio precedente per questo connettore.

## <a name="setup-needed-before-using-fiscal-integration"></a>Impostazione necessaria prima di utilizzare l'integrazione fiscale
Per utilizzare la funzionalità di integrazione fiscale, è necessario definire le seguenti impostazioni:

- La sequenza numerica nella pagina **Parametri di vendita al dettaglio** per il numero di profilo funzionale fiscale.
  
- Le sequenze numeriche nella pagina **Parametri condivisi di vendita al dettaglio** per i riferimenti seguenti:
  
  - Numero del profilo tecnico fiscale
  - Numero del gruppo di connettori fiscali
  - Numero del processo di registrazione

- Creare im **Connector fiscale** in **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Connettori fiscali** per ogni dispositivo o servizi che si prevede di utilizzare per scopi di integrazione fiscale.

-  Creare un **Fornitore di documenti fiscali** **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Fornitori di documenti fiscali** per tutti i connettori fiscali. Il mapping dei dati viene considerato parte del fornitore di documenti fiscali. Per impostare i mapping dei dati diversi per lo stesso connettore (ad esempio le normative specifiche di stato), è necessario creare diversi fornitori di documenti fiscali.

- Creare un **Profilo funzionale del connettore** in **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Profili funzionali del connettore** per ciascun fornitore di documenti fiscali.
  - Selezionare un nome di connettore.
  - Selezionare un fornitore di documenti.
  - Specificare impostazioni di aliquote IVA nella scheda **Impostazione servizio**.
  - Specificare il mapping di codici IVA e il mapping dei tipi di pagamento nella scheda **Mapping dei dati**.

  #### <a name="examples"></a>Esempi 

  |  | Formatta | Esempio | 
  |--------|--------|--------|
  | Impostazioni aliquote IVA | value : VATrate | 1 : 2000, 2 : 1800 |
  | Mapping codici IVA | VATcode : value | vat20 : 1, vat18 : 2 |
  | Mapping tipi di metodo di pagamento | TenderTyp : value | Cash : 1, Card : 2 |

- Creare **Gruppi di connettori fiscali** in **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Gruppo di connettori fiscali**. Un gruppo di connettori è un sottoinsieme dei profili funzionali collegati ai connettori fiscali che eseguono funzioni identiche e sono utilizzati nella stessa fase in un processo di registrazione fiscale.

   - Aggiungere profili funzionali al gruppo di connettori. Fare clic su **Aggiungi** nella pagina **Profili funzionali** e selezionare un numero di profilo.
   - Se si desidera sospendere l'utilizzo del profilo funzionale, impostare **Disattiva** su **Sì**. 
   
     Questa modifica ha effetto solo sul gruppo di connettori corrente. È possibile continuare a utilizzare lo stesso profilo funzionale in altri gruppi di connettori.

     >[!NOTE]
     > In un gruppo di connettori, ogni connettore fiscale può avere un solo profilo funzionale.

- Creare un **Profilo tecnico del connettore** in **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Profili tecnici del connettore** per ciascun connettore fiscale.
  - Selezionare un nome di connettore.
  - Selezionare un tipo di connettore: 
      - **Locale** - Impostare questo tipo per dispositivi fisici o applicazioni installate in un computer locale.
      - **Interno** - Impostare questo tipo per i dispositivi e i servizi fiscali connessi al Server Retail.
      - **Esterno** - Per i servizi fiscali esterni come un portale Web fornito da un ufficio tributario.
    
  - Specificare le impostazioni della scheda **Connessione**.

      
 >[!NOTE]
 > Una versione aggiornata di una configurazione che è stata precedentemente caricata verrà caricata per i profili sia funzionali sia tecnici. Se un connettore o un fornitore di documenti appropriato è già in uso, verrà inviata una notifica. Per impostazione predefinita, tutte le modifiche che sono state create manualmente nei profili funzionali e tecnici verranno archiviate. Per sostituire questi profili con il set predefinito di parametri di una configurazione, fare clic su **Aggiorna** nella pagina **Profili funzionali del connettore** e nella pagina **Profili tecnici del connettore**.
 
- Creare un **Processo di registrazione fiscale** in **Vendita al dettaglio > Impostazione canale > Integrazione fiscale > Processi di registrazione fiscale** per ogni processo univoco dell'integrazione fiscale. Un processo di registrazione è definito dalla sequenza di passaggi di registrazione e dal gruppo di connettori utilizzato in ogni passaggio. 
  
  - Aggiungere i passaggi di registrazione al processo:
      - Fare clic su **Aggiungi**.
      - Selezionare un tipo di connettore.
      
      >[!NOTE]
      > Questo campo definisce dove il sistema cerca il connettore in un profilo tecnico, nei profili hardware per il tipo di connettore **Locale** o nei profili funzionalità POS per gli altri tipi di connettore fiscale.
      
   - Selezionare un gruppo di connettori.
   
     >[!NOTE]
     > Scegliere **Convalida** per verificare l'integrità della struttura del processo di registrazione. Si consiglia di eseguire convalide nei seguenti casi:
       >- Per un nuovo processo di registrazione dopo che tutte le impostazioni vengono completate, inclusi l'associazione ai profili funzionalità POS e ai profili hardware.
       >- Dopo aver apportato aggiornamenti a un processo di registrazione esistente.

-  Associare i processi di registrazione fiscale ai profili funzionalità POS in **Vendita al dettaglio > Impostazione canale > Impostazioni POS > Profili POS > Profili funzionalità**.
   - Fare clic su **Modifica** e selezionare **Numero processo** nella scheda **Processo di registrazione fiscale**.
- Associare i profili tecnici del connettore ai profili hardware in **Vendita al dettaglio >  Impostazioni canale > Impostazioni POS > Profili POS > Profili hardware**.
   - Fare clic su **Modifica**, quindi fare clic su **Nuovo** nella scheda **Profilo tecnico fiscale**.
   - Selezionare un profilo tecnico del connettore nel campo **Numero profilo**.
   
     >[!NOTE]
     > È possibile aggiungere più profili tecnici a un profilo hardware. Tuttavia, ciò non è supportato se un profilo hardware contiene più di un'intersezione con qualsiasi gruppo di connettori. Per evitare le impostazioni non corrette, è consigliabile convalidare il processo di registrazione dopo l'aggiornamento di tutti i profili hardware.

