---
title: Nascondere le modalità di consegna non vettore dalle opzioni di spedizione nel POS
description: In questo argomento viene descritta un'opzione di configurazione che può impedire la visualizzazione delle modalità di consegna non vettore per la selezione quando gli ordini di spedizione vengono creati nell'applicazione POS.
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: a5f08fc86dc093fd0ead219b808fa720a43f6b6b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797120"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Nascondere le modalità di consegna non vettore dalle opzioni di spedizione nel POS


[!include [banner](includes/banner.md)]

In questo argomento viene descritta un'opzione di configurazione disponibile per l'applicazione POS. Questa opzione di configurazione modifica il comportamento per la selezione di una modalità di consegna quando gli ordini di spedizione vengono creati in POS.

Quando gli utenti creano gli ordini di spedizione per il cliente nel POS, possono selezionare una modalità di consegna per la spedizione. Questa funzionalità è disponibile indipendentemente dal fatto che si invii l'intero ordine o solo righe selezionate.

Per impostazione predefinita, la finestra di dialogo in cui è selezionata una modalità di consegna mostra tutte le modalità di consegna valide per la combinazione di un canale, un articolo e un indirizzo di consegna. Queste modalità di consegna sono definite nella pagina **Modi di consegna** in Headquarters (**Vendite e marketing \> Impostazioni \> Distribuzione \> Modi di consegna**). I modi di consegna "non vettore", ad esempio **Esegui** o **Ritiro**, potrebbero essere disponibili per la selezione nella finestra di dialogo.

Tuttavia, è stata aggiunta una funzione che consente di nascondere le modalità di consegna non vettore nella finestra di dialogo. Per attivare questa funzionalità, nella pagina **Parametri di commercio**, nella scheda **Ordini cliente**, impostare l'opzione per **visualizzare solo le opzioni della modalità di consegna vettore per ordini di spedizione** su **Sì**. Dopo aver attivato questa funzionalità ed eseguito i processi di distribuzione appropriati per sincronizzare le informazioni con il database del canale, le modalità di consegna non vettore non verranno visualizzate per la selezione durante il processo di creazione degli ordini di spedizione in POS.


[!INCLUDE[footer-include](../includes/footer-banner.md)]