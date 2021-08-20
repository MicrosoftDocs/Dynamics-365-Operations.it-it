---
title: Sequenza numerica unificata per gli ID processo
description: Questa funzione fornisce un'unica sequenza numerica unificata che genera ID processo per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748717"
---
# <a name="unified-number-sequence-for-job-ids"></a>Sequenza numerica unificata per gli ID processo

[!include [banner](../includes/banner.md)]

Questa funzione fornisce un'unica sequenza numerica unificata che genera ID processo per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze. In precedenza, era possibile scegliere una sequenza numerica diversa per ciascuno di questi moduli, il che poteva generare ID processo in conflitto se due o più di queste sequenze utilizzavano un formato identico. Un tale conflitto può causare il danneggiamento dei dati.

## <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Se il sistema in uso non include già la funzione descritta in questo argomento, vedi [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva la funzionalità *Sequenza numerica unificata per ID processo*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Impostare la sequenza numerica per gli ID processo

Dopo aver abilitato questa funzione, le impostazioni della sequenza numerica **identificazione del processo** esistenti nelle pagine dei parametri per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze saranno obsolete e verrà aggiunto il nuovo campo **ID processo unificato**. Il valore **ID processo unificato** è condiviso da tutti e tre i moduli, assicurando così che tutti i moduli facciano riferimento alla stessa sequenza numerica. Gli ID processo saranno quindi univoci in tutti e tre i moduli e non si verificherà mai un conflitto.

Per impostare la sequenza numerica per gli ID processo:

1. Attiva la funzione come descritto nella sezione precedente.
1. Identifica la sequenza numerica che desideri utilizzare per gli ID processo unificati o creane una nuova. Per ulteriori informazioni, vedere [Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Vai allla pagina **Parametri di controllo produzione**, **Parametri di esecuzione produzione**, o **Parametri di orario e presenze**. Non importa quale scegli perché quando effettui questa impostazione su una di quelle pagine, tutte le altre pagine si aggiorneranno automaticamente.
1. Apri la scheda **Sequenze numeriche** nella pagina dei parametri selezionata.
1. Assegna il **Codice di sequenza numerica** che hai identificato in precedenza alla riga **ID processo unificati** della griglia.
