---
title: Configurare la visualizzazione dei batch meno recenti di un magazzino su un dispositivo mobile
description: In questo argomento viene descritto come configurare un dispositivo mobile per visualizzare un elenco di ubicazioni con batch meno recenti rispetto a quelli dell'ubicazione corrente di una riga di lavoro.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d23a259f4c16026ee36f73b427f7d2e610a4b8d938c2e21ec9715d8d2b8137b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727776"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>Configurare la visualizzazione dei batch meno recenti di un magazzino su un dispositivo mobile

[!include [banner](../includes/banner.md)]

La configurazione **Visualizza batch meno recenti di un magazzino** consente di visualizzare un elenco di ubicazioni con batch meno recenti rispetto a quelli dell'ubicazione corrente della riga di lavoro. L'elenco delle ubicazioni visualizzate include informazioni sui batch meno recenti nell'ubicazione con la data di scadenza e l'inventario fisico di ogni batch. È possibile scegliere di prelevare da una nuova ubicazione o di continuare a prelevare dall'ubicazione corrente. 
- Preleva da una nuova ubicazione - Se si seleziona il prelievo da una nuova ubicazione, la riga di lavoro corrente verrà aggiornata per utilizzare la nuova ubicazione e il lavoro continuerà normalmente con la nuova ubicazione. Affinché la nuova ubicazione sia valida, deve avere una quantità disponibile sufficiente per l'intera riga di lavoro. Se la quantità richiesta non è disponibile, la riga di lavoro non verrà aggiornata e verrà visualizzato l'elenco. 
- Continua a prelevare dalla posizione corrente - Se si continua con l'ubicazione della riga di lavoro corrente, le quantità per la riga di lavoro continueranno a essere prelevate dall'ubicazione originale.

## <a name="where-it-applies"></a>Dove si applica
La visualizzazione dei batch meno recenti è configurata nelle voci di menu del dispositivo mobile e ha impatto sul prelievo di batch degli articoli seguenti.

## <a name="set-up-display-older-batches-within-warehouse"></a>Configurare la visualizzazione di batch meno recenti nel magazzino
La configurazione **Visualizza batch meno recenti all'interno del magazzino** è disponibile per le voci di menu del dispositivo mobile se l'opzione **Preleva batch meno recente** è impostata su **Avvisa**.

- In **Gestione magazzino** > **Impostazioni** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile** impostare **Utilizza lavoro esistente** su **Sì** per la voce di menu e selezionare **Avvisa** nel campo **Preleva batch meno recente**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]