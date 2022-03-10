---
title: Impostare un canale online
description: In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f32872fcc27e2e74300c4f18dfa08d666e4ad8a8
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092114"
---
# <a name="set-up-an-online-channel"></a>Impostare un canale online

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un nuovo canale in Microsoft Dynamics 365 Commerce.

In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio. Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici. I punti vendita online offrono ai clienti la possibilità di acquistare prodotti presso il punto vendita online del fornitore oltre che nei punti vendita al dettaglio.

Per creare un negozio online in Commerce, devi prima creare un canale online. Prima di creare un nuovo canale online, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).

Prima di poter creare un nuovo sito, almeno un punto vendita online deve essere creato in Commerce. Per ulteriori informazioni, vedi [Creare un sito di e-commerce](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Creare e configurare un nuovo canale online

Per creare e configurare un nuovo canale online, effettuare le seguenti operazioni.

1. Nel pannello di navigazione, andare a **Moduli \> Canali \> Punti vendita online**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** digitare un nome per il nuovo canale.
1. In **Persona giuridica**, immettere la persona giuridica appropriata.
1. In **Magazzino**, immettere il magazzino appropriato.
1. Nel campo **Fuso orario punto vendita** selezionare il fuso orario appropriato.
1. Nel campo **Valuta**, selezionare la valuta appropriata.
1. Nel campo **Cliente predefinito** fornire un cliente predefinito valido.
1. Nel campo **Rubrica clienti**, fornire una rubrica valida.
1. Nel campo **Profilo funzionalità**, selezionare un profilo di funzionalità, se applicabile.
1. Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra la creazione di un nuovo canale online.

![Nuovo canale online.](media/channel-setup-online-1.png)

L'immagine seguente mostra un esempio di canale online.

![Esempio di canale online.](media/channel-setup-online-2.png)

## <a name="assign-the-channel-to-a-commerce-scale-unit"></a>Assegnare il canale a Commerce Scale Unit

Il tuo nuovo canale deve essere assegnato a Commerce Scale Unit. Per istruzioni, vedi [Configurare i canali per utilizzare Commerce Scale Unit](../fin-ops-core/dev-itpro/deployment/initialize-retail-channels.md#configure-channels-to-use-commerce-scale-unit).

## <a name="set-up-languages"></a>Impostare le lingue

Se il sito di e-commerce supporterà più lingue, espandere la sezione **Lingue** e aggiungere altre lingue come necessario.

## <a name="set-up-payment-account"></a>Impostare un conto pagamenti

Nella sezione **Conto pagamenti**, è possibile aggiungere un fornitore di servizi di pagamento di terze parti. Per informazioni sull'impostazione del connettore di pagamento Adyen, vedere [Connettore pagamenti di Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Ulteriori azioni di impostazione di canali

Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, modalità di consegna e assegnazione del gruppo di adempimento.

L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna**, **Metodi di pagamento** e **Assegnazione gruppo di adempimento** nella scheda **Imposta**.

![Ulteriori azioni di impostazione del canale online.](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>Impostare i metodi di pagamento

Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel pannello di navigazione, selezionare un metodo di pagamento desiderato.
1. Nella sezione **Generale**, immettere un nome in **Nome operazione** e configurare qualsiasi altra impostazione desiderata.
1. Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente illustra un esempio di metodo di pagamento in contanti.

![Esempio di metodi di pagamento.](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Imposta la modalità di consegna

È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.  

Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.

1. Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.
1. Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.
1. Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale. Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.

L'immagine seguente illustra un esempio di modalità di consegna.

![Impostare le modalità di consegna.](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Impostare l'assegnazione di un gruppo di adempimento

Per impostare l'assegnazione di un gruppo di adempimento, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'elenco a discesa **Gruppo di adempimento**, selezionare un gruppo di adempimento.
1. Nel campo **Descrizione**, immettere una descrizione.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di impostazione dell'assegnazione di un gruppo di adempimento.

![Impostare l'assegnazione di un gruppo di adempimento.](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Prerequisiti dell'impostazione dei canali](channels-prerequisites.md)

[Impostare un canale di vendita al dettaglio](channel-setup-retail.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)

[Connettore pagamenti di Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
