---
title: Configurare e gestire la registrazione del database
description: Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae974436469c00a3df6fd40d9d60521a0883a917
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054814"
---
# <a name="configure-and-manage-database-logging"></a>Configurare e gestire la registrazione del database

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puoi tenere traccia delle modifiche a tabelle e campi in Dynamics 365 Human Resources con la registrazione del database. In questo argomento viene descritto come:

- Gestire la sicurezza e le prestazioni per la registrazione del database
- Imposta la registrazione del database
- Pulisci i log del database

## <a name="overview-of-database-logging"></a>Panoramica della registrazione del database

La registrazione del database tiene traccia di modifiche specifiche a tabelle e campi in Microsoft Dynamics 365 Human Resources. Queste modifiche includono l'inserimento, l'aggiornamento o l'eliminazione. La registrazione del database memorizza un record di modifiche a tabelle o campi nella tabella di registro del database.

Gli usi aziendali della registrazione del database includono:

- Creazione di un record di controllo delle modifiche a tabelle specifiche che contengono informazioni riservate.
- Tracciamento di singole transazioni. La registrazione del database non è intesa per tenere traccia delle transazioni automatizzate eseguite in processi batch.

## <a name="security-for-database-logging"></a>Sicurezza per la registrazione del database

I registri del database possono contenere dati sensibili. Limita l'accesso per includere solo i ruoli di sicurezza che richiedono l'accesso ai dati del registro.

## <a name="database-logging-and-performance"></a>Registrazione e prestazioni del database

Sebbene la registrazione nel database possa risultare utile da un punto di vista commerciale, può risultare costosa in termini di utilizzo e gestione delle risorse. Le implicazioni sulle prestazioni della registrazione del database includono:

- La tabella dei registri del database può crescere rapidamente e causare un aumento delle dimensioni del database. La crescita dipende dalla quantità di dati registrati che decidi di conservare. Per impostazione predefinita, la tabella di registro del database conserva solo 30 giorni di dati di registro. 

- La registrazione del database può influire negativamente sui processi automatizzati di lunga durata, come le importazioni di dati di lunga durata.

### <a name="best-practices"></a>Procedure consigliate

Per migliorare le prestazioni, limitare le voci del registro selezionando campi specifici e non intere tabelle. Per aiutare a mantenere le prestazioni generali, la registrazione del database è limitata a 20 tabelle.

> [!NOTE]
> In caso di campi singoli, puoi registrare solo gli aggiornamenti.

## <a name="set-up-database-logging"></a>Imposta la registrazione del database

Puoi anche usare la procedura guidata **Registrazione modifiche database** per impostare la registrazione del database. La procedura guidata fornisce un modo flessibile per impostare la registrazione per tabelle o campi.

1. Vai ad **Amministrazione sistema> Collegamenti> Database > Impostazione registro database**. Seleziona **Nuovo** per avviare la procedura guidata **Registrazione modifiche database**.
2. Selezionare **Avanti**. 
3. Nella pagina **Tabelle e campi** della procedura guidata, seleziona le tabelle e i campi in cui vuoi abilitare la registrazione del database e seleziona **Avanti**.

   > [!Note]
   > La registrazione del database non è disponibile su tutte le tabelle nel database Human Resources La selezione di **Mostra tutte le tabelle** sotto l'elenco espande l'elenco di tabelle e campi per mostrare tutte le tabelle di database per le quali è disponibile la registrazione del database, ma questo sarà un sottoinsieme dell'elenco completo delle tabelle di database.

4. Nella pagina **Tipi di modifica** della procedura guidata, seleziona le operazioni sui dati per le quali vuoi tenere traccia delle modifiche per ciascuna delle tabelle e dei campi, quindi seleziona **Avanti**. Vedere la tabella seguente per una descrizione delle operazioni sui dati disponibili per la registrazione.
5. Nella pagina **Fine** rivedi le modifiche che verranno apportate e seleziona **Fine**.

| Operazione | descrizione |
| -- | -- |
| Tieni traccia delle nuove transazioni | Crea un registro per i nuovi record che vengono creati nella tabella. |
| Aggiornamento | Creare un registro per gli aggiornamenti ai record della tabella o per gli aggiornamenti ai campi selezionati individualmente nella tabella. Se selezioni di registrare gli aggiornamenti per la tabella, viene creato un record di registro ogni volta che viene effettuato un aggiornamento a qualsiasi campo di qualsiasi record nella tabella. Se selezioni di registrare gli aggiornamenti per campi specifici, viene creato un record di registro solo quando vengono effettuati aggiornamenti a quei campi dei record di tabella. |
| CANC | Crea un registro per i record eliminati dalla tabella. |
| Rinomina chiave | Crea un record di registro quando una chiave di tabella viene rinominata. |


## <a name="clean-up-database-logs"></a>Pulisci i log del database

Puoi eliminare tutti o parte dei registri del database, utilizzando le seguenti opzioni:

- Seleziona tutti i registri per una determinata tabella.
- Seleziona tipi specifici di registro del database.
- Seleziona la data e l'ora in cui è stato creato un registro.

Per configurare la pulitura del registro del database, effettua le seguenti operazioni: 

1. Vai ad **Amministrazione sistema> Collegamenti> Database > Registro database**. Seleziona **Pulisci registro**.

2. Scegli un metodo di selezione dei registri da eliminare inserendo una delle seguenti opzioni:

   - ID tabella
   - Tipo di registro
   - Data e ora creazione

3. Usa la scheda **Pulitura registro database** per determinare quando eseguire l'attività di pulizia del registro. Per impostazione predefinita, i registri del database sono disponibili per 30 giorni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
