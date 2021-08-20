---
title: Risolvere i problemi di rifornimento del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il rifornimento dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 251dc174d52d754a0c488d5becf63f1a43f9bd30034036d10086c9803060b5a0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758402"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Risolvere i problemi di rifornimento del magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il rifornimento dei magazzini in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>Viene visualizzato il messaggio di errore seguente"Il lavoro %1 non può essere sbloccato perché ha un lavoro di rifornimento incompiuto".

### <a name="issue-description"></a>Descrizione del problema

Il lavoro di prelievo è bloccato a causa del lavoro di rifornimento dipendente.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Quando si utilizza il rifornimento della domanda ciclo, se un'ubicazione di prelievo deve essere rifornita per soddisfare la domanda dell'ordine di origine, il sistema crea sia il lavoro di rifornimento che il lavoro di prelievo. Tuttavia, blocca il lavoro di prelievo fino al completamento del lavoro di rifornimento. Questo comportamento è intenzionale, perché l'ubicazione di prelievo non avrà scorte sufficienti a meno che il lavoro di rifornimento non sia completato. Completare il lavoro di rifornimento e quindi elaborare il lavoro di prelievo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]