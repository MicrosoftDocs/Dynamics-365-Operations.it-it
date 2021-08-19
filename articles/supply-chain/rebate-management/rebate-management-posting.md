---
title: Configurazione della registrazione della gestione degli sconti
description: In questo argomento viene descritto come impostare i profili di registrazione. I profili di registrazione vengono utilizzati per determinare i movimenti di registrazione per le righe di calcolo della gestione degli sconti.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 4eb0c38baa0b46c535e9394673d5a046f761ac71a9633edcc6ee7f237ff7691d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725676"
---
# <a name="rebate-management-posting-setup"></a>Configurazione della registrazione della gestione degli sconti

[!include [banner](../includes/banner.md)]

I profili di registrazione della gestione degli sconti vengono utilizzati per determinare i movimenti di registrazione per le righe di calcolo della gestione degli sconti. Quando un profilo di registrazione viene selezionato nell'intestazione della transazione, si applica a tutte le righe della transazione.

Questa funzionalità funziona in tutte le società (persone giuridiche). Puoi specificare la società per cui matureranno gli accantonamenti e da cui verranno pagate le richieste. È inoltre possibile impostare diversi conti di addebito di accantonamento e conti di credito di annullamento per società di registrazione di origine.

Per impostare i profili di registrazione della gestione degli sconti per clienti e fornitori, vai a **Gestione degli sconti \> Impostazione registrazione gestione scnti \> Profili di registrazione gestione degli sconti**. La pagina **Profili di registrazione della gestione degli sconti** include un riquadro elenco che mostra tutti i profili esistenti. Puoi utilizzare i pulsanti nel riquadro Azioni per aggiungere o rimuovere i profili nell'elenco.

Le sezioni rimanenti di questo argomento descrivono come utilizzare i campi disponibili quando crei o modifichi un profilo.

## <a name="posting-profile-header"></a>Intestazione profilo di registrazione

La tabella seguente descrive le impostazioni disponibili nella sezione dell'intestazione di ogni profilo di registrazione della gestione degli sconti.

| Campo | descrizione |
|---|---|
| Profilo registrazione | Immetti un nome univoco per il profilo. |
| descrizione | Immetti una descrizione del profilo. |
| Modulo | Seleziona il modulo associato a sconti e royalty del profilo (*Cliente* o *Fornitore*). |
| Tipo | Seleziona il tipo di profilo (*Sconto* o *Royalty*). |
| Tipo di pagamento | <p>Questo campo determina il formato dell'output dello sconto registrato.<p><p>Quando il campo **Tipo** è impostato su *Sconto*, sono disponibili i seguenti valori:</p><ul><li>*Paga utilizzando la contabilità fornitori* - Quando si registra uno sconto per il cliente, viene creata una fattura fornitore per il fornitore della rimessa impostata sul cliente dello sconto. Quando si registra uno sconto per il cliente, viene creato un conto fornitore per lo sconto.</li><li>*Detrazioni cliente* - Quando si registra lo sconto, viene creato un giornale di registrazione detrazioni cliente per il cliente dello sconto.</li><li>*Detrazioni cliente fattura fiscale* - Quando si registra lo sconto, viene creata una fattura a testo libero per il cliente dello sconto.</li><li>*Fondi per promozioni* - Quando si registra lo sconto, viene creato un giornale di registrazione detrazioni cliente per il cliente dello sconto.</li><li>*Report* - Quando si registra lo sconto, viene creato un giornale di registrazione detrazioni cliente per il cliente dello sconto.</li></ul><p>Quando il campo **Tipo** è impostato su *Royalty*, sono disponibili i seguenti valori:</p><ul><li>*Paga utilizzando la contabilità fornitori* - Quando si registra lo sconto, viene creato un conto fornitore per lo sconto.</li><li>*Report* - Quando si registra lo sconto, viene creato un conto fornitore per lo sconto.</li></ul><p>Per ulteriori informazioni vedi la sezione seguente [Tipi di pagamento](#payment-types). |
| Società | Seleziona la società (persona giuridica) per cui matureranno gli accantonamenti e da cui verranno pagate le richieste. |

### <a name="payment-types"></a>Tipi di pagamento

La tabella seguente riassume come le varie impostazioni del campo **Tipo di pagamento** influiscono sulla posizione in cui vengono registrati i pagamenti. I pagamenti possono essere registrati in un conto cliente, conto fornitore o conto rimessa, a seconda della transazione di destinazione e del tipo di sconto.

| Tipo di pagamento | Tipo di transazione di destinazione | Tipo di sconto | Pagamento a (conto fattura) |
|---|---|---|---|
| Paga mediante Contabilità fornitori | Giornale di registrazione fatture fornitore | Sconto cliente | Conto fornitore della rimessa del cliente |
| Paga mediante Contabilità fornitori | Giornale di registrazione fatture fornitore | Royalty cliente | Account fornitore |
| Paga mediante Contabilità fornitori | Giornale di registrazione fatture fornitore | Sconto fornitori | Account fornitore |
| Detrazioni cliente | Giornale di registrazione giornaliero | Sconto cliente | Account cliente |
| Detrazioni cliente fattura fiscale | Fattura a testo libero | Sconto cliente | Account cliente |
| Fondi per promozioni | Giornale di registrazione giornaliero | Sconto cliente | Account cliente |
| Creazione di report | Giornale di registrazione giornaliero | Sconto cliente | Account cliente |
| Creazione di report | Giornale di registrazione fatture fornitore | Royalty cliente | Account fornitore |
| Creazione di report | Giornale di registrazione fatture fornitore | Sconto fornitori | Account fornitore |

> [!NOTE]
> Considera i seguenti punti durante la configurazione delle [transazioni di gestione degli sconti](rebate-management-deals.md):
>
> - Per le transazioni in cui il campo **Riconcilia per** è impostato su *Transazione*, non puoi utilizzare il conto transazione dinamico durante la registrazione. È necessario utilizzare un conto cliente o fornitore specificato.
> - Per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga*, puoi utilizzare un profilo di registrazione che esegue l'offset a un conto transazione dinamico sulla riga della transazione, poiché il cliente o il fornitore è impostato per riga della transazione.

## <a name="posting-fasttab"></a>Scheda dettaglio Registrazione

La tabella seguente descrive i campi disponibili nella scheda dettaglio **Registrazione** di ogni profilo di registrazione della gestione degli sconti.

| Campo | descrizione |
|---|---|
| Tipo di accredito | Scegli se accreditare un conto CoGe o un cliente. Se il campo **Tipo di pagamento** nell'intestazione è impostato su *Detrazioni cliente fattura fiscale*, questo campo è impostato su *Conto CoGe*. Per gli sconti fornitore, questo campo è impostato su *Conto CoGe*. |
| Conto in Avere | Seleziona il conto in cui vengono registrati gli importi in Avere quando vengono effettuati accantonamenti di sconti. Questo conto verrà utilizzato anche come conto di contropartita quando lo sconto viene registrato per accreditare il cliente o addebitare il fornitore. |
| Nome giornale di registrazione<br>(Nella sezione **Accantonamento**) | Seleziona il nome del giornale di registrazione da utilizzare per registrare l'accantonamento registrato. |
| Tipo | Scegli se registrare lo sconto in un conto CoGe, un cliente o un fornitore. Se il campo **Tipo di pagamento** nell'intestazione è impostato su *Detrazioni cliente fattura fiscale*, questo campo è impostato su *Cliente/Fornitore*. |
| Usare l'origine conto | <p>Selezionare uno dei seguenti valori:</p><ul><li>*Conto fisso* - Se selezioni questo valore, devi specificare un conto nel campo **Conto sconti**.</li><li>*Conto righe di transazione* - Utilizza il conto cliente o fornitore specificato nella riga dello sconto. Puoi selezionare questo valore solo per le transazioni in cui il campo **Riconcilia per** è impostato su *Riga* e le righe di transazione in cui il campo **Codice conto** è impostato su *Tabella*. Non si applica ai profili di registrazione delle royalty dei clienti o agli sconti fornitore basati su ordini cliente.</li></ul> |
| Conto sconti | Il conto in cui verranno registrate le spese effettive degli sconti. |
| Nome giornale di registrazione<br>Nel gruppo di campi **Gestione degli sconti** | Seleziona il nome del giornale di registrazione da utilizzare per registrare una nota di credito per l'importo dello sconto al cliente o al fornitore. Questo campo non è disponibile quando il campo **Tipo di pagamento** nell'intestazione è impostato su *Detrazioni cliente fattura fiscale*. Per gli sconti cliente, i nomi dei giornali di registrazione di tipo *Giornaliero* sono disponibili. Per le royalty dei clienti e gli sconti dei fornitori, i nomi dei giornali di registrazione di tipo *Registrazione fattura fornitore* sono disponibili. |
| Fascia IVA articoli | Specificare se lo sconto è tassabile. |
| Nome giornale di registrazione<br>Nel gruppo di campi **Eliminazione** | Se lo sconto registrato non è uguale all'accantonamento, la differenza può essere cancellata. Seleziona il nome del giornale di registrazione da utilizzare per registrare l'annullamento registrato. |

## <a name="posting-by-company-fasttab"></a>Scheda dettaglio Registrazione per società

La scheda dettaglio **Registrazione per società** di ogni profilo di registrazione della gestione degli sconti consente di specificare il conto di registrazione utilizzato da ciascuna società (persona giuridica) nella griglia.

Utilizza i pulsanti nella barra degli strumenti per aggiungere società nella griglia o rimuoverle. Ogni volta che aggiungi una riga alla griglia, usa il campo **Società** per specificare la persona giuridica per quella riga. Il valore del campo **Nome** viene quindi impostato automaticamente.

Seleziona la riga per ciascuna società, quindi inserisci le seguenti informazioni utilizzando i campi sotto la griglia:

- **Tipo di debito** – Seleziona se addebitare un conto CoGe o un fornitore. Per le royalty e gli sconti cliente, questo campo è impostato su *Conto CoGe*.
- **Conto in Dare** - Immetti il conto in cui viene registrato l'importo in addebito quando vengono effettuati gli accantonamenti per lo sconto.
- **Conto principale** - Seleziona il conto principale per gli annullamenti.
