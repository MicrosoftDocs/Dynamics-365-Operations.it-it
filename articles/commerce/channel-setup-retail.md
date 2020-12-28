---
title: Impostare un canale di vendita al dettaglio
description: In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a9291dddf7d4dc080b6eb1ec60702de32a761f45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413418"
---
# <a name="set-up-a-retail-channel"></a>Impostare un canale di vendita al dettaglio


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio. Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici. Ogni canale di vendita al dettaglio può disporre di propri metodi di pagamento, gruppi di prezzi, POS, conti ricavi/spese e personale. È necessario impostare tutti questi elementi prima di creare un canale di vendita al dettaglio. 

Prima di creare un canale di vendita al dettaglio, assicurarsi di soddisfare i [prerequisiti per i canali](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Creare e configurare un nuovo canale di vendita al dettaglio

1. Nel pannello di navigazione, andare a **Moduli \> Canali \> Punti vendita \> Tutti i punti vendita**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** digitare un nome per il nuovo canale.
1. Nel campo **Numero punto vendita** immettere un numero di punto vendita univoco. Il numero può essere alfanumerico con un massimo di 10 caratteri.
1. Nell'elenco a discesa **Persona giuridica**, immettere la persona giuridica appropriata.
1. Nell'elenco a discesa **Magazzino**, immettere il magazzino appropriato.
1. Nel campo **Fuso orario punto vendita** selezionare il fuso orario appropriato.
1. Nell'elenco a discesa **Fascia IVA**, selezionare una fascia IVA appropriata per il punto vendita.
1. Nel campo **Valuta**, selezionare la valuta appropriata.
1. Nel campo **Rubrica clienti**, fornire una rubrica valida.
1. Nel campo **Cliente predefinito** fornire un cliente predefinito valido.
1. Nel campo **Profilo funzionalità**, selezionare un profilo di funzionalità, se applicabile.
1. Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra la creazione di un nuovo canale di vendita al dettaglio.

![Nuovo canale di vendita al dettaglio](media/channel-setup-retail-1.png)

L'immagine seguente mostra un esempio di canale di vendita al dettaglio.

![Esempio di canale di vendita al dettaglio](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Altre impostazioni

Ci sono numerose altre impostazioni facoltative che possono essere impostate nelle sezioni **Rendiconto/Chiusura** e **Varie**, in base alle esigenze del punto vendita al dettaglio.

Inoltre, vedere [Layout di schermo per il POS](pos-screen-layouts.md) per informazioni sulla configurazione del layout di schermo predefinito nella sezione **Layout schermo** e [Configurare e installare Retail hardware station](retail-hardware-station-configuration-installation.md) per informazioni sulla configurazione della sezione **Stazioni hardware**.

L'immagine seguente mostra un esempio di configurazione di un canale di vendita al dettaglio.

![Esempio di configurazione di un canale di vendita al dettaglio](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Ulteriori operazioni di impostazione di canali

Ulteriori elementi che devono essere impostati per un canale si trovano nel **Riquadro azioni** sotto la sezione **Imposta**.

Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, riepilogo di cassa, modalità di consegna, conto ricavi/spese, sezioni, assegnazione del gruppo di adempimento e casseforti.

L'immagine seguente mostra varie ulteriori opzioni di impostazione dei canali di vendita al dettaglio nella scheda **Imposta**.

![Impostare un canale](media/channel-setup-retail-4.png)

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

### <a name="set-up-cash-declaration"></a>Impostare il riepilogo di cassa

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Riepilogo di cassa**.
1. Nel riquadro azioni, selezionare **Nuovo** e quindi creare tutte le denominazioni **Moneta** e **Banconota** applicabili.

L'immagine seguente illustra un esempio di riepilogo di cassa.

![Impostare riepiloghi di cassa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Impostare le modalità di consegna

È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.  

Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.

1. Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.
1. Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.
1. Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale. Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.

L'immagine seguente illustra un esempio di modalità di consegna.

![Impostare le modalità di consegna](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Impostare un conto ricavi/spese

Per impostare un conto ricavi/spese, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Conto ricavi/spese**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Sotto **Nome**, immettere un nome.
1. Sotto **Nome di ricerca** immettere un nome di ricerca.
1. Sotto **Tipo di conto**, immettere un tipo di conto.
1. Immettere il testo per **Riga messaggio 1**, **Riga messaggio 2**, **Testo distinta 1** e **Testo distinta 2** come necessario.
1. Sotto **Registrazione**, immettere le informazioni di registrazione.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di conto ricavi/spese.

![Impostare conti ricavi/spese](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Impostare sezioni

Per impostare sezioni, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi fare clic su **Sezioni**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Sotto **Numero sezione**, immettere un numero di sezione.
1. Sotto **Descrizione** immettere una descrizione.
1. Sotto **Dimensioni sezione**, immettere le dimensioni della sezione.
1. Configurare impostazioni aggiuntive per **Generale** e **Statistiche vendite** come necessario.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-a-fulfillment-group-assignment"></a>Impostare l'assegnazione di un gruppo di adempimento

Per impostare l'assegnazione di un gruppo di adempimento, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'elenco a discesa **Gruppo di adempimento**, selezionare un gruppo di adempimento.
1. Nel campo **Descrizione**, immettere una descrizione.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di impostazione dell'assegnazione di un gruppo di adempimento.

![Impostare l'assegnazione di un gruppo di adempimento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Impostare casseforti

Per impostare casseforti, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi fare clic su **Casseforti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Immettere un nome per la cassaforte.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Impostare un canale online](channel-setup-online.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)

