---
title: Panoramica dei profili di registrazione
description: Questo argomento spiega come vengono utilizzati i profili di registrazione nelle app Microsoft Dynamics 365.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9ad33d9a34bc449b81ec6d02a78b9ca1653aca5
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2022
ms.locfileid: "8018381"
---
# <a name="posting-profiles-overview"></a>Panoramica dei profili di registrazione

Nelle app Finance and Operations, il termine *profili di registrazione* viene utilizzato per descrivere le configurazioni che controllano il modo in cui i conti del giornale d registrazione secondario vengono convertiti in conti principali in modo che possano essere utilizzati nelle transazioni registrate nella contabilità generale. Ad esempio, controllano il modo in cui il cliente viene convertito in un conto principale Contabilità clienti quando viene registrata una fattura.

Alcuni moduli e funzionalità hanno una pagina che include le parole "profilo di registrazione" nel nome (ad esempio, **Profilo di registrazione cliente** o **Profilo di registrazione fornitore**). Inoltre, alcuni moduli hanno più opzioni per la configurazione della registrazione contabile per le transazioni generate dal giornale di registrazione secondario. Ad esempio, nel modulo **Controllo produzione** puoi impostare la registrazione per gruppo di produzione, risorsa o gruppo di risorse.

Tieni presente che, per molti tipi di transazioni, esiste un'alternativa ai profili di registrazione: le definizioni di registrazione. Per i documenti supportati è possibile utilizzare le definizioni di registrazione anziché i profili di registrazione per classificare i conti principali e le dimensioni finanziarie per le voci contabili. Se pensi di utilizzare impegni di spesa o impegni preliminari di spesa, è necessaria una definizione di registrazione per definire i conti per le registrazioni contabili.

Prima di poter configurare i profili di registrazione, le definizioni di registrazione o la pagina **Conti per transazioni automatiche** è necessario configurare il piano dei conti nella pagina **Contabilità generale** della persona giuridica che vuoi configurare.

## <a name="posting-types"></a>Tipi di registrazione

Nelle app Finance and Operations, un tipo di registrazione viene utilizzato per definire una categoria generale per un debito o un credito. Questa categoria è indipendente dal conto principale nella contabilità generale. Esistono tipi di registrazione per ogni addebito o accredito nella contabilità generale.

Un singolo giustificativo può avere uno o più tipi di registrazione. Ad esempio, una transazione registrata tramite un giornale di registrazione generale in cui il conto e il conto di contropartita sono impostati su **Contabilità generale** avrà un tipo di registrazione **Giornale di registrazione contabile** sia per il debito che per il credito. Al contrario, una fattura fornitore avrà più tipi di registrazione. Questi tipi di registrazione includeranno una riga per il saldo fornitore e righe aggiuntive per il movimento di contropartita, ad esempio **Giornale di registrazione contabile**.

Puoi visualizzare il tipo di registrazione nel campo **Tipo di registrazione** nella scheda **Generale** della pagina **Transazioni giustificativo**.

> [!TIP]
> Puoi usare la barra degli strumenti **Personalizzazione** per aggiungere il campo **Tipo di registrazione** alla griglia sulla scheda **Panoramica** o per spostarlo. In questo modo, puoi rendere più facile l'accesso o la visualizzazione di questo campo quando visualizzi i giustificativi.

## <a name="detail-settings-for-a-posting-profile"></a>Impostazione dei dettagli per un profilo registrazione 

Quando configuri i profili di registrazione, il campo **Codice conto** definisce il livello dell'impostazione. Le opzioni disponibili sono: **Tabella**, **Gruppo**, e **Tutto**. L'abbinamento si interrompe dopo la prima corrispondenza e l'ordine va dal livello più specifico al livello meno specifico. Sebbene il campo **Codice conto** potrebbe avere un nome leggermente diverso in alcuni casi, il comportamento e la funzione del campo rimangono gli stessi. Ad esempio, il profilo di registrazione dell'inventario include un campo **Codice articolo** e un campo **Codice conto**. Entrambi i campi hanno i valori **Tabella**, **Gruppo**, e **Tutto**.

Se lasci il campo **Conto principale** vuoto per un profilo di registrazione e non hai configurato un conto principale nella pagina **Conti per transazione automatica** o in una pagina specifica del modulo o della funzionalità, riceverai un messaggio di errore quando registri una transazione che utilizza il tipo di registrazione. In genere, il messaggio sarà "Impossibile trovare il conto per \[tipo di registrazione\]".

### <a name="table-value"></a>Valore tabella

Il valore **Tabella** si riferisce al record master associato al profilo di registrazione. Ogni record di tabella è specifico per un valore. Specifica il valore nel campo che appare dopo il campo **Codice conto**. In genere, questo campo è denominato **Conto** o **Numero di conto/gruppo**. Il nome esatto varia a seconda della pagina in cui appare.

Ad esempio, se stai lavorando con un profilo di registrazione di un cliente, il valore **Tabella** rappresenta un cliente specifico. Pertanto se selezioni **Tabella** nel campo **Codice conto**, devi selezionare il numero del cliente nel campo **Numero conto/gruppo**.

Il valore **Tabella** rappresenta il tipo di record più specifico. Il sistema utilizza sempre questo valore, anche se hai configurato un altro record in cui il valore **Gruppo** o **Tutto** è selezionato. Questo valore sovrascrive anche tutti i valori che hai creato come valori predefiniti nella pagina **Conti per transazioni automatiche**.

Non ti consigliamo di utilizzare il valore **Tabella** come meccanismo principale per la gestione dei profili di registrazione, poiché possono verificarsi problemi di qualità dei dati se viene mantenuto un profilo di registrazione separato per ogni record di dati master. È anche difficile mantenere e riconciliare un profilo di registrazione separato per ogni record di dati master. Questo valore deve essere utilizzato per gestire le eccezioni nei profili di registrazione.

### <a name="group-value"></a>Valore Gruppo

Il valore **Gruppo** si riferisce al record di raggruppamento supportato dal record master associato al profilo di registrazione. Ogni record di gruppo è specifico per un valore. Specifica il valore nel campo che appare dopo il campo **Codice conto**. In genere, questo campo è denominato **Conto** o **Numero di conto/gruppo**. Il nome esatto varia a seconda della pagina in cui appare.

Il valore **Gruppo** richiede di configurare prima un gruppo e poi collegarlo a uno o più record per il conto. Il valore **Gruppo** è meno specifico del valore **Tabella** ma più specifico del valore **Tutto**. Se non è stato configurato alcun record per una tabella, il sistema tenta di trovare un record per il gruppo a cui appartiene il record.

Ad esempio, se stai lavorando con un profilo di registrazione di un cliente e selezioni **Gruppo** nel campo **Codice conto** devi selezionare un gruppo di clienti nel campo **Numero conto/gruppo**. È necessario predefinire i gruppi di clienti nella pagina **Gruppo di clienti** ed è necessario specificare un gruppo di clienti quando si crea un cliente.

Se devi tenere traccia di più conti principali per un determinato tipo di registrazione, ti consigliamo di utilizzare il valore **Gruppo**. Ad esempio, hai tre conti commerciali principali di contabilità clienti: uno per i clienti abituali, uno per i dipendenti e uno per la vendita interaziendale. In questo caso, ti consigliamo di creare tre gruppi di clienti per segmentare i clienti. Quindi mappa ogni gruppo di clienti al conto principale corretto nel profilo di registrazione del cliente. La tabella seguente mostra i tre gruppi di clienti per questo esempio.

| Gruppo di clienti | Name | Description |
|----------------|------|-------------|
| EST | Cliente esterno | Questo gruppo viene utilizzato per tutti i clienti standard esterni. |
| DIP | Dipendenti | Questo gruppo viene utilizzato per tutti i dipendenti che effettuano acquisti dalla tua organizzazione. |
| INT | Vendite interaziendali | Questo gruppo viene utilizzato per tutti i conti cliente interaziendali utilizzati con ordini di acquisto e vendita di integrazione. |

Nel profilo di registrazione, verranno quindi impostate tre righe. Su ogni riga, selezioni il valore **Gruppo** e il relativo conto principale.

### <a name="all-value"></a>Valore Tutto

Il valore **Tutto** indica che le impostazioni si applicano a tutti i record. Se selezioni il valore **Tutto** nel campo **Codice conto** il campo **Numero di conto/gruppo** non è disponibile e non è possibile selezionare un record specifico a cui applicare la configurazione.

Il valore **Tutto** è il valore meno specifico. Viene utilizzato solo se il sistema non riesce a trovare una corrispondenza per il valore **Tabella** o **Gruppo**. Dovresti selezionare il valore **Tutto** quando hai un solo conto principale per un tipo di registrazione specifico.

Ad esempio, quando lavori con un profilo di registrazione del cliente, i conti principali specificati si applicano a tutti gli altri clienti e gruppi di clienti che non dispongono di un record per una tabella (cliente) o un gruppo (gruppo di clienti) specifici.

### <a name="category"></a>Categoria

I profili di registrazione dell'inventario hanno un valore aggiuntivo specifico per la categoria di vendita o la categoria di approvvigionamento. Questo valore assomiglia al valore **Tabella** in quanto si applica solo a una specifica categoria di vendita o approvvigionamento.

### <a name="default-value"></a>Valore predefinito

Se non crei un record per un tipo di registrazione in un profilo di registrazione in cui il campo **Codice conto** è impostato su **Tutto** e il sistema non riesce a trovare un record del profilo di registrazione corrispondente per il valore **Gruppo** o **Tabella**, il sistema torna al valore predefinito che può essere specificato nella pagina **Conti per transazione automatica**. Per ulteriori informazioni, vedi [Conti per transazioni automatiche](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Conti di compensazione

Il termine *conto di compensazione* è spesso usato in contabilità. Alcuni tipi di registrazione nelle app Microsoft Dynamics 365 sono conti di compensazione. In altre parole, il saldo del conto viene compensato o stornato quando viene registrata un'altra transazione. Ad esempio, quando registri un'entrata prodotti di un ordine fornitore, la somma dei costi stimati dei prodotti, più le imposte e le eventuali spese nelle righe dell'ordine fornitore, viene registrata nel tipo di registrazione ratei di acquisto come passività. Successivamente, quando fatturi l'ordine fornitore, il saldo viene stornato dal tipo di registrazione ratei di acquisto e spostato nel conto commerciale Contabilità fornitori.

## <a name="additional-resources"></a>Risorse aggiuntive

Molti moduli in Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, e Dynamics 365 Project Operations hanno un profilo di registrazione o configurazioni aggiuntive che controllano il funzionamento della registrazione nella contabilità generale. Usa i seguenti argomenti per saperne di più sui profili di registrazione e sulle impostazioni di registrazione in ciascun modulo:

- [Conti per transazioni automatiche](accounts-for-auto-transactions.md)
- [Registrazione nella contabilità fornitori](accts-payble-posting.md)
- [Registrazione nella contabilità clienti](accts-recvble-posting.md)
- [Registrazione leasing cespite](../asset-leasing/set-up-lease-posting-accts.md)
- Registrazione di gestione cespiti (presto disponibile)
- Gestione cassa e banche (presto disponibile)
- Conti di registrazione rivalutazione valuta (presto disponibile)
- Registrazione di gestione spese (presto disponibile)
- [Profilo registrazione cespiti](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Registrazione contabile interaziendale (presto disponibile)
- Profilo di registrazione dell'inventario (presto disponibile)
- [Registrazione costi di spedizione](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Panoramica delle definizioni di registrazione](posting-definitions.md)
- Registrazione del controllo produzione (presto disponibile)
- Registrazione gestione progetti e contabilità (presto disponibile)
- Registrazione di gestione servizi (presto disponibile)
- Registrazione delle imposte (presto disponibile)
- Registrazione orari e presenze (presto disponibile)
- Registrazione di gestione trasporti (presto disponibile)
- Profili di registrazione per la gestione degli sconti (presto disponibile)
