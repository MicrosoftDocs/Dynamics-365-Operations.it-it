---
title: Impostare le sequenze numeriche per i rendiconti di vendita al dettaglio
description: In questo articolo viene descritto come configurare le sequenze numeriche necessarie per i rendiconti di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 5c4eb872ec2151a9f4ac5462ad43dd03a6705487
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880005"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Impostare le sequenze numeriche per i rendiconti di vendita al dettaglio

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo articolo viene descritto come configurare le sequenze numeriche necessarie per i rendiconti di vendita al dettaglio in Microsoft Dynamics 365 Commerce.

Due tipi di rendiconti di vendita al dettaglio vengono utilizzati in Dynamics 365 Commerce: 

- **Rendiconti transazionali** sono destinati ad essere creati e pubblicati ad alta frequenza. Sono utilizzati per registrare tutte le transazioni non finanziarie nel negozio in Dynamics 365 Commerce headquarters. 
- **Rendiconti finanziari** sono destinati ad essere creati e pubblicati una volta per giorno lavorativo. Includono solo i turni chiusi dai negozi al dettaglio che sono stati caricati in Commerce headquarters il processo P.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Configurare una sequenza numerica per la registrazione rendiconto

Dopo aver completato la configurazione di un negozio al dettaglio, in Commerce headquarters, è necessario configurare una sequenza numerica univoca che verrà utilizzata per i rendiconto durante il processo di creazione del rendiconto.

Per configurare una sequenza numerica per la registrazione rendiconto in Commerce headquarters, attieniti alla seguente procedura.

1. Fare clic su **Amministrazione organizzazione \> Sequenze numeriche \> Sequenze numeriche**.
1. Seleziona **Nuovo \> Sequenza numerica** per creare un nuovo record.
1. Nella Scheda dettaglio **Identificazione**, nel campo **Codice sequenza numerica**, immetti un codice di sequenza numerica.
1. Immetti un nome nel campo **Nome sequenza numerica**.
1. Nella Scheda dettaglio **Parametri di ambito**, nel campo **Ambito**, seleziona **Unità operativa**.
1. Nel campo **Unità Operativa** seleziona il negozio per cui verrà utilizzata la sequenza numerica.
1. Sulla scheda dettaglio **Segmenti** definisci i segmenti.
1. Sulla Scheda dettaglio **Riferimenti**, imposta il campo **Area** su **Punto vendita al dettaglio**.
1. Imposta il campo **Riferimento** su **Numero rendiconto**, quindi seleziona **OK**.

    ![Schede dettaglio Identificazione, Parametri di ambito, Segmenti e Riferimenti nella pagina Sequenze numeriche.](media/retail-statements-num-seq-setup-01.png)

1. Sulla Scheda dettaglio **Generale**, nella sezione **Allocazione numero** aggiorna i campi **Minimo** e **Massimo** in modo che corrispondano alla lunghezza del segmento **Alfanumerico** che hai definito nella scheda dettaglio **Segmenti**.
1. Sulla scheda dettaglio **Prestazioni** ti consigliamo di impostare l'opzione **Preallocazione** su **sì** e il campo **Quantità di numeri** su **25**.

    ![Schede dettaglio Generale e Prestazioni nella pagina Sequenze numeriche.](media/retail-statements-num-seq-setup-02.png)

1. Seleziona **Salva** nel riquadro azioni per salvare le modifiche e chiudere la pagina.
