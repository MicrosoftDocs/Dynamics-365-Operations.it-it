---
title: Domande frequenti sui cataloghi Commerce per siti B2B
description: In questo articolo vengono fornite risposte alle domande frequenti sui cataloghi di Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 68c648c5caf2667f413b236dc437fc2c74c40d07
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168987"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>Domande frequenti sui cataloghi Commerce per siti B2B

[!include [banner](includes/banner.md)]

In questo articolo vengono fornite risposte alle domande frequenti sui cataloghi di Microsoft Dynamics 365 Commerce [Business to Business (B2B)](catalogs-b2b-sites.md).

### <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>Perché non posso configurare una gerarchia di navigazione specifica del catalogo o visualizzare un'opzione per associare una gerarchia di clienti?

Assicurati che la funzionalità **Abilita l'utilizzo di più cataloghi nei canali di vendita al dettaglio** sia abilitata nell'area di lavoro **Gestione funzionalità** in Commerce headquarters e che l'ambiente sia aggiornato alla versione di Commerce 10.0.27 o successiva. Verifica di aver selezionato **B2B** in **Tipo di catalogo**.

### <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>Posso visualizzare la gerarchia specifica del catalogo e arricchire le pagine delle categorie nel generatore di siti di Commerce?

Sì, gli utenti del generatore di siti di Commerce che hanno accesso alla pagina **Prodotti** nel geratore di siti possono selezionare un catalogo e visualizzare la gerarchia specifica del catalogo. Dalla pagina **Prodotti** gli utenti possono anche arricchire una pagina di categoria per una categoria specifica nel catalogo. Per ulteriori informazioni, vedere [Migliorare una pagina di destinazione di categoria](enrich-category-page.md). Se vuoi avere un arricchimento specifico per un catalogo, ti consigliamo di usare una gerarchia di navigazione distinta e univoca per quel catalogo.

### <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>Un acquirente B2B può acquistare da più cataloghi in un'unica transazione di pagamento?

Sì, gli acquisti da più cataloghi in un'unica transazione di pagamento sono consentiti. Gli acquirenti B2B possono utilizzare l'indicatore del catalogo nella visualizzazione del carrello per determinare quali articoli sono stati aggiunti da quali cataloghi.

### <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Se un acquirente B2B acquista lo stesso articolo da cataloghi diversi, qual è il comportamento previsto?

Sebbene un utente possa avere accesso a più cataloghi in un dato momento, ci si aspetta che i prodotti in quei cataloghi si escludano a vicenda. In altre parole, idealmente, lo stesso prodotto non deve far parte di più di un catalogo per un determinato utente.

Tuttavia, se si verifica una situazione in cui lo stesso prodotto appartiene a più cataloghi, il sistema manterrà più righe di carrello per quel prodotto. Ci sarà una riga separata per ogni catalogo. Lo stesso prodotto di due cataloghi diversi non verrà unito al momento del pagamento.

### <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Quando un acquirente B2B fa acquisti, c'è qualche convalida per la disponibilità del catalogo?

Sì. Un acquirente B2B potrà procedere alla cassa solo se tutti gli articoli nel carrello provengono da cataloghi validi. Se gli articoli del carrello provengono da cataloghi scaduti o ritirati, verranno rimossi e l'utente verrà avvisato.

### <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Durante l'esperienza di acquisto, la ricerca e l'individuazione dei prodotti (incluse le raccolte di prodotti correlati e consigliati) sono specifiche del catalogo?

Sì. Non appena un utente seleziona un catalogo specifico, l'intero percorso di acquisto diventa specifico del catalogo. Questo percorso include esperienze di individuazione di prodotti come suggerimenti di ricerca, risultati di ricerca, risultati di categoria, criteri di affinamento della ricerca, prezzi, attributi e prodotti consigliati (come prodotti nuovi, più venduti, di tendenza, acquistati di frequente insieme e prodotti correlati).

### <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>Un acquirente B2B può acquistare dall'assortimento predefinito (catalogID=0)?

No, un acquirente B2B non può acquistare dall'assortimento predefinito. Questo assortimento è inteso solo per la navigazione anonima. Se a un acquirente B2B mancano le assegnazioni di catalogo (aggiornamenti in attesa dall'amministrazione), non sarà in grado di vedere alcun catalogo tra cui scegliere e non sarà visibile alcuna gerarchia di categorie.

### <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>I contenuti di marketing possono essere curati per un prodotto specifico di un catalogo?

Attualmente, l'arricchimento del prodotto è supportato solo a livello di sito e canale. In altre parole, se un prodotto viene arricchito, viene condiviso su più cataloghi e la pagina dei dettagli del prodotto arricchito (PDP) corrispondente per quel prodotto verrà visualizzata allo stesso modo in tutti i cataloghi di un determinato sito. 

### <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>Il supporto del catalogo è disponibile per i canali online B2B e business-to-consumer (B2C)?

Attualmente, i cataloghi di Commerce funzionano solo con i canali B2B online.

### <a name="a-new-customer-was-added-to-the-customer-hierarchy-or-a-new-hierarchy-was-associated-with-the-catalog-but-the-catalog-is-not-available-to-the-user-why"></a>È stato aggiunto un nuovo cliente alla gerarchia dei clienti oppure è stata associata una nuova gerarchia al catalogo, ma il catalogo non è disponibile all'utente. Perché?

Assicurati di aver eseguito i processi **1010** dopo aver associato il nuovo cliente a una gerarchia dei clienti esistente e al momento della creazione della nuova gerarchia dei clienti. I cataloghi associati alla gerarchia dei clienti saranno visibili solo una volta completato il processo **1010**. Se anche il catalogo è nuovo, assicurati di aver eseguito anche il processo **1150** (catalogo), oltre ai processi **1010**. Come per ogni nuovo catalogo, attendi il completamento della sincronizzazione dei dati al canale e all'indice di ricerca. Se un processo ha lo stato "Applicato", ciò significa che è in corso la sincronizzazione dei dati al database del canale, ma è necessario ancora un po' di tempo per la sincronizzazione dei dati all'indice di ricerca. 

### <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>Possiamo impostare articoli di upsell/cross-sell specifici del catalogo?

Attualmente, sono supportate solo le funzionalità dei prodotti correlati. Tuttavia, per i call center sono disponibili configurazioni di articoli di upsell e cross-sell.

Le seguenti funzioni sono supportate solo per i call center:

- Codici sorgente del catalogo
- Utilizzare gli ID origine per tenere traccia dei costi e delle velocità di risposta
- Script di articolo e di ordine specifici del catalogo
- Analisi della pagina Catalogo
- Richieste catalogo
- Scadenzari pagamenti
- Prodotti gratuiti basati su codici sorgente

### <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>Possiamo utilizzare i codici sorgente del catalogo per gli ordini B2B tramite il portale e-commerce?

N. I codici sorgente del catalogo sono supportati solo per i canali del call center.

## <a name="additional-resources"></a>Risorse aggiuntive

[Crea cataloghi di Commerce per siti B2B](catalogs-b2b-sites.md)

[Modulo di selezione catalogo](catalog-picker.md)

[Impatto sull'estendibilità dei cataloghi di Commerce per le personalizzazioni B2B](catalogs-b2b-sites-dev.md)
