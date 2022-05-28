---
title: Procedure consigliate per i profili di registrazione
description: Questo argomento descrive le procedure consigliate per la configurazione dei profili di registrazione.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 211dc42b80089eb1f59a435f09d6e9d9f956736b
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734277"
---
# <a name="recommended-practices-for-posting-profiles"></a>Procedure consigliate per i profili di registrazione

Esistono diverse procedure consigliate da seguire quando configuri i profili di registrazione nel sistema. Questo argomento descrive diversi scenari e le procedure consigliate corrispondenti.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Impostazione del flag Non consentire l'immissione manuale

Nella pagina **Conti principali** la casella di controllo **Non consentire l'immissione manuale** deve essere selezionata per qualsiasi conto principale utilizzato per un profilo di registrazione. Questa impostazione impedisce agli utenti di registrare manualmente una scrittura contabile nel conto principale. Pertanto, aiuta a garantire che il giornale di registrazione secondario rimanga in equilibrio con la contabilità generale e aiuta a semplificare il processo di riconciliazione.

Se sono necessarie rettifiche su un conto controllato dal sistema e registrato automaticamente, puoi utilizzare uno di questi metodi:

- Crea un conto principale secondario in cui è possibile registrare le rettifiche. Quindi utilizza un conto totale o una riga speciale nei report finanziari per raggruppare e sommare i conti insieme.
- Storna le transazioni originali nel giornale di registrazione secondario appropriato, apporta le correzioni richieste e quindi registra nuovamente la transazione tramite lo stesso giornale di registrazione secondario.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Modifica dei profili di registrazione dopo l'avvio di transazioni

Se modifichi un profilo di registrazione dopo l'avvio di transazioni, la riconciliazione potrebbe non riuscire e il giornale di registrazione secondario e la contabilità generale possono diventare sbilanciati. In generale, ti consigliamo di **non** modificare il profilo di registrazione dopo l'avvio di transazioni.

Se sono necessarie modifiche, utilizza le seguenti linee guida per garantire l'integrità del sistema:

- Apporta le modifiche durante un periodo di chiusura.
- Apporta le modifiche quando non sono presenti altre transazioni nel sistema.
- Convalida la contabilità generale e riconciliala con il giornale di registrazione secondario prima e dopo aver apportato le modifiche.
- Le transazioni registrate non vengono aggiornate se modifichi il profilo di registrazione. Valuta attentamente se sono necessarie movimenti di rettifica per la modifica.
- Se stai modificando i profili di registrazione dell'inventario, considera in che modo le modifiche influiranno sulle scorte disponibili e sui saldi contabili. Alcune modifiche potrebbero richiedere di portare l'inventario a 0 (zero), chiudere l'inventario e quindi riportare l'inventario dopo aver apportato le modifiche.
- Testa sempre le modifiche in un ambiente non di produzione prima di apportarle in produzione.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Utilizzo della registrazione del database per controllare le modifiche ai profili di registrazione

Prendi in considerazione l'impostazione della registrazione del database per ogni profilo di registrazione e tabella dei parametri che controllano la registrazione. Quindi, se un parametro o un profilo viene modificato, avrai un record di controllo completo del valore che è stato modificato, chi lo ha modificato, quando è stato modificato e quale era il valore precedente. Queste informazioni possono essere critiche durante il processo di riconciliazione e il revisore potrebbe richiedere la documentazione di supporto.

Per ulteriori informazioni, vedi [Configurare la registrazione del database](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Utilizza la tabella seguente come riferimento per nomi di tabelle comuni correlati ai profili di registrazione e ai parametri di registrazione correlati.

| Nome pagina | Percorso di navigazione | Nome tabella |
|-----------|-----------------|------------|
| Parametri contabilità fornitori | Contabilità fornitori &gt; Impostazione &gt; Parametri contabilità fornitori | VendParm |
| Profilo registrazione fornitore | Contabilità fornitori &gt; Impostazione &gt; Profilo di registrazione fornitore | VendPosting |
| Codice di spese | Contabilità fornitori &gt; Impostazione spese &gt; Codice di addebito o Contabilità clienti &gt; Impostazione spese &gt; Codice spese | MarkupTable |
| Metodi di pagamento | Contabilità fornitori &gt; Impostazione pagamenti &gt; Metodi di pagamento | VendPaymMode |
| Sconti di cassa | Contabilità fornitori &gt; Impostazione pagamenti &gt; Sconti di cassa o Contabilità clienti &gt; Impostazione pagamenti &gt; Sconti di cassa | CashDisc |
| Commissione pagamento (fornitore) | Contabilità fornitori &gt; Impostazione pagamenti &gt; Commissione pagamento | VendPaymFee |
| Parametri contabilità clienti | Contabilità clienti &gt; Impostazioni &gt; Parametri contabilità clienti | CustParm |
| Profili di registrazione cliente | Contabilità clienti &gt; Impostazione &gt; Profilo di registrazione cliente | CustPosting |
| Metodi di pagamento | Contabilità clienti &gt; Impostazione pagamenti &gt; Metodi di pagamento | CustPaymMode |
| Commissione pagamento (cliente) | Contabilità clienti &gt; Impostazione pagamenti &gt; Metodi di pagamento | CustPaymFee |
| Parametri di leasing cespite | Leasing cespite &gt; Impostazione &gt; Parametri di leasing cespite | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Conti bancari | Gestione cassa e banche &gt; Conti bancari &gt; Conti bancari | BankAccountsTable |
| Tipi di transazioni bancarie | Gestione cassa e banche &gt; Impostazione &gt; Tipi di transazione bancaria | BankTransType |
| Regole di eliminazione | Consolidamenti &gt; Impostazione &gt; Regola di eliminazione | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Categorie di spesa | Gestione spese &gt; Impostazione &gt; Generale &gt; Categorie di spesa | ProjCategories |
| Parametri Cespiti | Cespiti &gt; Impostazione &gt; Parametri cespiti | AssetParameters |
| Profili registrazione cespiti | Cespiti &gt; Impostazioni &gt; Profili registrazione cespiti | AssetLedgerAccounts<br>AssetDisposalParameters |
| Conti rivalutazione valuta | Contabilità generale &gt; Valute &gt; Conti rivalutazione valuta | CurrencyLedgerGainLossAccount |
| Conti per transazioni automatiche | Contabilità generale &gt; Impostazione registrazione &gt; Conti per transazioni automatiche | LedgerSystemAccounts |
| Contabilità interaziendale | Contabilità generale &gt; Impostazione registrazione &gt; Conti interaziendali | LedgerIntercompany |
| Definizioni di registrazione transazioni | Contabilità generale &gt; Impostazione registrazione &gt; Definizioni di registrazione transazioni | JournalizingDefinitionTrans |
| Definizioni di registrazione | Contabilità generale &gt; Impostazione registrazione &gt; Definizioni di registrazione | JournalizingDefintion |
| Registrazione (inventario) | Gestione scorte &gt; Impostazione &gt; Registrazione &gt; Registrazione | InventPosting |
| Codici tipo di costo | Costo di spedizione &gt; Configurazione costi &gt; Codici tipo di costo | ITMCostTypeTable |
| Risorse | Controllo produzione &gt; Impostazione &gt; Risorse &gt; Risorse | WrkCtrTable |
| Gruppi di risorse | Controllo produzione &gt; Impostazione &gt; Risorse &gt; Gruppi di risorse | WrkCtrResourceGroup |
| Gruppi di produzioni | Controllo produzione &gt; Impostazione &gt; Produzione &gt; Gruppo di produzione | ProdGroup |
| Categorie costi | Controllo produzione &gt; Impostazione &gt; Cicli di lavorazione &gt; Categorie costi | ProjCategory |
| Gruppi di progetti | Gestione progetti e contabilità &gt; Impostazione &gt; Registrazione &gt; Gruppi di progetto | ProjGroup |
| Impostazioni registrazione contabile (progetti) | Gestione progetti e contabilità &gt; Impostazione &gt; Registrazione &gt; Impostazioni registrazione contabile | ProjPosting |
| Conti di contropartita predefiniti per le spese | Gestione progetti e contabilità &gt; Impostazione &gt; Registrazione &gt; Conti di compensazione predefiniti per spese | ProjDefaultOffsetSetup |
| Profili di registrazione della gestione degli sconti | Gestione sconti &gt; Impostazione registrazione gestione sconti &gt; Profili di registrazione gestione sconti | TAMRebatePosting |
| Gruppo registrazione contabile (imposte) | Imposta &gt; Impostazione &gt; IVA &gt; Gruppo registrazione contabile | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Modifica dei gruppi dopo l'avvio delle transazioni

Presta attenzione quando modifichi i gruppi nei dati master. Se utilizzi i gruppi per definire i profili di registrazione, qualsiasi modifica a un gruppo in un record master può avere un impatto negativo sulla capacità di riconciliare la contabilità generale nel giornale di registrazione secondario. Ad esempio, è possibile configurare il profilo di registrazione dell'inventario per i ricavi degli ordini cliente in modo che venga utilizzato un conto ricavi diverso per ciascun gruppo di articoli. Se modifichi il gruppo di articoli assegnato a un articolo dopo l'avvio di transazioni, i ricavi delle nuove transazioni verranno registrati nel conto aggiornato. Tuttavia, tutti ricavi registrati prima della modifica rimarranno nel conto originale.

## <a name="testing-posting-profiles"></a>Test dei profili di registrazione

Prima della fase operativa e dopo aver apportato modifiche o aggiunte ai profili di registrazione o ai parametri correlati, è necessario testare ogni scenario. Come minimo, dovresti testare ogni tipo di registrazione per verificare che funzioni correttamente. Tuttavia, l'approccio consigliato consiste nel testare ogni transazione e combinazione del profilo di registrazione.

Ad esempio, hai due profili di registrazione dei clienti, ognuno dei quali ha tre record specifici per gruppi di clienti. In questo caso, dovresti testare ogni tipo di transazione.

**Profili registrazione:**

- **GEN** – Il profilo di registrazione generale che ha un gruppo per i dipendenti, uno per i clienti e uno interaziendale. Ogni gruppo punta a un conto commerciale di Contabilità clienti diverso.
- **PRE** – Il profilo di registrazione del pagamento anticipato che ha un record per tutti i pagamenti anticipati che punta ai conti pagamenti anticipati del cliente.

### <a name="testing-scenarios"></a>Scenari di test

- Fattura a testo libero per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **GEN**
- Fattura a testo libero per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **PRE**
- Fattura ordine cliente per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **GEN**
- Fattura ordine cliente per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **PRE**
- Giornale di registrazione pagamenti cliente per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **GEN**
- Giornale di registrazione pagamenti cliente per un cliente nel gruppo **Dipendente** che utilizza il profilo di registrazione **PRE**

Per l'esempio precedente, ripeti uno scenario di test per ogni gruppo di clienti e ripeti ciascun gruppo di scenari di test per ogni tipo di transazione aggiuntivo (ad esempio, fatture di progetto e gestione dei servizi).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Riconciliazione della contabilità generale nel giornale di registrazione secondario

La contabilità generale deve essere riconciliata con il giornale di registrazione secondario ogni periodo. Molti moduli contengono report predefiniti che possono essere utilizzati per aiutare a fare questa riconciliazione. Tuttavia, a seconda dei requisiti locali, potrebbe essere necessario sviluppare report personalizzati o estendere i report esistenti per soddisfare i propri requisiti.

Ti consigliamo di chiudere un periodo di simulazione e riconciliare ciascuno dei tuoi giornali di registrazione secondari con la contabilità generale prima della fase operativa. Ti consigliamo inoltre di eseguire un cutover di simulazione di tutti i saldi aperti e le transazioni aperte prima della fase operativa iniziale. Come parte di questo processo, è necessario eseguire una riconciliazione completa per garantire che la migrazione dei saldi e delle transazioni aperte sia in equilibrio con i sistemi legacy e che tutti i giornali di registrazione secondari siano in equilibrio con la contabilità generale prima della creazione di nuove transazioni.
