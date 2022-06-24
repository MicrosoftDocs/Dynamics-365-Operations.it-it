---
title: Codici di errore per il controllo dello stato della mappa della tabella
description: Questo articolo descrive i codici di errore per il controllo dello stato della mappa della tabella.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 3ae78077fc716311c38620b14665af3983a44c2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884085"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Codici di errore per il controllo dello stato della mappa della tabella

[!include [banner](../../includes/banner.md)]



Questo articolo descrive i codici di errore per il controllo dello stato della mappa della tabella.

## <a name="error-100"></a>Errore 100

Il messaggio di errore è "La versione minima richiesta della piattaforma Finanza e operazioni è PU 43 per eseguire i suggerimenti di Finanza e operazioni".

La funzione richiede aggiornamenti della piattaforma per la versione 10.0.19 o successiva delle app per finanza e operazioni.

## <a name="error-400"></a>Errore 400

Il messaggio di errore è "Nessun dato di registrazione degli eventi aziendali trovato per l'entità \{Finanza e operazioni UniqueEntityName\} il che significa che la mappa non è in esecuzione o tutte le mappe dei campi sono unidirezionali".

## <a name="error-500"></a>Errore 500

Il messaggio di errore è "Nessuna configurazione di progetto trovata per il progetto \{nome del progetto\}. Potrebbe essere che il progetto non è abilitato o che tutte le mappature dei campi sono unidirezionali da Customer Engagement a Finanza e operazioni."

Controlla le mappature per la mappa della tabella. Se sono unidirezionali dalle app customer engagement alle app per finanza e operazioni, non viene generato traffico per la sincronizzazione live dalle app per finanza e operazioni per Dataverse.

## <a name="error-900"></a>Errore 900

Il messaggio di errore è "Formato del filtro di origine non valido \{sourceFilter\} per l'entità \{Finanza e operazioni UniqueEntityName\}."

Il filtro di origine specificato nella mappa della tabella per le app per finanza e operazioni non è sintatticamente corretto. Per convalidare i criteri di filtro, vedi [Risolvere i problemi di sincronizzazione live](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Errore 1000

Il messaggio di errore è "La query dell'entità \{Finanza e operazioni UniqueEntityName\} utilizzata per la sincronizzazione live a doppia scrittura è \{Finanza e operazioni EntityFilterQueryString\}. I record che soddisfano i criteri di query verranno raccolti per la sincronizzazione in tempo reale."

La query dell'entità che è stata restituita è la query SQL di supporto per l'entità. Verifica la presenza di join interni o filtri nella query che determinano i dati aziendali che vengono prelevati per la sincronizzazione in tempo reale. I join interni e i filtri sono condizioni obbligatorie che devono essere soddisfatte per ogni record che viene prelevato per la sincronizzazione live a doppia scrittura.

## <a name="error-1300"></a>Errore 1300

Il messaggio di errore è "Campi virtuali \{s.EntityFieldName\} per l'entità \{Finanza e operazioni EntityMetadata.EntityProperties.LogicalEntityName\} potrebbero non essere tracciati per la doppia scrittura."

I campi virtuali delle tabelle Finanza e operazioni non sono abilitati per il monitoraggio. La sincronizzazione in tempo reale può sincronizzare i dati, ma non sarà in grado di rilevare le modifiche apportate alle colonne.

## <a name="error-1500"></a>Errore 1500

Il messaggio di errore è "È necessario almeno un campo mappato a un campo non di ricerca in customer engagement per abilitare il tracciamento sull'origine dati \{datasource.DataSourceName\}".

L'origine dati dell'entità non ha un campo mappato per la doppia scrittura. Le modifiche alla tabella sottostante non verranno rilevate per la doppia scrittura.

## <a name="error-1600"></a>Errore 1600

Il messaggio di errore è "L'origine dati:: \{datasource.DataSourceName\} per l'entità \{Finanza e operazioni EntityMetadata.EntityProperties.LogicalEntityName\} ha un intervallo. Solo i record che soddisfano la condizione di intervallo vengono prelevati per l'uscita."

Le entità nelle app per finanza e operazioni possono avere origini dati in cui sono abilitati gli intervalli di filtri. Questi intervalli definiscono i record che vengono prelevati come parte della sincronizzazione in tempo reale. Se alcuni record vengono saltati dalle app per finanza e operazioni per Dataverse, controlla se i record soddisfano i criteri di intervallo sull'entità. Un modo semplice per eseguire questo controllo consiste nell'eseguire una query SQL simile all'esempio seguente.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Errore 1700

Il messaggio di errore è "La tabella: \{datasourceTable.Key.subscribedTableName\} per entità \{datasourceTable.Key.entityName\} è tracciata per entità \{origTableToEntityMaps.EntityName\}. Le stesse tabelle tracciate per più entità possono influire sulle prestazioni del sistema per le transazioni di sincronizzazione in tempo reale."

Se la stessa tabella viene tracciata da più entità, qualsiasi modifica alla tabella attiverà la valutazione a doppia scrittura per le entità collegate. Sebbene le clausole di filtro inviino solo i record validi, la valutazione potrebbe causare un problema di prestazioni se sono presenti query di lunga durata o piani di query non ottimizzati. Questo problema potrebbe non essere evitabile dal punto di vista aziendale. Tuttavia, se sono presenti molte tabelle che si intersecano in più entità, dovresti prendere in considerazione la semplificazione delle entità o il controllo delle ottimizzazioni per le query di entità.

## <a name="error-1800"></a>Errore 1800
Il messaggio di errore è "Origine dati: {} per l'entità CustCustomerV3Entity include un valore di intervallo. Gli aggiornamenti dei record in entrata da Dataverse a Finance and Operations possono essere influenzati dai valori di intervallo sull'entità. Testa gli aggiornamenti dei record da Dataverse a Finance and Operations con record che non corrispondono ai criteri di filtro per convalidare le impostazioni."

Se è presente un intervallo specificato nell'entità nelle app per la finanza e le operazioni, la sincronizzazione in entrata da Dataverse alle app per la finanza e le operazioni devono essere testate per il comportamento di aggiornamento sui record che non soddisfano i criteri di questo intervallo. Qualsiasi record che non corrisponde all'intervallo viene trattato come un'operazione di inserimento dall'entità. Se è presente un record nella tabella sottostante, l'inserimento avrà esito negativo. Ti consigliamo di testare questo caso d'uso per tutti gli scenari prima della distribuzione in produzione.

## <a name="error-1900"></a>Errore 1900
Il messaggio di errore è "Entità: ha {} origini dati che non vengono tracciate per la doppia scrittura in uscita. Ciò può influire sulle prestazioni delle query di sincronizzazione in tempo reale. Rimodella l'entità in Finance and Operations per rimuovere le origini dati e le tabelle inutilizzate o implementare getEntityRecordIdsImpactedByTableChange per ottimizzare le query di runtime."

Se sono presenti molte origini dati che non vengono utilizzate per il monitoraggio nella sincronizzazione in tempo reale effettiva dalle app per la finanza e le operazioni, è possibile che le prestazioni delle entità possano influire sulla sincronizzazione in tempo reale. Per ottimizzare le tabelle tracciate, utilizza il metodo getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Errore 5000
Il messaggio di errore è "I plug-in di sincronizzazione sono registrati per gli eventi di gestione dei dati per gli account di entità. Questi possono influire sulla sincronizzazione iniziale e sulle prestazioni di importazione della sincronizzazione in tempo reale in Dataverse. Per prestazioni ottimali, modifica i plug-in per l'elaborazione asincrona. Elenco dei plug-in registrati {}."

I plug-in sincroni su un'entità Dataverse possono influire sulla sincronizzazione in tempo reale e sulle prestazioni della sincronizzazione iniziale in quanto si aggiunge al carico della transazione. L'approccio consigliato è disattivare i plug-in o rendere questi plug-in asincroni se si verificano tempi di caricamento lenti nella sincronizzazione iniziale o nella sincronizzazione in tempo reale per una particolare entità.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
