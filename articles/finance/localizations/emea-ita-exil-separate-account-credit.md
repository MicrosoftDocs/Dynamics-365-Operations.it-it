---
title: Conti separati per note di credito
description: Questo argomento spiega come impostare e utilizzare account separati per le note di credito.
author: ilkond
ms.date: 09/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 02e467e82ba7c85deeea6811fefb6493f45b05b1
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894738"
---
# <a name="separate-accounts-for-credit-notes"></a>Conti separati per note di credito

[!include [banner](../includes/banner.md)]

In Italia, una società può definire i criteri contabili in modo che gli importi delle note di credito vengano registrati nei conti CoGe che differiscono dai conti ricavi. Questo approccio viene utilizzato per tenere traccia dell'importo emesso sulle note di credito.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Conti separati per note di credito**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-posting-accounts"></a>Impostare i conti di registrazione

È possibile definire conti CoGe specifici da utilizzare per gli ordini cliente. Per completare la configurazione, sulla pagina **Registrazione**, selezionare l'opzione **Nota di credito**, quindi specificare i conti CoGe.

Puoi anche usare la pagine **Registrazione** per impostare account diversi per varie combinazioni di clienti, articoli e gruppi correlati.

![Configurazione della registrazione dei conti](media/emea-ita-exil-separate-account-credit-pic1.jpg)

## <a name="post-credit-notes"></a>Registrazione delle note di credito

### <a name="post-a-new-credit-note"></a>Registrare una nuova nota di credito.

Quando si registra una nuova nota di credito, viene utilizzato il conto CoGe anziché il conto ricavi standard definito nell'ordine cliente.

Se non viene definito un conto CoGe separato per la nota di credito o se non viene trovata una combinazione richiesta di cliente e articolo, per la registrazione viene utilizzato un conto ricavi ordine cliente standard.

### <a name="post-a-credit-note-that-was-created-from-a-sales-order"></a>Registrare una nota di credito creata da un ordine cliente

Se si crea una nota di credito basata su un ordine cliente esistente, deselezionare il campo **Conto principale** per ogni riga della nota di credito. Nel campo potrebbe essere stato inserito automaticamente un conto ricavi dall'ordine cliente.

![Compensazione del conto principale](media/emea-ita-exil-separate-account-credit-pic2.jpg)

> [!NOTE]
> Conti separati sono applicabili solo alle note di credito basate su ordini cliente. Non sono applicabili alle note di credito a testo libero, poiché le note di credito a testo libero richiedono l'inserimento esplicito di un conto CoGe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]