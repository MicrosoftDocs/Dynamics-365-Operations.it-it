---
title: Funzionalità dell'app Store Commerce
description: Questo articolo descrive la funzionalità disponibile nell'app Store Commerce per Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: d713cc0e9537ae20ffddee6e77779a16e74bd779
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725637"
---
# <a name="store-commerce-app-capabilities"></a>Funzionalità dell'app Store Commerce

[!include [banner](includes/banner.md)]

L'app Store Commerce è la moderna esperienza POS per Microsoft Dynamics 365 Commerce. Consente alle aziende di elaborare le transazioni in negozio e gestire le operazioni di back-office come l'inventario e l'elaborazione degli ordini. L'app consente inoltre alle aziende di gestire le relazioni con i clienti con fedeltà e fidelizzazione dei clienti. 

Basata su Commerce Scale Unit (CSU), l'app Store Commerce offre una soluzione multicanale completa. Ad esempio, un cliente può acquistare un prodotto online e ritirarlo in un negozio vicino, continuando così il percorso di acquisto attraverso i canali senza perdere alcun dato. 

Questo articolo fornisce una panoramica delle capacità dell'app Store Commerce.

## <a name="platform"></a>Piattaforma

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Multicanale | Dynamics 365 Commerce offre una soluzione multicanale completa che unifica le esperienze di back-office, nel punto vendita, call center e digitali. | [Panoramica](index.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Commerce Headless | Commerce Scale Unit ospita il motore di Commerce headless. Il motore di Commerce headless funge da punto centrale per tutta la logica di business di Commerce e offre una soluzione multicanale completa. | <p>[Panoramica dell'architettura](commerce-architecture.md)</p><p>[Architettura headless](dev-itpro/retail-server-architecture.md)</p> | [Video tecnologici](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce Headquarters | Commerce headquarters fornisce funzionalità di back-office che consentono la configurazione di prodotti, dipendenti, processi aziendali, prezzi e altre funzionalità necessarie per l'azienda. | [Panoramica dell'architettura](commerce-architecture.md) | |
| POS | L'app Store Commerce è l'esperienza POS per Dynamics 365 Commerce. Offre funzionalità POS complete e ricche di capacità che aiutano gli addetti alle vendite, i cassieri e i responsabili a fornire un servizio clienti di qualità superiore. Inoltre, fornisce diverse opzioni di distribuzione ai rivenditori, aiuta a migliorare le prestazioni e offre una migliore gestione del ciclo di vita delle applicazioni (ALM). | [App Store Commerce](dev-itpro/store-commerce.md) | <p>[Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Video](https://youtu.be/7B332XH_zfs)</p><p>[Migrazione da MPOS in Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Distribuzione cloud | È possibile distribuire più istanze di Commerce Scale Unit per la distribuzione del carico e la prossimità geografica. | [Distribuzione cloud](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| Distribuzione locale | Utilizzando una distribuzione di dati aziendali locale, i clienti Commerce possono avere una maggiore proprietà e gestione degli ambienti Dynamics 365. | [Distribuzione locale](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Gestione delle periferiche

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Fattori di forma multipli | L'app Store Commerce è supportata su più fattori di forma del dispositivo, come PC, tablet e dispositivi mobili. L'interfaccia utente (UI) reattiva consente il ridimensionamento automatico del layout e l'adattamento alle dimensioni dello schermo. | [Configurazioni visive](pos-screen-layouts.md) | |
| Multipiattaforma | L'app Store Commerce è supportata sulle piattaforme Web, Windows, iOS e Android. | [Piattaforme](dev-itpro/hybridapp.md) | |
| Marchio | La finestra di progettazione della schermata ti consente di personalizzare i layout dello schermo per soddisfare le tue esigenze aziendali. Inoltre, i temi, i layout, i colori e le immagini possono essere creati in base ai ruoli dei dipendenti e possono quindi essere condivisi tra gli utenti per coerenza del marchio e facilità d'uso. | [Configurazioni visive](pos-screen-layouts.md) | [Video](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topologia | Sono supportate diverse topologie nel punto vendita, in base alla disponibilità della rete. | <p>[Topologia](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infografica](dev-itpro/retail-in-store-topology.md)</p> | |
| Gestione di più periferiche | È possibile gestire facilmente più dispositivi in tutti i negozi da Commerce headquarters. | [Attivazione](set-up-activation-accounts-validate-devices-hq.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Gestione dipendenti

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Accesso | Ogni dipendente del negozio può avere un accesso dedicato. I tipi di accesso includono nome utente, codice a barre, lettore di strisce magnetiche (MSR), dati biometrici e Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Accesso esteso](extended-logon.md)</p> | |
| Autorizzazioni | Sono supportati diversi livelli di autorizzazione per i dipendenti, come l'autorizzazione a creare gli ordini e l'autorizzazione a modificare gli ordini. | [Autorizzazioni](tasks/create-pos-permission-groups.md) | |
| Gestione di orario e presenze | Le presenze possono essere gestite utilizzando la funzione Orologio. I dati sulle presenze possono essere elaborati in busta paga utilizzando l'app Dynamics 365 Human Resources. | [Gestione orari](retail-time-attendance.md) | |
| Provvigione di vendita | Le vendite possono essere tracciate per rappresentante per il calcolo delle provvigioni o altri incentivi. | [Provvigione](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Merchandising

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Gestione dell'assortimento | I responsabili del merchandising possono ordinare i prodotti in modo che siano disponibili per la vendita in un canale specifico e durante un periodo specifico. | [Assortimenti](assortments.md) | |
| Cataloghi | I responsabili del merchandising possono gestire i cataloghi per identificare i prodotti che desideri offrire con prezzi specifici del catalogo. | [Cataloghi](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Gestione categorie e prodotti | In Commerce headquarters, i responsabili del merchandising possono creare prodotti con varianti, attributi, un'unità di misura e così via. Possono anche definire una gerarchia di categorie per organizzare i prodotti. | [Prodotto](retail-hierarchies.md) | |
| Aggregazioni | I responsabili del merchandising possono raggruppare i prodotti in modo che vengano venduti come aggregazione o kit. | [Kit](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Codici informativi | Usa i codici di informazioni per suggerire al cassiere di inserire le informazioni nelle varie azioni nel POS, ad esempio le vendite dell'articolo, i resi articolo o la selezione dei clienti. | [Codici informativi](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Articoli collegati | Usa gli articoli collegati per vendere i prodotti quando un articolo viene aggiunto alla transazione. | [Articoli collegati](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garanzie | Le garanzie estese possono essere vendute insieme ai prodotti. | [Garanzia](extended-warranty.md) | |
| Stampa di etichette | Le etichette possono essere generate per contenere informazioni sul prodotto quali il numero batch, il numero di serie o la data di scadenza. | [Stampa di etichette](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Vendita assistita

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Esplorazione prodotto | Sfoglia i prodotti per categoria. | [Gerarchia prodotti](retail-hierarchies.md) | |
| Ricerca prodotto | Cerca i prodotti per nome e perfeziona le ricerche utilizzando gli attributi del prodotto come la marca, il prezzo e il materiale. Questa funzionalità è basata su Ricerca cognitiva di Azure. | [Ricerca basata su cloud](cloud-powered-search-overview.md) | |
| Pagina Dettagli prodotto | Le pagine ricche di dettagli sui prodotti possono includere immagini, una descrizione, attributi del prodotto e prodotti consigliati. Le raccomandazioni sono basate sul servizio raccomandazioni. | | |
| Confronto di prodotti | Confronta più prodotti e aiuta i clienti a sceglierne uno e aggiungerlo a una transazione. | | |
| Sezione infinita | Cerca facilmente l'inventario in altri negozi e crea ordini. | [Ricerca in magazzino](pos-inventory-lookup-operation.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Suggerimenti | Upselling e cross-selling di prodotti utilizzando il servizio raccomandazioni. Questo servizio utilizza una tecnologia brevettata per suggerire raccomandazioni, in base alle tendenze di acquisto e caratteristiche come nuovi arrivi, immagini simili e bestseller. Queste raccomandazioni sono disponibili nelle pagine dei dettagli del prodotto, nella pagina **Dettagli cliente** e nella pagina **Transazioni**. | [Suggerimenti](product-recommendations.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Relazione con il cliente

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Gestione clienti | Consente di creare, modificare e gestire i conti dei clienti. I conti dei clienti possono essere gestiti in modalità asincrona per evitare l'elaborazione in tempo reale. | [Management](customer-mgmt-stores.md) | |
| Attributi cliente | Il framework degli attributi del cliente consente di acquisire dati aggiuntivi relativi al cliente in base ai requisiti aziendali. | [Attributi](dev-itpro/customer-attributes.md) | |
| Pagina Dettagli cliente | Una ricca pagina dei dettagli del cliente fornisce una visione multicanale delle interazioni del cliente su tutti i canali. Queste interazioni includono acquisti, liste dei desideri e punti fedeltà. | | |
| Ricerca di clienti basata su cloud | Cerca i clienti per nome, numero di telefono, indirizzo e-mail, carta fedeltà, indirizzo e così via. | [Ricerca basata su cloud](pos-search-improvements.md#customer-search) | |
| Fedeltà e premi | I clienti possono aderire a programmi fedeltà e guadagnare e riscattare punti fedeltà su tutti i canali. | [Fedeltà](set-up-customer-loyalty-program.md) | |
| Gestione profili clienti | Gestisci i clienti chiave utilizzando un registro clienti e tieni traccia delle attività e delle note sul profilo del cliente. L'integrazione di Dynamics 365 Customer Insights consente ai dipendenti del negozio di ottenere indicazioni sulla prossima azione migliore da eseguire per ciascun cliente. | [Gestione profili clienti](clienteling-overview.md#activities-and-notes) | |

## <a name="pricing-and-discounts"></a>Prezzi e sconti

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Accordi commerciali | I responsabili dei prezzi possono utilizzare gli accordi commerciali per definire prezzi speciali, basati su accordi a lungo termine per clienti specifici. | [Determinazione prezzo](price-management.md)| [Video](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Contratti di vendita | I responsabili dei prezzi possono utilizzare i contratti di vendita per definire i prezzi basati su contratto negli scenari di commercio business-to-business (B2B). | [Determinazione prezzo](price-management.md) | |
| Rettifiche prezzo | I responsabili dei prezzi possono utilizzare la funzionalità di adeguamento dei prezzi per creare, tracciare e gestire gli sconti dei prezzi per i loro prodotti nel tempo. | [Rettifiche prezzo](price-adjustments-discounts.md) | |
| Sconti | I responsabili dei prezzi possono impostare diversi tipi di sconti per eseguire una varietà di promozioni. Questi sconti includono sconti semplici, sconti quantità, sconti semplici, sconti quantità, sconti soglia, sconti gamma e sconti basati sul metodo di pagamento e sconti sulla spedizione. | [Sconti](retail-discounts-overview.md) | |
| Buoni sconto | I responsabili dei prezzi possono impostare codici coupon o codici a barre, collegarli agli sconti e distribuirli ai clienti. Gli addetti alle vendite possono aggiungere coupon alle transazioni di vendita o rimuoverli. | [Buoni sconto](coupons.md) | |
| Gruppi di prezzi | I responsabili dei prezzi possono utilizzare la funzionalità dei gruppi di prezzi per definire i prezzi contestuali, in base a canali, cataloghi, affiliazioni o programmi fedeltà. | [Determinazione prezzo](price-management.md) | |
| Promozioni disponibili | Gli addetti alle vendite possono cercare facilmente le promozioni disponibili per i prodotti nel negozio, i prodotti che sono stati aggiunti a una transazione e così via. | [Funzioni di prezzo](pos-pricing-functions.md) | |
| Controlli di prezzi | Gli addetti alle vendite possono controllare rapidamente i prezzi di vendita attivi dei prodotti nel negozio. | [Funzioni di prezzo](pos-pricing-functions.md) | |
| Sostituizioni prezzi | Gli addetti alle vendite che dispongono delle autorizzazioni necessarie possono sostituire i prezzi calcolati o configurati dal sistema. | [Funzioni di prezzo](pos-pricing-functions.md) | |
| Sconti manuali | Gli addetti alle vendite che dispongono delle autorizzazioni richieste possono applicare sconti manuali alle transazioni di vendita o alle righe di vendita. | [Funzioni di prezzo](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Pagamenti elettronici

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Credito e debito | L'app Store Commerce supporta i principali pagamenti con carta di credito e debito tramite Adyen Payment Gateway e l'evasione degli ordini tramite PayPal. L'SDK di pagamenti consente connessioni a gateway esterni supportate da integrazioni ISV (Independent Software Vendor). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Pagamenti](payment-methods.md)</p> | <p>[Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Supporto per portafoglio digitale | L'app Store Commerce supporta i pagamenti tramite metodi di pagamento del portafoglio digitale che non utilizzano gli intervalli di numero di identificazione della banca (BIN) come fanno le tradizionali carte di credito e di debito. I metodi di pagamento possono essere mappati a pagamenti con portafoglio digitale come Adyen. | [Portafoglio](wallets.md) | |
| Supporto gift card | Gift card Dynamics 365 con numero di identificazione della banca, Stored Value Solutions (SVS) e gift card Givex. Le gift card possono essere acquistate e riscattate in un ordine. | [Gift card](dev-itpro/gift-card.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Fraud Protection | Dynamics 365 Fraud Protection ti aiuta a prevenire le attività fraudolente e identificare i luoghi in cui la frode potrebbe passare inosservata. | [Fraud Protection](dev-itpro/dfp.md) | [Video](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Imposte e addebiti

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Imposte | L'app Store Commerce supporta numerosi tipi di imposte indirette, ad esempio imposta sul valore aggiunto (IVA), Imposta sui Beni e Servizi (GST, Goods and Services Tax), commissioni in base a unità e ritenuta d'acconto. | [Imposte](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Spese | Gli addebiti possono essere configurati a livello di riga, a livello di intestazione, come addebiti automatici, per canale e così via. | [Spese](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Elaborazione ed evasione degli ordini

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Creazione ordine | È possibile creare un ordine per la spedizione o per il ritiro presso un negozio vicino. È possibile fornire le fasce orarie per il ritiro. | [Panoramica](customer-orders-overview.md) | |
| Modifica dell'ordine | Un ordine può essere modificato, restituito, annullato e così via. | <p>[Annulla](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Resi](pos-returns.md)</p> | |
| Cerca ordini | Cerca e filtra gli ordini utilizzando le informazioni specifiche dell'ordine. | [Cerca ordini](enhancedorderrecall.md) | |
| Attributi ordine | Il framework degli attributi dell'ordine consente di acquisire informazioni aggiuntive relative all'ordine in base ai requisiti aziendali. | [Attributi](dev-itpro/order-attributes.md) | |
| Consegna diretta | Gli articoli possono essere contrassegnati per la consegna diretta da un fornitore all'indirizzo di un cliente. La spedizione diretta è anche definita spedizione dal fornitore al cliente. | [Consegna diretta](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Offerta | I dipendenti del negozio possono creare offerte per i clienti e specificare un prezzo speciale, sconti manuali e una data di validità dell'offerta. | [Offerta](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Evasione | I negozi possono prelevare, imballare e spedire gli ordini. Un documento di trasporto può essere aggiunto ai pacchi pronti per la spedizione. | [Evasione](order-fulfillment-overview.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021) |
| Gestione ordini distribuiti | L'app Store Commerce supporta l'ottimizzazione intelligente dell'evasione degli ordini in cui le strategie aziendali possono essere configurate in base alla natura dell'attività, al tipo di cliente, all'origine di un ordine e al metodo di consegna di un ordine. | [DOM](dom.md) | |

## <a name="inventory-management"></a>Gestione inventario

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Distribuzione push | Semplifica la distribuzione dell'inventario disponibile da un centro di distribuzione a più negozi o magazzini. | [Distribuzione push](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Cross-docking | Semplifica la distribuzione dell'inventario degli ordini di acquisto in entrata a più negozi o magazzini. | [Cross-docking](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Scorte in entrata | Ricevi l'inventario da un fornitore tramite un ordine di acquisto o da un altro magazzino tramite un ordine di trasferimento. Crea un ordine di acquisto in entrata o una richiesta di ordine di trasferimento. | [In entrata](pos-inbound-inventory-operation.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Scorte in uscita | Spedisci l'inventario a un altro magazzino tramite un ordine di trasferimento e crea una richiesta di ordine di trasferimento in uscita. | [In uscita](pos-outbound-inventory-operation.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Ricerca in magazzino | Controlla l'inventario disponibile per i prodotti nei negozi e nei magazzini e controlla l'inventario available-to-promise (ATP) nelle date future. | [Ricerca in magazzino](pos-inventory-lookup-operation.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Rettifica scorte | Modifica l'inventario in entrata o in uscita dal magazzino di un negozio per soddisfare requisiti aziendali specifici senza utilizzare una vendita, una ricevuta o un riconteggio. | [Rettifica scorte](work-with-store-inventory.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Conteggi scorte | Conta l'inventario fisico e rettifica l'inventario della contabilità di sistema in modo che corrispondano. | [Conteggio](work-with-store-inventory.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Movimento scorte | Sposta l'inventario tra le posizioni di un negozio. | [Movimento](work-with-store-inventory.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |

## <a name="financials"></a>Dati finanziari

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Gestione di cassa | L'app Store Commerce supporta la gestione della cassa e altri metodi di pagamento specifici nel negozio. Inoltre, è possibile abilitare la riconciliazione dei turni nel negozio per funzionalità avanzate di gestione della cassa. | [Cassa](cash-mgmt.md) | |
| Rendiconti finanziari e riconciliazione | Le transazioni di cassa e transazionali per un negozio vengono registrate in Commerce headquarters attraverso i processi di registrazione degli estratti conto. | [Rendiconti](retail-statements.md) | |
| Transazioni ricavi e spese | Elabora le transazioni di piccola cassa nel negozio e registra le entrate che non arrivano nel modo tradizionale, come i soldi smarriti, la quota dei ricavi di un bar e i servizi di pulizia dei tappeti. | [Rendiconti](retail-statements.md) | |
| Pagamenti fatture | Acquisisci i pagamenti in base alle fatture. | [Fattura](payinvoice.md) | |

## <a name="employee-productivity"></a>Produttività dei dipendenti

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Gestione attività | Crea gli elenchi di attività e assegna le attività a negozi e dipendenti. Tieni traccia dello stato delle attività nei negozi. La perfetta integrazione con Microsoft Teams è fornita. | <p>[Gestione attività](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Video](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Hardware e periferiche

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Connettere le periferiche | Collega le periferiche come stampanti, cassetti di cassa, scanner e dispositivi di pagamento a un terminale POS. | [Periferiche](retail-peripherals-overview.md) ||
| Condividere le periferiche | Stampanti di ricevute, cassetti di cassa e dispositivi di pagamento possono essere condivisi tra molti terminali collegandoli a una stazione hardware condivisa. | <p>[Stazione hardware](retail-peripherals-overview.md) ||
| POS e simulatore periferica | Il simulatore di periferica supporta il test di scenari che richiedono in genere dispositivi POS fisici. Include anche un simulatore POS che può essere utilizzato per testare la compatibilità di dispositivi periferici fisici senza richiedere la distribuzione del client POS. | [Simulatore](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Entrate

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Stampare le ricevute | Ricevute di vario tipo, come ricevute di vendita, ricevute di carte di credito, ricevute regalo e fatture, possono essere stampate per impostazione predefinita o dopo la conferma del cassiere al momento del pagamento. Possono anche essere ristampate dal giornale di registrazione. | [Stampa](receipt-templates-printing.md) | |
| Ricevute inviate tramite posta elettronica | Le ricevute possono essere inviate via e-mail dal POS dopo il completamento di un pagamento. | [Messaggio e-mail](email-receipts.md) | |
| Progettare le ricevute | Le ricevute del negozio possono essere personalizzate in modo da mostrare dati e layout appropriati per il rivenditore e il tipo di transazione. Le ricevute possono anche essere estese in modo da mostrare i dati personalizzati richiesti dal rivenditore. | [Progettazione](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Supporto offline

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Offline semplice | La modalità offline facilitata ti consente di continuare a effettuare transazioni anche quando la connettività Internet è limitata o non disponibile. L'esclusione dei dati consente di ridurre le dimensioni dei dati dei database offline e di ottimizzare le prestazioni. | [Offline](pos-operations.md) | |
| Passaggio basato sulle prestazioni | Passa alla modalità offline quando viene rilevato un degrado delle prestazioni. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Video](https://youtu.be/sQU-2pgHToI) |
| Dashboard offline | Il dashboard **Stato offline** mostra lo stato offline, gli errori e i dettagli dei dati per ciascun dispositivo. Pertanto, è facile gestire lo stato di molti dispositivi. | [Offline](dev-itpro/implementation-considerations-offline.md) | [Video](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Estendibilità

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Commerce Headquarters | Le soluzioni Commerce headquarters possono essere personalizzate aggiungendo o modificando i processi aziendali. Commerce headquarters supporta l'uso di metadati e un modello di estensione basato su codice per aggiungere funzionalità personalizzate. Può essere facilmente integrato in soluzioni esterne. | [Panoramica](dev-itpro/extend-customer-cdx-package.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Commerce Headless | Il framework dell'API multicanale estensibile può essere utilizzato per personalizzare e aggiungere la logica aziendale. API con gestori delle richieste e modelli di estensione pre trigger e post trigger. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Commerce SDK | Commerce SDK include il codice, gli esempi di codice, i modelli e gli strumenti necessari per l'estensione o la personalizzazione delle funzionalità di Dynamics 365 Commerce. L'SDK viene pubblicato in diversi repository in GitHub, a seconda dei componenti dell'estensione. | [SDK](dev-itpro/retail-sdk/sdk-github.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| POS | L'app Store Commerce può essere estesa in modo indipendente utilizzando la funzione di estensione POS di Commerce SDK. Il framework supporta la personalizzazione dell'esperienza utente, dei flussi di lavoro e della logica aziendale. | [POS](dev-itpro/pos-extension/pos-extension-overview.md) | [Video tecnologici](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Report

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Report vendite | I report sulle vendite per personale, registro, tipo di pagamento, resi, prodotto e così via sono disponibili per i responsabili del negozio. I esponsabili possono visualizzare questi report e utilizzarli per allocare commissioni e identificare le tendenze dei prodotti. | | |

## <a name="diagnostics"></a>Diagnostica

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Operational Insights | Le metriche di affidabilità e prestazioni del servizio curate dal negozio sono disponibili nella sottoscrizione Application Insights del cliente. Sono disponibili funzionalità avanzate di monitoraggio e avviso. | | |
| Controllo integrità | La disponibilità delle periferiche collegate a un POS può essere verificata eseguendo l'operazione di controllo dello stato. I singoli problemi delle periferiche possono quindi essere risolti e verificati. | [Controllo integrità](pos-healthcheck.md) | [Video](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalizzazione

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Supporto multimercato | Le funzionalità specifiche del mercato come integrazione fiscale, GST, fatturazione avanzata e pagamenti anticipati sono supportate per impostazione predefinita. Questa capacità copre diversi mercati in Europa, nelle Americhe, in Russia, in Asia, in Arabia Saudita e così via. | [Globalizzazione](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Conformità

| Capacità | Description | Documentazione | Contenuti supplementari |
|---|---|---|---|
| Standard Microsoft | L'app Store Commerce soddisfa gli standard Microsoft per sicurezza, privacy, accessibilità, il regolamento generale sulla protezione dei dati (GDPR), il limite dei dati dell'Unione europea (UE) e così via. | | |

