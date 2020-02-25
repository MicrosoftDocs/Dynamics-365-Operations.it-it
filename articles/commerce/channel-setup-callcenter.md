---
title: Impostare un canale servizio clienti
description: In questo argomento viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002452"
---
# <a name="set-up-a-call-center-channel"></a>Impostare un canale servizio clienti


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce, un servizio clienti è un tipo di canale che può essere definito nell'applicazione. La definizione di un canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente. Una società può definire più canali servizio clienti in Commerce. 

Prima di creare un nuovo canale servizio clienti, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Creare e configurare un nuovo canale servizio clienti

Per creare e configurare un nuovo canale servizio clienti, effettuare le seguenti operazioni.

1. Nel pannello di navigazione andare a **Moduli \> Canali \> Servizi clienti \> Tutti i servizi clienti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** digitare un nome per il nuovo canale.
1. Selezionare la **persona giuridica** appropriata nell'elenco a discesa.
1. Selezionare l'ubicazione **magazzino** appropriata nell'elenco a discesa.
1. Nel campo **Cliente predefinito** fornire un cliente predefinito valido.
1. Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.
1. Fornire un codice informativo **Forzatura prezzo**. Notare che potrebbe essere necessario creare dapprima un codice informativo.
1. Fornire un codice informativo **Codice sospensione**. Notare che potrebbe essere necessario creare dapprima un codice informativo.
1. Fornire un codice informativo **Credito**. Notare che potrebbe essere necessario creare dapprima un codice informativo.
1. Selezionare **Salva**.

L'immagine seguente mostra la creazione di un nuovo canale servizio clienti.

![Nuovo canale servizio clienti](media/channel-setup-callcenter-1.png)

L'immagine seguente mostra un esempio di canale servizio clienti.

![Esempio di canale servizio clienti](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Ulteriori azioni di impostazione di canali

Ulteriori attività necessarie per l'impostazione di canali servizio clienti includono l'impostazione di metodi di pagamento e di modalità di consegna.

L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna** e **Metodi di pagamento** nella scheda **Imposta**.

![Ulteriori azioni di impostazione dei canali servizio clienti](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Impostare i metodi di pagamento

Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.
1. Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.
1. Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente illustra un esempio di metodo di pagamento in contanti.

![Esempio di metodi di pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Impostare le modalità di consegna

È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.  

Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.

1. Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.
1. Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.
1. Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale. Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.

L'immagine seguente illustra un esempio di modalità di consegna.

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Funzionalità di vendita del servizio clienti](call-center-functionality.md)

[Impostare le opzioni di elaborazione dell'ordine](set-up-order-processing-options.md)

[Cataloghi del servizio clienti](call-center-catalogs.md)

[Impostare e utilizzare gli avvisi di frode](set-up-fraud-alerts.md)

[Impostare programmi di continuità per i servizi clienti](set-up-continuity-program.md)
