---
title: Configurare i parametri del leasing (anteprima)
description: Questo articolo descrive le impostazioni di configurazione per Leasing cespite, come le informazioni sulla sicurezza e le impostazioni di contabilità.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e878fa7634cfdcc6c0db19a91e771757c545505b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895082"
---
# <a name="configure-lease-parameters"></a>Configurare i parametri del leasing

[!include [banner](../includes/banner.md)]

Diverse impostazioni di configurazione influiscono sul comportamento di Leasing cespite. Queste impostazioni includono nomi di giornali di registrazione, parametri generali e impostazioni del profilo di registrazione.

1. Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.
2. Nella scheda **Leasing**, seleziona la Scheda dettaglio **Generale**.

    Il parametro **Consenti l'override della classificazione manuale** determina se la classificazione del leasing può essere sovrascritta prima della conferma dello scadenziario pagamenti.

    Il parametro **Batch tra entità** determina se è possibile registrare su altre persone giuridiche dalla persona giuridica corrente. Se questo parametro è attivato, puoi creare registrazioni a giornale per le persone giuridiche a cui hai accesso.

3. Imposta l'opzione **Consenti l'eliminazione dei leasing confermati** su **Sì** per consentire l'eliminazione dei leasing che hanno confermato scadenziari di pagamento. I leasing non possono essere eliminati se ad essi sono associate transazioni registrate o non registrate, indipendentemente dall'impostazione di questa opzione. Non puoi ripristinare un record di leasing dopo che è stato eliminato. Se carichi record per un leasing eliminato, manualmente o tramite entità di dati, le informazioni caricate vengono trattate come nuove, non come un aggiornamento di un leasing esistente.

    Se imposti questa opzione su **Sì** e il tipo di transizione del libro è **Recupero cumulativo Opzione A o B**, il sistema imposta il campo **Tasso incrementale di prestito** sul valore del campo **Tasso incrementale di prestito durante la transizione** nella pagina **Impostazione libro**. Se questa opzione è impostata su **No**, il tasso sul leasing principale è impostato sul valore del campo **Tasso incrementale di prestito** nella pagina **Dettagli libro**, indipendentemente dal tipo di transizione del libro.

4. Imposta l'opzione **Consenti storni di ammortamento su libro chiuso** su **Sì** per consentire lo storno delle transazioni di ammortamento. Le transazioni di spesa possono essere stornate anche quando la versione del libro è chiusa.

    > [!NOTE]
    > È consigliabile mantenere questa opzione impostata su **No**. L'impostazione di questa opzione viene utilizzata come convalida e controllo per impedire l'ammortamento accidentale di una versione del libro chiuso. Mantenendo l'opzione impostata su **No**, contribuisci a mantenere accurati i calcoli del valore contabile netto e dell'ammortamento futuro.

5. Imposta l'opzione **Consenti suddivisione importo pagamento** su **sì** per consentire la suddivisione degli importi di pagamento nella scheda dettaglio **Righe scadenzario pagamenti** della pagina **Leasing**. I tipi di suddivisione pagamento sono definiti in **Impostazione** nella pagina **Tipi di importo pagamento**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
