---
title: Entità di attività contenitore
description: Questo argomento fornisce informazioni sulle attività dei contenitori, utilizzate per tenere traccia dello stato di avanzamento dei contenitori di spedizione.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 7bb2b97e8885e3b1265f0c93585873c8a64f1dfb
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813057"
---
# <a name="container-activities-entity"></a>Entità di attività contenitore

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Le attività dei contenitori vengono utilizzate per monitorare lo stato di avanzamento dei contenitori di spedizione. Viene creato un record per ogni scalo assegnato al modello di viaggio selezionato al momento della creazione del contenitore di spedizione. I record vengono creati anche quando il container di spedizione viene creato tramite un'entità dati.

Le informazioni sullo stato di avanzamento di un container di spedizione in transito vengono spesso ricevute da un'origine esterna. L'entità delle attività del container consente a un'origine esterna, ad esempio uno spedizioniere, di aggiornare direttamente il record. Pertanto, non è richiesto alcun aggiornamento manuale dei dati.

## <a name="container-activities-itmcontaineractivityentity"></a>Attività del contenitore (ITMContainerActivityEntity)

È possibile utilizzare l'entità delle attività del contenitore (`ITMContainerActivityEntity`) per creare record di attività aggiuntivi. In alternativa, uno spedizioniere può passare gli aggiornamenti per un valore **Data di fine effettiva** confermato.

| Name | Mappatura | Tipo di dati | Chiave | Obbligatorio |
|---|---|---|---|---|
| Data di fine effettiva | ITMContainerActivityTable.ActualEndDate | Data/Ora | Numero | Numero |
| Modalità di consegna | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | Numero | Numero |
| Data di fine stimata | ITMContainerActivityTable.EsimatedDate | Data/Ora | Numero | Numero |
| Numero riga | ITMContainerActivityTable.LineNum | Numeric(32, 16) | **Sì** | Numero |
| Note | ITMContainerActivityTable.Notes | nvarchar(MAX) | Numero | Numero |
| Attività | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | Numero | **Sì** |
| Contenitore di spedizione | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Sì** | **Sì** |
| Viaggio | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Sì** | **Sì** |
| Scalo | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | Numero | **Sì** |
| Provider di servizi | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | Numero | Numero |
| Temperatura | ITMContainerActivityTable.ShipTemperature | Numeric(32, 6) | Numero | Numero |
| Imbarcazione | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | Numero | Numero |
| Data di inizio | ITMContainerActivityTable.StartDate | Data/Ora | Numero | Numero |

## <a name="tracking-control"></a>Controllo della tracciabilità

Il centro di controllo della tracciabilità consente di attivare un aggiornamento di un campo di origine specificato tramite un aggiornamento di un campo di destinazione specificato. Se sia il valore del campo di origine che il valore del campo di destinazione vengono aggiornati utilizzando l'entità delle attività del contenitore, il campo di destinazione mostrerà il valore dell'entità. Questo comportamento è correlato ai record di controllo della tracciabilità che dispongono di un valore **Crea tipo** di *Lead time*.

Per le aree di costo che hanno un **Crea tipo** di *Aggiornamento di stato* o *Vuoto* (che è un valore definito dall'utente), il sistema aggiornerà il campo dello stato o della destinazione del viaggio in base alla configurazione del controllo di tracciabilità.

## <a name="calculated-fields"></a>Campi calcolati

I valori dei seguenti campi in un record di attività del contenitore vengono calcolati in base ai valori di altri campi. Sebbene questi campi calcolati non siano inclusi nell'entità dati, verranno impostati se vengono forniti i campi su cui si basano i calcoli.

- **Giorni stimati** = **Data di fine stimata** – **Data di inizio**
- **Giorni effettivi** = **Data di fine effettiva** – **Data di inizio**
