---
title: Migrazione del tipo di dati valuta per la doppia scrittura
description: Questo argomento descrive come modificare il numero di posizioni decimali supportate dalla doppia scrittura per la valuta.
author: RamaKrishnamoorthy
ms.date: 12/08/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: e9dc3e6c5fbec9636370b64a9bbdcf8a5834d332
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061838"
---
# <a name="currency-data-type-migration-for-dual-write"></a>Migrazione del tipo di dati valuta per la doppia scrittura

[!include [banner](../../includes/banner.md)]



È possibile aumentare il numero di posizioni decimali supportate per i valori di valuta fino a un massimo di 10. Il limite predefinito è quattro cifre decimali. Aumentando il numero di cifre decimali, si contribuisce a prevenire la perdita di dati quando si utilizza la doppia scrittura per sincronizzare i dati. L'aumento del numero di cifre decimali è una modifica con consenso esplicito. Per implementarlo, è necessario richiedere assistenza a Microsoft.

Il processo di modifica del numero di cifre decimali prevede due passaggi:

1. Richiedere la migrazione da Microsoft.
2. Modificare il numero di posizioni decimali in Dataverse.

L'app per finanza e operazioni e Dataverse devono supportare lo stesso numero di cifre decimali nei valori di valuta. In caso contrario, la perdita di dati può verificarsi quando queste informazioni vengono sincronizzate tra le app. Il processo di migrazione riconfigura il modo in cui sono memorizzati i valori di valuta e tasso di cambio, ma non modifica alcun dato. Una volta completata la migrazione, è possibile aumentare il numero di posizioni decimali per i codici valuta e i prezzi e i dati immessi e visualizzati dagli utenti possono avere una maggiore precisione decimale.

La migrazione è facoltativa. Se il supporto per più cifre decimali è vantaggioso per l'utente, consigliamo di prendere in considerazione la migrazione. Le organizzazioni che non richiedono valori con più di quattro cifre decimali non devono essere migrate.

## <a name="requesting-migration-from-microsoft"></a>Richiesta di migrazione da Microsoft

L'archiviazione per le colonne di valuta esistenti in Dataverse non può supportare più di quattro cifre decimali. Pertanto, durante il processo di migrazione, i valori di valuta vengono copiati in nuove colonne interne nel database. Questo processo si verifica continuamente fino alla migrazione di tutti i dati. Internamente, al termine della migrazione, i nuovi tipi di archiviazione sostituiscono i vecchi tipi di archiviazione, ma i valori dei dati rimangono invariati. Le colonne di valuta possono quindi supportare fino a 10 cifre decimali. Durante il processo di migrazione, Dataverse può continuare a essere utilizzato senza interruzioni.

Allo stesso tempo, i tassi di cambio vengono modificati in modo da supportare fino a 12 cifre decimali anziché l'attuale limite di 10. Questa modifica è necessaria in modo che il numero di decimali sia lo stesso nell'app per finanza e operazioni e in Dataverse.

La migrazione non modifica alcun dato. Dopo la conversione delle colonne di valuta e tasso di cambio, gli amministratori possono configurare il sistema in modo da utilizzare fino a 10 posizioni decimali per le colonne di valuta specificando il numero di posizioni decimali per ciascuna valuta di transazione e per i prezzi.

### <a name="request-a-migration"></a>Richiedere una migrazione

Per rendere disponibile questa funzione, inviare un'e-mail a **CDSExpandDecimal@microsoft.com** e includere le seguenti informazioni:

+ **Oggetto:** Richiesta di abilitare il supporto decimale esteso per \<organizationID\>
+ **Corpo:** Vorrei abilitare il supporto decimale esteso per la mia organizzazione \<organizationID\>.

Si verrà contattati da rappresentante Microsoft entro due o tre giorni lavorativi per i passaggi successivi.

Quando si richiede una migrazione, è necessario conoscere i seguenti dettagli e pianificarli di conseguenza:

+ Il tempo necessario per migrare i dati dipende dalla quantità di dati nel sistema. La migrazione di database di grandi dimensioni può richiedere diversi giorni.
+ La dimensione del database aumenta temporaneamente mentre la migrazione è in esecuzione, poiché è necessario spazio aggiuntivo per gli indici. La maggior parte dello spazio aggiuntivo viene liberato al termine della migrazione.
+ Durante il processo di migrazione, se si verificano errori che impediscono il completamento della migrazione, il sistema invia avvisi al supporto Microsoft, in modo che il personale di supporto possa intervenire. Tuttavia, anche se si verificano errori durante la migrazione, Dataverse rimane completamente disponibile per l'uso regolare.
+ Il processo di migrazione non è reversibile.

## <a name="changing-the-number-of-decimal-places"></a>Modifica del numero di posizioni decimali

Al termine della migrazione, Dataverse può memorizzare numeri che hanno più decimali. Gli amministratori possono scegliere quante posizioni decimali vengono utilizzate per codici valuta specifici e per i prezzi. Utenti di Microsoft Power Apps, Power BI e Power Automate possono quindi visualizzare e utilizzare numeri con più cifre decimali.

Per apportare questa modifica, è necessario aggiornare le seguenti impostazioni in Power Apps:

+ **Impostazioni di sistema: precisione della valuta per i prezzi** - La colonna **Impostazione della precisione della valuta utilizzata per la determinazione dei prezzi** definisce come la valuta si comporterà per l'organizzazione quando **Precisione nella determinazione prezzo** è selezionato.
+ **Gestione aziendale: valute** - La colonna **Precisione valuta** consente di specificare un numero personalizzato di posizioni decimali per una valuta specifica. C'è un fallback a livello di organizzazione.

Sono previste alcune limitazioni:

+ Non è possibile configurare la colonna di valuta su una tabella.
+ È possibile specificare più di quattro cifre decimali solo a livello di **Prezzi** e **Valuta di transazione**.

### <a name="system-settings-currency-precision-for-pricing"></a>Impostazioni di sistema: precisione della valuta per i prezzi

Al termine della migrazione, gli amministratori possono impostare la precisione della valuta. Passare a **Impostazioni \> Amministrazione** e selezionare **Impostazioni di sistema**. Quindi, nella scheda **Generale**, cambiare il valore della colonna **Impostazione della precisione della valuta utilizzata per la determinazione dei prezzi**, come mostrato nella figura seguente.

![Impostazioni di sistema per la valuta.](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Gestione aziendale: valute

Se si richiede che la precisione di una valuta specifica differisca dalla precisione della valuta utilizzata per la determinazione dei prezzi, è possibile modificarla. Passare a **Impostazioni \> Gestione aziendale**, selezionare **Valute** e selezionare la valuta da modificare. Quindi impostare la colonna **Precisione valuta** sul numero di posizioni decimali desiderate, come mostrato nella figura seguente.

![Impostazioni della valuta per una valuta locale specifica.](media/specific-currency.png)

### <a name="tables-currency-column"></a>Tabelle: colonna Valuta

Il numero di posizioni decimali che è possibile configurare per colonne di valuta specifiche è limitato a quattro.

### <a name="default-currency-decimal-precision"></a>Precisione decimale della valuta predefinita
Per il comportamento previsto della precisione decimale della valuta predefinita in scenari di migrazione e non migrazione, fai riferimento alla tabella seguente. 

| Data creazione  | Campo Valuta decimale    | Organizzazione esistente (campo valuta non migrato) | Organizzazione esistente (campo valuta migrato) | Nuova organizzazione creata dopo la build 9.2.21062.00134 |
|---------------------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------------|
| Campo valuta creato prima della build 9.2.21111.00146  |     |  |       |
|    | Massima precisione visibile nell'interfaccia utente   | 4 cifre    | 10 cifre    | N/D    |
| | Massima precisione visibile nel database e nell'interfaccia utente dei risultati delle query DB         | 4 cifre   | 10 cifre   | N/D    |
| Campo valuta creato dopo la build 9.2.21111.00146 |    |  |     |   |
|   | Massima precisione decimale visibile nell'interfaccia utente     | 4 cifre   | 10 cifre   | 10 cifre     |
|          | Massima precisione decimale visibile nel database e nell'interfaccia utente dei risultati delle query DB | 10 cifre. Tuttavia, solo 4 sono significative con tutti gli zeri oltre le 4 cifre decimali. Ciò consente una migrazione più semplice e veloce dell'organizzazione, se necessario. | 10 cifre      | 10 cifre     |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
