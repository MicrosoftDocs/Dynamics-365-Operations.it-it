---
title: Creare cataloghi Commerce per siti B2B
description: Questo articolo descrive come creare cataloghi di Commerce per i siti business-to-business (B2B) Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7d4ed3e2a76924c2c3c0ba55e21ba648e8da7b76
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136828"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Creare cataloghi Commerce per siti B2B

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare cataloghi di prodotti di Commerce per i siti business-to-business (B2B) Microsoft Dynamics 365 Commerce. Per le risposte alle domande frequenti sui cataloghi di Commerce per i siti B2B, vedi [Domande frequenti sui cataloghi di Commerce per B2B](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Questo articolo si applica a Dynamics 365 Commerce versione 10.0.27 e successive.

È possibile utilizzare i cataloghi di Commerce per identificare i prodotti che si desidera offrire nei negozi online B2B. Quando si crea un catalogo, è necessario identificare i negozi online in cui vengono offerti i prodotti, aggiungere i prodotti che si desidera includere e migliorare le offerte di prodotti aggiungendo i dettagli di vendita. È possibile creare più cataloghi per ogni negozio online B2B, come mostrato nella figura seguente.

![Anteprima dei cataloghi di prodotti di Commerce.](./media/Commerce_Catalogs.png)

I cataloghi di prodotti di Commerce consentono di definire le seguenti informazioni:

- **Tipo di catalogo**: configura il valore come **B2B**. Puoi definire le proprietà specifiche del catalogo B2B, quali la gerarchia di navigazione, una gerarchia personalizzata e metadati degli attributi per il catalogo. 
- **Gerarchia di navigazione specifica del catalogo** – Le organizzazioni possono creare una struttura di categorie distinta per il loro catalogo specifico.
- **Metadati degli attributi specifici del catalogo** – Gli attributi contengono i dettagli sul prodotto. Assegnando gli attributi a una categoria della gerarchia di navigazione, è possibile definire valori per quegli attributi a livello di prodotti assegnati a quella categoria. Le organizzazioni possono quindi effettuare le seguenti attività:

    - Definire i valori degli attributi specifici del catalogo.
    - Controllare la visibilità degli attributi a livello di catalogo.
    - Selezionare i criteri di affinamento specifici per un singolo catalogo.

- **Canali** – Le organizzazioni possono associare più di un canale online B2B a un catalogo. Il supporto end-to-end per i cataloghi è attualmente disponibile solo per i negozi online B2B.
- **Gerarchie di clienti** – Per un determinato canale B2B, le organizzazioni possono rendere disponibile un catalogo specifico ai partner B2B selezionati associando le gerarchie dei clienti a quel catalogo.
- **Gruppi di prezzi** – È possibile configurare prezzi e promozioni specifici per un determinato catalogo. Questa capacità è fondamentale per definire un catalogo per un canale B2B. I gruppi di prezzi per i cataloghi consentono alle organizzazioni di rendere disponibili i prodotti alle organizzazioni B2B previste e di applicare i prezzi e gli sconti preferiti. I clienti B2B che ordinano da un catalogo configurato possono beneficiare di prezzi speciali e promozioni dopo aver effettuato l'accesso a un sito Commerce B2B. Per configurare prezzi specifici per il catalogo, seleziona **Gruppi di prezzi** nella scheda **Cataloghi** per collegare uno o più gruppi di prezzi al catalogo. Tutti gli accordi commerciali, i giornali di registrazione rettifiche prezzo e gli sconti avanzati che sono stati collegati allo stesso gruppo di prezzi verranno applicati quando i clienti ordinano dal catalogo. Gli sconti avanzati includono sconti su soglia, quantità, unità e corrispondenza. Per ulteriori informazioni sui gruppi di prezzi, vedi [Gruppi di prezzi](price-management.md#price-groups).

> [!NOTE]
> Questa funzionalità è disponibile a partire da Dynamics 365 Commerce versione 10.0.27. Per configurare le configurazioni specifiche del catalogo, come la gerarchia di navigazione e la gerarchia dei clienti, in Commerce headquarters, vai all'area di lavoro **Gestione funzionalità** (**Amministrazione di sistema \> Aree di lavoro \> Gestione funzionalità**), abilita la funzionalità **Abilita l'utilizzo di più cataloghi nei canali di vendita al dettaglio**, quindi esegui il processo **1110 CDX**. Quando abiliti questa funzionalità, tutti i cataloghi esistenti usati per i negozi POS o per un call center verranno contrassegnati come **Tipo di catalogo = B2C** nella pagina **Cataloghi**. Solo i cataloghi nuovi ed esistenti contrassegnati come **Tipo di catalogo = B2C** sono applicabili ai negozi POS e a un call center. 

## <a name="b2b-catalog-process-flow"></a>Flusso di processo del catalogo B2B

Il processo di creazione ed elaborazione di un catalogo prevede quattro fasi generali. Ogni passaggio è spiegato in dettaglio nella sezione successiva.

> [!NOTE]
> Prima di procedere, verifica che il catalogo sia contrassegnato come **Tipo di catalogo = B2B**.

1. **[Configurazione](#configure-the-catalog)**

    - Associa la gerarchia di navigazione.
    - Specifica le date di validità e di scadenza, se applicabili.
    - Aggiungi e classifica i prodotti.
    - Associa gruppi di prezzi.
    - Associa una gerarchia di clienti specifica per le tue organizzazioni B2B. 
    - Associa il gruppo di attributi di dimensione predefinito per criteri di affinamento quali dimensione, stile e colore.
    - Imposta i metadati di attributi.

1. **[Convalida](#validate-the-catalog)** – In questo passaggio, esegui le regole di convalida che impongono un comportamento specifico. Di seguito sono riportati alcuni esempi.

    - Assicurati che non ci siano prodotti non categorizzati.
    - Assicurati che tutti gli articoli assortiti per ciascun canale siano associati a un catalogo.

1. **[Approvazione](#approve-the-catalog)**
1. **[Pubblicazione](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Impostare il catalogo

Usa le informazioni in questa sezione per impostare il tuo catalogo.

### <a name="configure-the-catalog"></a>Configurare il catalogo

In Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi** per configurare il tuo catalogo.

Quando si crea un nuovo catalogo, è necessario prima associarlo a uno o più canali. Per creare il catalogo possono essere utilizzati solo gli articoli collegati al canale selezionato [assortimenti](/dynamics365/unified-operations/retail/assortments). Per associare il catalogo a uno o più canali, seleziona **Aggiungi** sulla scheda dettaglio **Canali di Commerce** della pagina **Impostazione catalogo**. Verifica che il catalogo sia contrassegnato come **Tipo di catalogo = B2B**.

#### <a name="associate-the-navigation-hierarchy"></a>Associare la gerarchia di navigazione

Per aggiungere prodotti a un catalogo, è necessario selezionare una gerarchia di navigazione. La gerarchia di navigazione supporta la struttura di categorie del catalogo. È necessario selezionare una delle gerarchie di navigazione associate ai canali di vendita al dettaglio selezionati nella Scheda dettaglio **Canali di commercio** della pagina **Impostazione catalogo**. Per associare una gerarchia di navigazione predefinita a ciascuno dei tuoi canali, vai a **Vendita al dettaglio e commercio \> Impostazione canale \> Categorie di canali e attributi di prodotto**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Specificare una data di validità e una data di scadenza

Per specificare le date di validità e di scadenza per un catalogo, seleziona il nodo superiore della gerarchia del catalogo per tornare alla visualizzazione dell'intestazione del catalogo principale. Quindi nella scheda dettaglio **Generale** configura le date di validità e di scadenza come richiesto.

#### <a name="add-and-categorize-products"></a>Aggiungere e classificare i prodotti

Per configurare i prodotti da aggiungere al catalogo in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Quindi, nella scheda **Cataloghi**, seleziona **Aggiungi prodotti**.

In alternativa, seleziona un nodo nella gerarchia di navigazione. Potrai quindi aggiungere i prodotti direttamente a una categoria nel catalogo.

#### <a name="associate-price-groups"></a>Associare gruppi di prezzi

Per configurare i prodotti da aggiungere al catalogo in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Quindi, nella scheda **Cataloghi**, seleziona **Aggiungi prodotti**. 

I prodotti aggiunti a un catalogo dal nodo radice della gerarchia di navigazione mediante la selezione di **Aggiungi prodotti** nel riquadro Azioni erediteranno le relative categorie se anche la gerarchia di navigazione di origine è associata al catalogo. Le modifiche alle categorie apportate nella gerarchia di navigazione di origine verranno immediatamente applicate ai cataloghi. Per aggiornare i canali dovrai pubblicare nuovamente i cataloghi.

In alternativa, puoi selezionare un nodo nella gerarchia di navigazione e aggiungere i prodotti direttamente a un categoria selezionata nel catalogo. 

Quando aggiungi dei prodotti, verrà resa disponibile l'opzione **Includi automaticamente tutte le varianti quando è selezionata solo la rappresentazione generale prodotto**. Per evitare che vengano incluse tutte le varianti, selezionare almeno una variante dalla rappresentazione generale prodotto. 

> [!NOTE]
> Se scegli di includere automaticamente tutte le varianti in un'ampia selezione di rappresentazioni generali prodotti, i tempi di elaborazione potrebbero risultare estremamente lunghi. Per le selezioni più ampie, consigliamo di selezionare **Includi tutte le varianti** nel riquadro Azioni della pagina del catalogo per eseguire l'operazione in modalità batch. Se hai incluso soltanto la rappresentazione generale prodotto nel catalogo senza includere alcune varianti, la selezione delle varianti potrebbe non essere disponibile quando accedi a una pagina di dettagli del prodotto. 

Per configurare i prezzi specifici del catalogo, è necessario collegare uno o più gruppi di prezzi al catalogo. Per associare gruppi di prezzi a un catalogo in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Poi, sulla scheda **Cataloghi** sotto **Prezzi**, seleziona **Gruppi di prezzi**. Tutti gli accordi commerciali, i giornali di registrazione rettifiche prezzo e gli sconti avanzati (soglia, quantità, unità e corrispondenza) che sono stati collegati allo stesso gruppo di prezzi verranno applicati quando i clienti ordinano dal catalogo.

Per ulteriori informazioni sui gruppi di prezzi, vedi [Gruppi di prezzi](price-management.md#price-groups).

> [!NOTE]
> Non è possibile creare un nuovo gruppo di prezzi dalla pagina **Tutti i cataloghi**. Devi crearlo dalla pagina **Tutti i gruppi di prezzi**. Devi quindi associarlo al catalogo nella pagina **Tutti i cataloghi**.

#### <a name="associate-a-customer-hierarchy"></a>Associare una gerarchia clienti

Per associare le gerarchie clienti in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Poi, sulla scheda **Cataloghi** sotto **Gerarchia dei clienti**, seleziona **Assegna gerarchie** per collegare una o più gerarchie di clienti al catalogo.

> [!NOTE]
> Non è possibile creare una nuova gerarchia di clienti dalla pagina **Tutti i cataloghi**. Devi crearlo dalla pagina **Gerarchie di clienti**. Devi quindi associarlo al catalogo nella pagina **Tutti i cataloghi**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Associare il gruppo di attributi di dimensione predefinito per criteri di affinamento quali dimensione, stile e colore

Per associare un gruppo di attributi di dimensione predefinito per criteri di affinamento quali dimensione, stile e colore, in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Poi, sulla scheda **Cataloghi** sotto **Attributi**, seleziona **Gruppi di attributi**.

#### <a name="set-attribute-metadata"></a>Imposta metadati di attributi

Per configurare i metadati di attributi, in Commerce headquarters, vai a **Vendita al dettaglio e commercio \> Cataloghi e assortimenti \> Tutti i cataloghi**. Poi, sulla scheda **Cataloghi** sotto **Attributi**, seleziona **Imposta metadati di attributi**. Per selezionare gli attributi che devono essere visualizzabili e affinabili, seleziona una categoria nella gerarchia di navigazione specifica del catalogo associata, quindi, in **Attributi prodotto catalogo**, seleziona un attributo. Quindi seleziona **Mostra attributo sul canale**. Per impostazione predefinita, tutti gli attributi visualizzabili sono anche ricercabili. Per rendere facoltativamente affinabili gli attributi, seleziona **Ridefinizione possibile**.

### <a name="validate-the-catalog"></a>Convalidare il catalogo

Prima che un nuovo catalogo sia disponibile all'utilizzo, deve essere convalidato e pubblicato.

Per convalidare un catalogo, attieniti alla procedura riportata di seguito.

1. Sulla scheda **Cataloghi** della pagina **Tutti i cataloghi** sotto **Convalida** seleziona **Convalida catalogo** per eseguire una convalida. Questo passaggio è obbligatorio. Convalida la precisione dell'impostazione necessaria.
1. Seleziona **Visualizza risultati** per vedere i dettagli della convalida. Se vengono rilevati errori, è necessario correggere i dati ed eseguire nuovamente la convalida finché non sia stata superata.

> [!NOTE]
> Se **Tipo catalogo = B2B**, la convalida avrà esito negativo se hai aggiunto negozi POS o un call center al catalogo. Ai cataloghi B2B possono essere associati soltanto canali B2B online. La convalida avrà esito negativo anche nel caso in cui non sia associata alcuna gerarchia dei clienti a un catalogo B2B. 

### <a name="approve-the-catalog"></a>Approva il catalogo

Dopo che un catalogo è stato convalidato, deve essere approvato.

Per avviare il flusso di lavoro di approvazione del catalogo, attieniti alla seguente procedura.

1. Nel riquadro azioni della pagina **Tutti i cataloghi** seleziona **Flusso di lavoro \> Invia**.
1. Vai in **Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Flussi di lavoro di commercio** per configurare i passaggi e gli utenti autorizzati per il flusso di lavoro. Il flusso di lavoro definisce i passaggi necessari per impostare il catalogo sullo stato **Approvato**.

### <a name="publish-the-catalog"></a>Pubblicare il catalogo

Dopo che un catalogo è nello stato **Approvato** puoi pubblicarlo selezionando **Pubblica** nel menu **Cataloghi**. Dopo che il catalogo si trova nello stato **Pubblicato**, può essere utilizzato nell'ordine registrazione del servizio clienti ed è possibile inviare i processi del catalogo. È possibile pubblicare un catalogo manualmente o tramite un processo batch. La data di validità definita per il catalogo determina se i prodotti sono disponibili nel negozio online. La data di scadenza definita determina quando i prodotti vengono rimossi dal negozio online.

> [!NOTE]
> Puoi pubblicare un catalogo contenente i prodotti con avvisi. Tuttavia tali prodotti non vengono visualizzati nel negozio online.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impatto sull'estendibilità dei cataloghi di Commerce per le personalizzazioni B2B](catalogs-b2b-sites-dev.md)

[Domande frequenti sui cataloghi di Commerce per B2B](catalogs-b2b-sites-FAQ.md)

[Modulo di selezione catalogo](catalog-picker.md)
