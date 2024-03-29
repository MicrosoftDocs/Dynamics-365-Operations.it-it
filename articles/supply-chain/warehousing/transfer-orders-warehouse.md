---
title: Impostare i magazzini per gli ordini di trasferimento
description: In questo articolo viene descritto come impostare magazzini per gli ordini di trasferimento.
author: Mirzaab
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 984f90343805d35833b7ddd1a175af5833c23dd5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905517"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Impostare i magazzini per gli ordini di trasferimento 

[!include [banner](../includes/banner.md)]

Utilizzando i livelli magazzino è possibile creare una gerarchia per supportare gli ordini di trasferimento tra magazzini. In base a questa impostazione, tramite la programmazione generale vengono calcolale le richieste articoli a livello di singolo magazzino e vengono generati gli ordini di trasferimento pianificati da un magazzino di origine assegnato per soddisfare tali richieste.

1.  Fare clic su **Gestione inventario > Impostazioni > Suddivisione scorte > Magazzino**.

2.  Selezionare il magazzino che si desidera ricaricare.

3.  Nella scheda dettaglio **Pianificazione generale**, selezionare la casella di controllo **Ricaricamento**.

4.  Nel campo **Magazzino principale** selezionare il magazzino che si desidera assegnare come magazzino di ricaricamento. Tramite la programmazione generale viene calcolato un fabbisogno di trasferimento per il magazzino selezionato e viene generato un ordine di trasferimento pianificato dal campo **Magazzino principale** assegnato.
   
    > [!NOTE]
    > <P>Se si deseleziona la casella di controllo <STRONG>Ricaricamento</STRONG>, al magazzino selezionato verrà assegnato un livello di magazzino in relazione all'opzione selezionata in <STRONG>Magazzino principale</STRONG>, ma il <STRONG>Magazzino principale</STRONG> non viene impostato come magazzino di ricaricamento.</P>

5.  Chiudere la pagina per applicare la nuova impostazione.


> [!TIP]
> <P>Se si desidera assegnare un magazzino per il ricaricamento, è necessario impostarlo prima come dimensione di immagazzinamento nella pagina modulo <STRONG>Gruppi di dimensioni di immagazzinamento</STRONG>. In questa pagina, selezionare i campi <STRONG>Attivo</STRONG> e <STRONG>Piano di copertura per dimensione</STRONG> per il magazzino.</P>

## <a name="set-up-transport-lead-time"></a>Impostare il lead time di spedizione

È inoltre necessario impostare il lead time di spedizione tra magazzini nella pagina **Giorni di spedizione**. 
1. Passare a **Gestione inventario > Impostazioni > Distribuzione > Giorni di spedizione**.
2. Nel campo **Punto di ricevimento** selezionare il **magazzino**.
3. Selezionare **Magazzino di spedizione**, **Magazzino ricevente** e **Giorni di spedizione**. 
4. (Facoltativo) È inoltre possibile impostare il tempo di spedizione, a seconda della modalità di consegna, nella scheda **Giorni di spedizione per modalità di consegna**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]