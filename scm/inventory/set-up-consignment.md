---
title: Spedizione di impostazione
description: In questo argomento viene illustrato come configurare le operazioni di inventario spedizione in entrata.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: afa59439e06aad9d669eb352a9837a013f447249
ms.openlocfilehash: 48e3f7f33bedf33bee5a7c2882e90743feac8687
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-consignment"></a>Spedizione di impostazione

In questo argomento viene illustrato come configurare le operazioni di inventario spedizione in entrata. 

L'inventario spedizione è l'inventario che appartiene a un fornitore ma immagazzinato presso il sito del cliente. Quando si è pronti per consumare o utilizzare l'inventario, si assume la proprietà dell'inventario. In questo argomento viene descritta l'impostazione necessaria per abilitare i processi di spedizione. Per ulteriori informazioni sui processi di spedizione, vedere [Spedizione](consignment.md).

## <a name="inventory-owners"></a>Proprietari inventario
Per registrare l'inventario spedizione in entrata fisico, è necessario definire un proprietario fornitore. Questo viene effettuato nella pagina **Proprietario inventario**. Quando si seleziona un **Conto fornitore**, vengono generati i valori predefiniti per i campi **Nome** e **Proprietario**. Il valore nel campo **Proprietario** sarà visibile al fornitore, pertanto è possibile modificarlo se i nomi di conto fornitore non sono facili da riconoscere per le persone esterne. È possibile modificare il campo **Proprietario**, ma solo fino al passaggio quando si salva il record **Proprietario inventario**. Il campo **Nome** viene popolato automaticamente con il nome della parte a cui il conto fornitore è associato e non può essere modificato. 

[elencati proprietari![(]. /media/inventory-owners.png)](. /media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Gruppo di dimensioni di tracciabilità
Gli articoli che verranno utilizzati nei processi di spedizione devono essere associati a un **Gruppo di dimensioni di tracciabilità** dove la dimensione **Proprietario** è impostata su **Attivo**. La dimensione Proprietario ha sempre le opzioni **Inventario fisico** e **Inventario finanziario** selezionate. **Piano di copertura per dimensione** non è mai selezionato. 

[gruppo di dimensioni di tracciabilità![(]. /media/tracking-dimension-group.png)](. /media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Giornale di registrazione modifiche proprietà inventario
Il giornale di registrazione **Modifica proprietà inventario **viene utilizzato per registrare il trasferimento di proprietà dell'inventario di spedizione dal fornitore alla persona giuridica che lo consuma. Come qualsiasi giornale di registrazione magazzino, deve essere identificatocon un nome di giornale di registrazione magazzino. Questi nomi vengono creati nella pagina **Nomi giornale di registrazione magazzino** e **Tipo di giornale di registrazione** deve essere impostato su **Modifica proprietà**. 

[inventario-proprietà-modifica- giornale di registrazione![(]. /media/inventory-ownership-change-journal.png)](. /media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Collaborazione fornitore nei processi di spedizione
Se i fornitori utilizzano l'interfaccia di collaborazione fornitore, possono utilizzare questa per monitorare il consumo dell'inventario nel sito. Per ulteriori informazioni su come impostare i fornitori per utilizzare la collaborazione fornitore, vedere [Configurazione della sicurezza per gli utenti di collaborazione fornitore](../procurement/configure-security-vendor-portal-users.md).


