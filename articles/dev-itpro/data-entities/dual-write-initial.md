---
title: Ordine di esecuzione per la sincronizzazione iniziale di Finance and Operations e Common Data Service
description: In questo argomento specifica l'ordine di sincronizzazione che è necessario seguire per creare i dati iniziali.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797300"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Ordine di esecuzione per la sincronizzazione iniziale di Finance and Operations e Common Data Service

Prima di utilizzare l'integrazione dei dati, è necessario creare i dati iniziali necessari per clienti, fornitori e i contatti. Ad esempio, se si desidera creare un nuovo articolo **Gruppo di fornitori** e impostare il relativo **Termini di pagamento** come **Net30**, prima di tentiate di creare l'articolo **Gruppo di fornitori** è necessario assicurarsi che **Net30** sia presente sia in Finance and Operations che in Common Data Service. (In futuro, rilasceremo una funzionalità per la piattaforma di doppia scrittura denominata **Sincronizzazione iniziale**. Farà una sincronizzazione una-tantum dei dati tra Finance and Operations e Common Data Service come parte dell'impostazione di doppia scrittura).

Suggerimenti: Stiamo rilasciando una mappa di doppia scrittura per tutti i dati di riferimento inclusi **Termini di pagamento** (condizioni di pagamento). Se si dispone già dei dati iniziali in un sistema, una piccola operazione di aggiornamento su un record può attivare la doppia scrittura su tale record. 

È necessario seguire il seguente ordine di priorità e accertarsi che i dati iniziali sono disponibili sia in Finance and Operations che in Common Data Service.   

## <a name="vendor"></a>Fornitore

L'ordine dell'esecuzione per Fornitore è:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Cliente (Organizzazione)

L'ordine dell'esecuzione per Cliente è:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Contatto (Persona)

L'ordine dell'esecuzione per Contatto è:

```
Customer
Vendor               
```
