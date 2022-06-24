---
title: Impostare un canale del servizio clienti
description: In questo articolo viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 03/13/2020
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
ms.openlocfilehash: 219c84eb9a8c3b53467ed48c13775106c82dac63
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864957"
---
# <a name="set-up-a-call-center-channel"></a>Impostare un canale del servizio clienti


[!include [banner](includes/banner.md)]

In questo articolo viene descritto come creare un nuovo canale servizio clienti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica


In Dynamics 365 Commerce, un servizio clienti è un tipo di canale di Commerce che può essere definito nell'applicazione. La definizione di un canale per le entità del servizio clienti consente al sistema di associare specifici valori predefiniti di dati e di elaborazione di ordini a ordini cliente. Mentre un'azienda può definire più canali di call center in Commerce, è importante notare che un singolo utente può essere collegato a un solo canale di servizio clienti. 

Prima di creare un nuovo canale servizio clienti, assicurarsi di aver completato i [prerequisiti di impostazione dei canali](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Creare e configurare un nuovo canale servizio clienti

Per creare e configurare un nuovo canale servizio clienti, effettuare le seguenti operazioni.

1. Nel riquadro di spostamento, passare a **Retail e Commerce \> Canali \> Servizi clienti \> Tutti i servizi clienti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Nome** digitare un nome per il nuovo canale.
1. Selezionare la **persona giuridica** appropriata nell'elenco a discesa.
1. Selezionare l'ubicazione **magazzino** appropriata nell'elenco a discesa. Questa posizione verrà utilizzata come impostazione predefinita per gli ordini cliente creati per questo canale di servizio clienti, a meno che non siano state definite altre impostazioni predefinite a livello di cliente o articolo.
1. Nel campo **Cliente predefinito** fornire un cliente predefinito valido. Questi dati vengono utilizzati per facilitare il popolamento automatico delle impostazioni predefinite quando vengono creati nuovi record cliente. Quando si creano ordini di servizio clienti, non è consigliabile creare ordini per il cliente predefinito.
1. Nel campo **Profilo di notifica tramite posta elettronica**, fornire un profilo di notifica valido. Man mano che gli ordini del servizio clienti vengono creati ed elaborati, il profilo di notifica e-mail viene utilizzato per attivare avvisi e-mail automatici ai clienti con informazioni sullo stato dell'ordine.
1. Fornire un codice informativo **Forzatura prezzo**. Potrebbe essere necessario creare dapprima un codice informativo. Questo codice informativo fornisce il set di codici motivo che l'utente dovrà scegliere quando utilizza la funzionalità di sostituzione del prezzo in un ordine di servizio clienti.
1. Fornire un codice informativo **Codice sospensione**. Potrebbe essere necessario creare dapprima un codice informativo. Questo codice informativo fornisce il set di codici motivo facoltativi che l'utente dovrà scegliere quando utilizza mette in attesa un ordine.
1. Fornire un codice informativo **Credito**. Potrebbe essere necessario creare dapprima un codice informativo. Questo codice informativo fornisce il set di codici motivo che l'utente può scegliere quando utilizza la funzionalità di credito dell'ordine del servizio clienti per fornire rimborsi al cliente per motivi di servizio clienti.
1. Facoltativo: impostare le dimensioni finanziarie nella scheda dettaglio **Dimensioni finanziarie**. Le dimensioni immesse verranno utilizzate come predefinite in qualsiasi ordine cliente creato in questo canale di servizio clienti.
1. Fare clic su **Salva**.

L'immagine seguente mostra la creazione di un nuovo canale servizio clienti.

![Nuovo canale servizio clienti.](media/channel-setup-callcenter-1.png)

L'immagine seguente mostra un esempio di canale servizio clienti.

![Esempio di canale servizio clienti.](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Ulteriori azioni di impostazione di canali

Ulteriori attività necessarie per l'impostazione di canali servizio clienti includono l'impostazione di metodi di pagamento e di modalità di consegna.

L'immagine seguente mostra le opzioni di impostazione **Modalità di consegna** e **Metodi di pagamento** nella scheda **Imposta**.

![Ulteriori azioni di impostazione dei canali servizio clienti.](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Impostare i metodi di pagamento

Per impostare i metodi di pagamento per ogni tipo di pagamento supportato per un canale, procedere come segue. Gli utenti dovranno scegliere tra i metodi di pagamento predefiniti per collegarli al canale del servizio clienti. Prima di impostare i metodi di pagamento del servizio clienti, impostare innanzitutto i metodi di pagamento principali **Retail e Commerce \> Impostazione del canale \> Modalità di pagamento \> Modalità di pagamento**.

1. Nel riquadro azioni, selezionare la scheda **Imposta**, quindi selezionare **Metodi di pagamento**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel riquadro di spostamento, selezionare un metodo di pagamento tra i pagamenti predefiniti disponibili.
1. Configurare eventuali impostazioni aggiuntive come necessario per il tipo di pagamento. Per le carte di credito, gift card o carte fedeltà, è necessaria un'impostazione aggiuntiva selezionando la funzione **Impostazione carta**. 
1. Configurare gli account di registrazione corretti per il tipo di pagamento nella sezione **Registrazione**.
1. Nel riquadro azioni fare clic su **Salva**.

L'immagine seguente illustra un esempio di metodo di pagamento in contanti.

![Esempio di metodi di pagamento.](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Imposta la modalità di consegna

È possibile visualizzare le modalità di consegna configurate selezionando **Modalità di consegna** nella scheda **Imposta** del **Riquadro azioni**.  

Per modificare o aggiungere una modalità di consegna da associare al canale del servizio clienti, attenersi alla seguente procedura.

1. Dal modulo delle modalità di consegna del servizio clienti, selezionare **Gestire le modalità di consegna**
1. Nel riquadro azioni, selezionare **Nuovo** per creare una nuova modalità di consegna o selezionarne una esistente.
1. Nella sezione **Canali di vendita al dettaglio**, fare clic su **Aggiungi riga** per aggiungere il canale del servizio clienti. Aggiungere canali utilizzando nodi dell'organizzazione anziché aggiungere ogni canale singolarmente può semplificare questa operazione.
1. Assicurarsi che la modalità di consegna sia stata configurata con i dati nella scheda dettaglio **Prodotti** e nella scheda dettaglio **Indirizzi**. Se nessun prodotto o indirizzo di consegna è valido per la modalità di consegna, la scelta durante l'inserimento dell'ordine comporterà errori.
1. Dopo che sono state apportate le modifiche alla modalità di configurazione della consegna del servizio clienti, il processo **Elabora modalità di consegna** deve essere eseguito per esplodere la matrice della modifica. Questo processo è disponibile accedendo a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Elabora modalità di consegna**.

L'immagine seguente illustra un esempio di modalità di consegna.

![Impostare le modalità di consegna.](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Impostare gli utenti del canale

Per creare un ordine cliente collegato al canale del servizio clienti da Commerce Headquarters, l'utente che crea l'ordine cliente deve essere collegato al canale del servizio clienti. L'utente non può collegare manualmente un ordine cliente creato in Commerce Headquarters al canale del servizio clienti. Il collegamento è sistematico e si basa sull'utente e sulla relazione dell'utente con il canale del servizio clienti. Un utente può essere collegato a un solo canale del servizio clienti.

1. Nel riquadro azioni, selezionare la scheda **Canale**, quindi selezionare **Utenti canale**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Scegliere un **ID utente** esistente dall'elenco di selezione a discesa per collegare questo utente al canale del servizio clienti

Dopo aver impostato l'utente del canale dopo che l'utente ha creato un nuovo ordine cliente in Commerce Headquarters, l'ordine cliente viene collegato al canale del servizio clienti associato. Eventuali configurazioni per questo canale verranno applicate sistematicamente all'ordine cliente. Un utente può confermare a quale canale del servizio clienti è collegato l'ordine cliente visualizzando il riferimento al nome del canale nell'intestazione dell'ordine cliente.


### <a name="set-up-price-groups"></a>Impostare gruppi di prezzi

I gruppi di prezzi sono facoltativi, ma se utilizzati possono controllare quali prezzi di vendita verranno offerti ai clienti che effettuano ordini nel canale del servizio clienti. Se un gruppo di prezzi non è stato configurato per il cliente o se i gruppi di prezzi del catalogo non vengono applicati all'ordine cliente (utilizzando il campo **ID codice sorgente** nell'intestazione dell'ordine del servizio clienti), il gruppo di prezzi del canale viene utilizzato per individuare i prezzi degli articoli. Se un gruppo di prezzi non viene trovato nel canale del servizio clienti, vengono utilizzati i prezzi principali dell'articolo predefiniti. 

Per impostare un gruppo di prezzi, procedere come segue.

1. Nel riquadro azioni, fare clic sulla scheda **Canale**, quindi selezionare **Gruppi di prezzi**.
1. Fare clic su **Nuovo** nel riquadro azioni.
1. Selezionare un **Gruppo di prezzi di vendita al dettaglio** dall'elenco di selezione a discesa.

## <a name="additional-resources"></a>Risorse aggiuntive

[Prerequisiti dell'impostazione dei canali](channels-prerequisites.md)

[Funzionalità di vendita del servizio clienti](call-center-functionality.md)

[Impostare le opzioni di elaborazione dell'ordine](set-up-order-processing-options.md)

[Cataloghi del servizio clienti](call-center-catalogs.md)

[Impostare e utilizzare gli avvisi di frode](set-up-fraud-alerts.md)

[Impostare programmi di continuità per i servizi clienti](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]