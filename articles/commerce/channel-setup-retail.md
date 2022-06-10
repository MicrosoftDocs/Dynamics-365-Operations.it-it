---
title: Impostare un canale di vendita al dettaglio
description: In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/18/2022
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
ms.openlocfilehash: 74a4f0f61e0bbfd73d0006d3cf45863af6fef18f
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770223"
---
# <a name="set-up-a-retail-channel"></a>Impostare un canale di vendita al dettaglio

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un nuovo canale di vendita al dettaglio in Microsoft Dynamics 365 Commerce.

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

![Nuovo canale di vendita al dettaglio.](media/channel-setup-retail-1.png)

L'immagine seguente mostra un esempio di canale di vendita al dettaglio.

![Esempio di canale di vendita al dettaglio.](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Altre impostazioni

Ci sono numerose altre impostazioni facoltative che possono essere impostate nelle sezioni **Rendiconto/Chiusura** e **Varie**, in base alle esigenze del punto vendita al dettaglio.

Inoltre, vedere [Layout di schermo per il POS](pos-screen-layouts.md) per informazioni sulla configurazione del layout di schermo predefinito nella sezione **Layout schermo** e [Configurare e installare Retail hardware station](retail-hardware-station-configuration-installation.md) per informazioni sulla configurazione della sezione **Stazioni hardware**.

L'immagine seguente mostra un esempio di configurazione di un canale di vendita al dettaglio.

![Esempio di configurazione di un canale di vendita al dettaglio.](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Ulteriori operazioni di impostazione di canali

Ulteriori elementi che devono essere impostati per un canale si trovano nel Riquadro azioni sotto la sezione **Imposta**.

Ulteriori attività necessarie per l'impostazione di un canale online includono l'impostazione di metodi di pagamento, riepilogo di cassa, modalità di consegna, conto ricavi/spese, sezioni, assegnazione del gruppo di adempimento e casseforti.

L'immagine seguente mostra varie ulteriori opzioni di impostazione dei canali di vendita al dettaglio nella scheda **Imposta**.

![Impostare un canale.](media/channel-setup-retail-4.png)

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

L'immagine seguente mostra un esempio di un metodo di pagamento in contanti e la configurazione della scheda **Quantità**.

![Esempio di impostazione del metodo di pagamento per gli importi.](media/payment-methods-recount.png)

> [!NOTE]
> I valori per la scheda **Quantità** vengono memorizzati nella cache nel server di vendita al dettaglio e non avranno effetto immediatamente dopo l'esecuzione dei processi di pianificazione della distribuzione. Potrebbe essere necessario riavviare Unità di scala cloud per applicare immediatamente questi valori per il test.

### <a name="set-up-cash-declaration"></a>Impostare il riepilogo di cassa

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Riepilogo di cassa**.
1. Nel riquadro azioni, selezionare **Nuovo** e quindi creare tutte le denominazioni **Moneta** e **Banconota** applicabili.

L'immagine seguente illustra un esempio di riepilogo di cassa.

![Impostare riepiloghi di cassa.](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Imposta la modalità di consegna

È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del Riquadro azioni.  

Per modificare o aggiungere una modalità di consegna, attenersi alla seguente procedura.

1. Nel pannello di navigazione, selezionare **Moduli \> Gestione inventario \> Modalità di consegna**.
1. Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.
1. Nella sezione **Canali di vendita al dettaglio**, selezionare **Aggiungi riga** per aggiungere il canale. Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.

L'immagine seguente illustra un esempio di modalità di consegna.

![Impostare le modalità di consegna.](media/channel-setup-retail-7.png)

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

![Impostare conti ricavi/spese.](media/channel-setup-retail-8.png)

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

![Impostare assegnazioni di gruppi di adempimento.](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Impostare casseforti

Per impostare casseforti, effettuare le seguenti operazioni.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi fare clic su **Casseforti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Immettere un nome per la cassaforte.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="ensure-unique-transaction-ids"></a>Garantire ID transazione univoci

A partire dalla versione Commerce 10.0.18, gli ID transazione generati per il POS sono sequenziali e includono le seguenti parti:

- Una parte fissa, che è una concatenazione di ID punto vendita e ID terminale. 
- Una parte sequenziale, che è una sequenza numerica. 

Nello specifico, il formato è *{store}-{terminal}-{numbersequence}*. 

Poiché gli ID transazione possono essere generati in modalità offline e online, ci sono stati casi di generazione di ID transazione duplicati. L'eliminazione degli ID di transazione duplicati richiede molte correzioni manuali dei dati. 

Con Commerce versione 10.0.19, il formato dell'ID transazione è stato aggiornato per rimuovere la parte sequenziale e utilizza invece un numero di 13 cifre generato calcolando il tempo in millisecondi dal 1970. Con questa modifica, il nuovo formato dell'ID transazione è *{store}-{terminal}-{millisecondsSince1970}*. Questo aggiornamento rende l'ID transazione non sequenziale e garantisce che gli ID transazione siano sempre univoci. 

> [!NOTE]
> Gli ID transazione sono destinati esclusivamente all'uso interno del sistema, quindi non è necessario che siano sequenziali. Tuttavia, molti paesi/aree geografiche richiedono che gli ID delle ricevute siano sequenziali.

La nuova funzionalità del formato dell'ID transazione può essere abilitata dall'area di lavoro **Gestione funzionalità**. 

Per abilitare l'uso dei nuovi ID transazione, segui questi passaggi:

1. In Commerce Headquarters andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Filtra per il modulo "Retail e Commerce".
1. Cerca il nome della funzionalità **Abilita nuovo ID transazione per evitare ID transazione duplicati**.
1. Selezionare la funzionalità, quindi nel riquadro destro, selezionare **Abilita ora**.  
1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Esegui i processi **1070 Configurazione canale** e **1170 Registrazione attività POS** per sincronizzare la funzione abilitata nei punti vendita.
1. Dopo che le modifiche sono state inviate ai punti vendita, i terminali POS devono essere chiusi e riaperti per utilizzare il nuovo formato dell'ID transazione. 

> [!NOTE]
> Dopo che la nuova funzionalità di formato dell'ID transazione è stata abilitata, non sarai in grado di disabilitarla. Se deve essere disabilitata, contatta il supporto di Commerce.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Prerequisiti dell'impostazione dei canali](channels-prerequisites.md)

[Impostare un canale online](channel-setup-online.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
