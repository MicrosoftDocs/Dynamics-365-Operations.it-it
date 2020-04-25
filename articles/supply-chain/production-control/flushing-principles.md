---
title: Principi di registrazione del consumo di materiali
description: Questo argomento descrive i quattro principi di registrazione utilizzati per il consumo di materie prime.
author: johanhoffmann
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9f7546b70ddef30d88a79b00fe31d4e82d9bfb9b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211539"
---
# <a name="flushing-principles"></a>Principi di registrazione del consumo di materiali

[!include [banner](../includes/banner.md)]

I principi di registrazione del consumo di materiali riflettono le diverse strategie di consumo delle materie prime utilizzate nei processi di produzione. Il consumo è il processo che preleva materiale dalle scorte disponibili e imposta il valore del materiale consumato su **Semilavorato** (WIP) per gli ordini di produzione e gli ordini batch. Le materie prime vengono in genere consumate da un'ubicazione che è configurata per il processo che consuma il materiale. Questa ubicazione è conosciuta come l'ubicazione entrata produzione.

Prima del consumo, i materiali vengono spostati nell'ubicazione di input. Nella seguente illustrazione viene mostrato il processo.

[![scenario4a](./media/scenario4a.png)](./media/scenario4a.png)

1. Magazzino materiale
2. Prelievo materie prime
3. Ubicazione entrata produzione
4. Consumo di materie prime
5. Processo di produzione

Il consumo di materiale è controllato dai seguenti principi di registrazione del consumo di materiali:

- Manuale
- Avvio
- Fine
- Disponibile in ubicazione

I principi di registrazione del consumo di materiali sono configurati in una gerarchia di valori predefiniti. La gerarchia inizia con il prodotto rilasciato, dove il valore del principio di registrazione del consumo di materiali è **Inizio**. Nella distinta base (DBA) o nella riga della formula è possibile ignorare il principio di registrazione del consumo di materiali dal prodotto. Il principio di registrazione del consumo di materiali predefinito nelle righe della DBA di produzione o nelle righe della formula dell'ordine batch viene ricavato dal prodotto o dal valore ignorato nella DBA o nelle formule.

## <a name="description-of-the-flushing-principles"></a>Descrizione dei principi di registrazione del consumo di materiali

### <a name="manual"></a>Manuale
Il principio di registrazione del consumo di materiali manuale indica che la registrazione del consumo di materiali è un'operazione manuale. Questo principio è viene applicato se, ad esempio, si desidera poter tenere traccia del tempo e conteggiare la quantità di numeri batch consumati o di numeri di serie, ai fini della tracciabilità. Il consumo manuale viene registrato in un giornale di registrazione distinte di prelievo produzione. Per gli articoli abilitati per i processi di magazzino avanzati, è possibile applicare un flusso gestibile manualmente.

### <a name="start"></a>Avvio
Il principio di registrazione del consumo di materiali Inizio indica che il materiale verrà consumato automaticamente quando viene avviato l'ordine di produzione. La quantità di materiale che viene consumato è proporzionale alla quantità iniziata. Quando il principio di registrazione del consumo di materiali Inizio viene utilizzato insieme al sistema di esecuzione produzione, può essere utilizzato anche per registrare i materiali quando viene avviata un'operazione o un processo di lavorazione. Questo principio è importante se, ad esempio, lo scostamento nel consumo è ridotto, i materiali sono di scarso valore, non vi sono requisiti di tracciabilità, oppure le operazioni devono essere svolte in poco tempo. 

### <a name="finish"></a>Fine
Il principio di registrazione del consumo di materiali Fine indica che il materiale verrà consumato automaticamente quando l'ordine di produzione verrà dichiarato finito oppure quando un'operazione impostata per il consumo di materiali verrà registrata come completata. La quantità di materiale che viene consumata è proporzionale alla quantità che viene segnalata come finita. Quando il principio di registrazione del consumo di materiali Fine viene utilizzato insieme al sistema di esecuzione produzione, può essere utilizzato anche per registrare i materiali quando viene completata un'operazione o un processo di lavorazione. Questo principio è rilevante nelle stesse situazioni del principio di inizio. Il principio di fine tuttavia viene utilizzato per operazioni con un tempo di esecuzione più lungo, dove i materiali non devono essere impostati su WIP prima che l'operazione sia stata completata. 

### <a name="available-at-location"></a>Disponibile in ubicazione
Il principio di registrazione del consumo di materiali Disponibile in ubicazione indica che il materiale verrà consumato automaticamente quando verrà registrato come prelevato per la produzione. Il materiale viene registrato come prelevato dall'ubicazione quando il lavoro per il prelievo di materie prime è completato oppure quando il materiale è disponibile nell'ubicazione entrata produzione e la riga materiali viene rilasciata al magazzino. La distinta di prelievo che viene generata durante il processo viene registrata in un processo batch. Questo principio è rilevante se, ad esempio, sono presenti molti attività di prelievo rispetto a un ordine di produzione. In questo caso, non è necessario aggiornare manualmente la distinta di prelievo ed è possibile ottenere una visualizzazione corrente del saldo WIP.
