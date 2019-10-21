---
title: Ordine di esecuzione per la sincronizzazione iniziale delle app Finance and Operations e Common Data Service
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
ms.openlocfilehash: 3110cb809558d168e9d97f640701b249caf73f6c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184510"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a>Ordine di esecuzione per la sincronizzazione iniziale delle app Finance and Operations e Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Prima di utilizzare l'integrazione dei dati, è necessario creare i dati iniziali necessari per clienti, fornitori e i contatti. Ad esempio, se si desidera creare un nuovo articolo **Gruppo di fornitori** e impostare il relativo valore **Termini di pagamento** su **Net30**. In questo caso, prima di provare a creare l'articolo **Gruppo di fornitori**, verificare che **Net30** sia presente nell'applicazione e in Common Data Service. (in futuro, Microsoft rilascerà una funzionalità per la piattaforma di doppia scrittura denominata Sincronizzazione iniziale. Questa funzionalità eseguirà una sincronizzazione una-tantum dei dati tra l'applicazione e Common Data Service come parte dell'impostazione di doppia scrittura).

> [!TIP]
> Microsoft sta rilasciando una mappa di doppia scrittura per tutti i dati di riferimento inclusi **Termini di pagamento** (condizioni di pagamento). Se si dispone già dei dati iniziali in un sistema, una piccola operazione di aggiornamento su un record può attivare la doppia scrittura su tale record.

È necessario seguire il seguente ordine di priorità e accertarsi che i dati iniziali siano disponibili sia nell'applicazione che in Common Data Service.

## <a name="vendor"></a>Fornitore

Di seguito è riportato l'ordine di esecuzione dell'entità **Fornitore** :

1. Gruppo di fornitori

    1. Termini di pagamento

        1. Righe e giorno di pagamento
        2. Scadenzario pagamenti

2. Metodo di pagamento fornitore

## <a name="customer-organization"></a>Cliente (Organizzazione)

Di seguito è riportato l'ordine di esecuzione dell'entità **Cliente**:

1. Gruppo di clienti

    1. Termini di pagamento

        1. Righe e giorno di pagamento
        2. Pagamento 

2. Metodo di pagamento clienti

## <a name="contact-person"></a>Contatto (Persona)

Di seguito è riportato l'ordine di esecuzione dell'entità **Contatto**:

1. Cliente
2. Fornitore
