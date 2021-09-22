---
title: L'impostazione Registra nel conto di addebito nella contabilità generale non è attivata
description: Questo problema si verifica quando viene fatturato un ordine fornitore, se l'opzione "Registra nel conto di addebito nella contabilità generale" è abilitata nella scheda "Fattura" della pagina "Parametri contabilità fornitori".
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476788"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>L'impostazione Registra nel conto di addebito nella contabilità generale non è attivata

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando viene fatturato un ordine fornitore, se l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**.

## <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
1. Nella scheda **Fattura**, imposta l'opzione **Registra nel conto di addebito nella contabilità generale** su *Sì*.
1. Vai a **Gestione scorte \> Impostazione \> Registrazione \> Registrazione**.
1. Nella scheda **Ordine fornitore**, assicurati di aver eliminato tutte le righe nella spesa di acquisto del prodotto.
1. Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Creare un ordine fornitore. Nel campo **Conto fornitore**, seleziona *1001 Acme Office Supplies*.
1. Aggiungi una riga ordine fornitore con le seguenti impostazioni:

    - **Numero articolo:** *D0011 Laser Projector*
    - **Sito:** *1*
    - **Magazzino:** *11*
    - **Quantità:** *4*

1. Nel riquadro azioni, nella scheda **Acquisto**, nel gruppo **Azione**, seleziona **Conferma**.
1. Nel riquadro azioni, nella scheda **Ricevi**, nel gruppo **Genera**, seleziona **Entrata prodotto**.
1. Nella finestra di dialogo **Registrazione entrata prodotti**, nel campo **Entrata prodotti**, immetti un numero arbitrario, quindi seleziona **OK**.
1. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
1. Nel campo **Numero**, immetti un numero arbitrario come numero di fattura.
1. Aggiorna lo stato di abbinamento e registra.
1. Si noti che ora viene visualizzato il seguente errore quando si genera una fattura da un ordine fornitore: "Numero di conto per il tipo di transazione spesa di acquisto per il prodotto inesistente".

## <a name="resolution"></a>Risoluzione

Ciò dipende dalle impostazioni dei parametri per le fatture e i gruppi di fatture. Per ulteriori informazioni, vedi il seguente post del blog: [Contabilizzazione per spese di acquisto e variazione delle scorte](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
