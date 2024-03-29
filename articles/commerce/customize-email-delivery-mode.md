---
title: Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna
description: In questo articolo viene descritto come impostare modelli di posta elettronica personalizzati per i tipi di notifica e le modalità di consegna specifici in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 0c0bd218c10a373d142ddcc7780c5339569f7a07
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275706"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come impostare modelli di posta elettronica personalizzati per i tipi di notifica e le modalità di consegna specifici in Microsoft Dynamics 365 Commerce.

I messaggi di posta elettronica transazionali ora possono essere personalizzati per la combinazione di un tipo di notifica (ad esempio, **Ordine creato**, **Ordine imballato**, o **Ordine fatturato**) e una modalità di consegna (ad esempio, durante la notte, ritiro in negozio o ritiro piano strada). I messaggi di posta elettronica transazionali personalizzati consentono ai rivenditori di fornire ai propri clienti esperienze di evasione degli ordini personalizzate in base alla modalità di consegna dell'ordine. Ad esempio, l'evento "ordine imballato" può essere personalizzato in modo da fornire istruzioni per il ritiro dal piano strada per i clienti che scelgono questo ritiro. In alternativa, può fornire informazioni sul corriere e sulla consegna per i clienti che scelgono di spedire l'ordine.

> [!NOTE]
> Per utilizzare la funzionalità per i messaggi di posta elettronica transazionali personalizzati è necessario prima attivare la funzionalità **Personalizza i modelli di messaggi di posta elettronica transazionali in base alla modalità di consegna** andando in **Aree di lavoro \> Gestione funzionalità** in Commerce headquarters.

I messaggi di posta elettronica possono essere personalizzati in base alla modalità di consegna per i seguenti tipi di notifica:

- **Annullamento ordine** - Questo tipo di notifica tramite posta elettronica è nuovo.
- **Ordine creato**
- **Ordine confermato**
- **Ordine fatturato** - Questo tipo di notifica tramite posta elettronica è nuovo. Può essere utilizzato al posto del tipo di notifica **Ordine spedito** che invierà una notifica per qualsiasi evento di fatturazione che abbia una modalità di consegna spedita (non una modalità di consegna ritiro, trasporto o elettronica).
- **Ordine ritirato**
- **Ordine imballato**
- **Ordine pronto per il ritiro** - Questo tipo di notifica può essere personalizzato in base alla modalità di consegna solo se la funzionalità **Supporto per più modalità di consegna ritiro** è attivata. In tal caso, questo tipo di notifica è funzionalmente equivalente al tipo di notifica **Ordine imballato**.
- **Pagamento non riuscito**
- **Ordine sostitutivo creato**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Configurare modelli di posta elettronica per modalità di consegna specifiche

Per questa procedura, si presume che siano stati già creati i nuovi modelli di messaggi di posta elettronica personalizzati e siano stati aggiunti alla pagina **Modelli di posta elettronica dell'organizzazione**. Per informazioni su come creare e caricare modelli di posta elettronica, vedere [Creare modelli di posta elettronica per eventi transazionali](email-templates-transactions.md).

Per configurare i modelli di posta elettronica per modalità di consegna specifiche in Commerce headquarters, seguire questi passaggi.

1. Andare a **Profilo di notifica tramite posta elettronica per Commerce**.
1. Sotto **Impostazioni notifica di eventi di vendita al dettaglio**, selezionare un tipo di notifica esistente.
1. Mentre il tipo di notifica è ancora selezionato, selezionare **Configurare le modalità di consegna**.
1. Nella finestra di dialogo **Modalità di consegna**, selezionare **Nuovo**.
1. Nella nuova riga, nel campo **Modalità di consegna**, selezionare una modalità di consegna.
1. Nel campo **ID posta elettronica** selezionare il modello di messaggio di posta elettronica da mappare alla modalità di consegna.
1. Selezionare la casella di controllo **Attiva**.
1. Ripetere i passaggi da 4 a 7 per aggiungere altre modalità di consegna.
1. Al termine, selezionare **OK**.

> [!NOTE]
> - Quando è presente più di una modalità di consegna tra le righe di un ordine cliente, verrà utilizzato il modello predefinito. Il modello predefinito è il modello mappato al tipo di notifica nella pagina **Profilo di notifica tramite posta elettronica per Commerce**.
> - Se un ordine cliente ha una modalità di consegna che non è stata configurata per un modello di posta elettronica personalizzato, verrà utilizzato il modello di posta elettronica predefinito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare ordini servizio clienti](tasks/create-call-center-orders.md)

[Modifica modalità di consegna nel POS](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
