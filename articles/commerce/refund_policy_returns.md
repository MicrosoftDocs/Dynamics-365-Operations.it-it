---
title: Creare e aggiornare una politica su resi e rimborsi per un canale
description: Questo argomento spiega come impostare una politica su resi e rimborsi per un canale.
author: ShalabhjainMSFT
ms.date: 07/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: ca5797cfc2d92c4cbc98d3f64d60e1fd260f0418
ms.sourcegitcommit: 08797bc43e93ea05711c5a70dd7cdb82cada667a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6558299"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Creare e aggiornare i criteri per resi e rimborsi di un canale

[!include [banner](includes/banner.md)]

La politica sui resi in Dynamics 365 Commerce consente ai rivenditori di impostare le applicazioni per le quali le offerte di pagamento possono essere consentite per l'elaborazione di un reso su un dispositivo POS.  

Questo argomento descrive i passaggi per impostare una politica su resi e rimborsi per un canale.

L'ambito della politica è attualmente limitato alla definizione delle offerte di pagamento che possono essere consentite per un canale. L'elenco "Consentite" si basa sui metodi di pagamento utilizzati per effettuare l'acquisto. Ad esempio:

- Se un acquisto è stato effettuato utilizzando una gift card, la politica del punto vendita prevede di elaborare i rimborsi solo su una nuova gift card o per fornire un buono acquisto. 
- Se una vendita viene effettuata in contanti, le opzioni consentite per il rimborso sono contanti, gift card e conto cliente, ma non la carta di credito. 

## <a name="enable-return-policy"></a>Abilitare la politica sui resi

Per abilitare la funzionalità di politica sui resi del canale in Commerce Headquarters, seguire questi passaggi.

1. Andare all'area di lavoro **Gestione funzionalità** in Dynamics 365 Commerce.
1. Cercare la funzionalità **Abilita politiche sui resi del canale** nell'elenco dei nomi di funzionalità.
1. Selezionare **Abilita ora**.
1. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1110** (Configurazione globale) per distribuire la modifica della funzionalità.

## <a name="initialize-the-commerce-scheduler"></a>Inizializzare l'utilità di pianificazione di commercio

Dopo aver abilitato la funzionalità **Abilita la politica sui resi del canale** devi inizializzare l'utilità di pianificazione di commercio per garantire che le nuove modifiche al database delle funzionalità vengano aggiunte tramite la sincronizzazione Commerce Data Exchange (CDX). 

Per inizializzare l'utilità di pianificazione di commercio in Commerce headquarters, segui questi passaggi.

- Andare a **Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Inizializza utilità di pianificazione di commercio**. In alternativa, puoi cercare "Inizializza utilità di pianificazione di commercio".
- Nella finestra di dialogo **Inizializza utilità di pianificazione di commercio**, verifica che l'opzione **Elimina configurazione esistente** sia impostata su **No** e seleziona **OK**.

## <a name="configure-return-policy"></a>Configurare la politica sui resi

Seguire questi passaggi per configurare una politica sui resi per un punto vendita al dettaglio o un canale di vendita al dettaglio online.

1. Andare a **Retail e Commerce** \> **Impostazione canale** \> **Resi** \> **Politica sui resi del canale**.

1. Selezionare **Nuovo** per creare un nuovo modello di politica sui resi. Per utilizzare un modello esistente, selezionare il modello nel riquadro sinistro. Per i nuovi modelli, aggiungere un nome e una descrizione che consentiranno di identificare la politica quando viene applicata al canale.

   ![Aggiungere nuovi criteri sui resi.](media/Return-policy-page1.png)
     
   
1. Nella sezione **Metodi di pagamento per rimborso consentiti**, definire le offerte di pagamento per resi **Consentite** specifiche a ogni metodo di pagamento.
   ![Impostare i metodi di pagamento consentiti per tipo di pagamento.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - I metodi di pagamento sono derivati da quelli impostati per l'organizzazione.
    > - L'aggiunta di un tipo di offerta di reso consentita per ogni metodo di pagamento elencato garantirà la possibilità di effettuare i resi per il tipo di offerta di reso consentito.
    
1. Associare il modello di politica sui resi ai punti vendita in cui verrà utilizzato. Selezionare **Aggiungi** nella scheda **Canali di vendita al dettaglio** e associare i canali disponibili. 

    - Nella finestra di dialogo **Scegli nodi organizzazione**, selezionare i punti vendita, le aree geografiche e le organizzazioni a cui il modello deve essere associato.
    - Un solo modello di politica sui resi può essere associato a ogni punto vendita.
    - Utilizzare i pulsanti freccia per selezionare punti vendita, aree geoagrafiche o organizzazioni.
    - La data di entrata in vigore della politica sarà la data alla quale le politiche vengono applicate ai canali e vengono eseguiti i processi del canale. 

    ![Finestra di dialogo Scegli nodi organizzazione.](media/Return-policy-page3.png)

1. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1070** per rendere la politica sui resi del canale disponibile nel POS.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Visualizzare in anteprima la politica sui resi del canale nel POS

Seguire i passaggi in uno dei seguenti esempi per visualizzare i tipi di offerte di reso consentite nel POS.

1. Accedere al POS come cassiere o responsabile.
1. Sotto **Turno e cassetto**, selezionare **Mostra giornale di registrazione**.
1. Seleziona la transazione che fa parte del reso. 
1. Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.  
    - Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.
    - Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.
    - Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.

oppure

1. Accedere al POS come cassiere o responsabile.
1. Selezionare **Transazione di reso** e immettere l'ID ricevuta utilizzando un lettore di codici a barre oppure manualmente. 
1. Seleziona la transazione che fa parte del reso. 
1. Selezionare gli articoli da rimborsare e scegliere il metodo di pagamento.  
    - Se l'offerta di pagamento selezionata è nell'elenco dei tipi di offerte di reso consentiti, il cassiere può completare la transazione.
    - Se l'offerta di pagamento selezionata non è consentita, viene visualizzato un messaggio di errore.
    - Selezionare **Importo dovuto** per visualizzare un elenco di tutti i tipi di offerte di reso consentiti.

![Tipo di rimborso non consentito.](media/Return-policy-page6.png)



![Tipo di rimborso consentito.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
