---
title: Configurare i libri contabili
description: Questo argomento fornisce informazioni su come configurare i libri contabili per ogni persona giuridica. Include informazioni su come selezionare le valute, i calendari fiscali, il piano dei conti e le strutture dei conti da utilizzare con ciascuna persona giuridica.
author: kweekley
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Ledger
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-09
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: aad10770750d2614da804380a7bba03d348e8c9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826205"
---
# <a name="configure-ledgers"></a>Configurare i libri contabili

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni su come configurare i libri contabili per ogni persona giuridica. Include informazioni su come selezionare le valute, i calendari fiscali, il piano dei conti e le strutture dei conti da utilizzare con ciascuna persona giuridica.

## <a name="selecting-the-chart-of-accounts"></a>Selezione del piano dei conti

Per ogni persona giuridica in Microsoft Dynamics 365 Finance, devono essere configurati i dettagli sul libro contabile. La pagina **Contabilità generale** consente di selezionare il piano dei conti e le strutture dei conti che verranno utilizzate per la persona giuridica selezionata. Puoi condividere il tuo piano dei conti e le strutture dei conti configurando la pagina **Contabilità generale** in ciascuna persona giuridica per utilizzare lo stesso piano dei conti e le stesse strutture dei conti. Puoi inoltre condividere parte della configurazione in ciascuna persona giuridica e avere configurazioni specifiche in ciascuna persona giuridica.

Se le persone giuridiche devono avere diversi piani dei conti o diverse strutture dei conti, la funzione di sostituzione della persona giuridica potrebbe essere utile. Utilizzando lo stesso piano dei conti e le stesse strutture dei conti per più persone giuridiche e quindi gestendo eventuali eccezioni tramite sostituzioni di entità giuridica, è possibile semplificare la manutenzione nel tempo.

Per configurare il piano dei conti per una persona giuridica, vai a **Contabilità generale \> Impostazione contabilità generale \> Contabilità generale**. Nella pagina **Contabilità generale**, seleziona **Piano dei conti**, quindi, seleziona nell'elenco il piano dei conti da utilizzare. Tieni presente che il piano dei conti non può essere modificato dopo aver selezionato un valore e registrato le transazioni nella persona giuridica.

Per ulteriori informazioni su come pianificare e configurare il piano dei conti e i conti principali, vedi [Pianificare il piano dei conti](plan-chart-of-accounts.md).

## <a name="selecting-account-structures"></a>Selezione delle strutture dei conti

Ogni persona giuridica in Dynamics 365 Finance può essere configurata per utilizzare una o più strutture di conto. Ogni struttura dei conti definisce le dimensioni finanziarie e le combinazioni di conti principali e dimensioni finanziarie che saranno consentite al momento della registrazione delle transazioni. Puoi utilizzare le stesse strutture dei conti in più di una persona giuridica.

Tieni presente che, se disponi di più strutture dei conti, puoi selezionare solo strutture dei conti che non hanno combinazioni sovrapposte di conti principali e dimensioni finanziarie. Ad esempio, una delle strutture dei tuoi conti è configurata per aggiungere una Business Unit per i conti principali tra 1000 e 1999. In un'altra struttura dei conti, hai aggiunto una dimensione finanziaria Reparto per i conti principali che iniziano con 1. In questo caso, solo una delle strutture dei conti può essere aggiunta nella stessa persona giuridica.

Per configurare le strutture dei conti per il tuo libro mastro, nella pagina **Contabilità generale**, nella Scheda dettaglio **Strutture dei conti**, seleziona **Aggiungi**, seleziona una struttura di conti nell'elenco, quindi scegli **Seleziona**. Potrebbero essere necessari alcuni minuti per aggiungere e salvare le strutture di conti. Tieni presente che le strutture dei conti che selezioni devono essere attive. In caso contrario, i dettagli delle strutture dei conti non saranno efficaci nelle persone giuridiche a cui sono collegati.

Per rimuovere una struttura dei conti, nella pagina **Contabilità generale**, nella Scheda dettaglio **Strutture dei conti**, seleziona **Rimuovi**. Tieni presente che, se rimuovi una struttura dei conti dal libro mastro, non rimuovi le transazioni registrate utilizzando la configurazione di quella struttura dei conti.

Per ulteriori informazioni su come configurare le strutture di conti, vedi [Configurare le strutture dei conti](configure-account-structures.md).

## <a name="configuring-calendars-for-the-ledger"></a>Configurazione dei calendari per il libro mastro

Un altro componente del libro mastro è il calendario fiscale. Per ogni persona giuridica è necessario selezionare un calendario fiscale. Puoi utilizzare lo stesso calendario fiscale in più di una persona giuridica. Quando selezioni un calendario fiscale per il libro mastro, viene creata una copia. Questa copia è denominata calendario di contabilità generale. Il calendario di contabilità generale consente di selezionare lo stato dei periodi e dei moduli in ciascun periodo.

Per accedere e aggiornare il calendario per la persona giuridica selezionata, nella pagina **Contabilità generale**, nel riquadro azioni seleziona **Calendario di contabilità generale**.

Per selezionare il calendario, seleziona **Calendari fiscali**, quindi seleziona il calendario nell'elenco. Se modifichi il calendario fiscale dopo che le transazioni sono state registrate nella persona giuridica, devi selezionare **Ricalcola periodi contabili**. Quindi, nella finestra di dialogo che appare, puoi aggiornare i saldi contabili per i periodi nel tuo calendario. Ti consigliamo di eseguire il processo **Ricalcola periodi contabili** nella modalità **BAtch** e di eseguirlo quando si verificano processi non critici nel sistema. A seconda del numero di transazioni e delle combinazioni di dimensioni finanziarie, questo processo può richiedere del tempo.

Se non è selezionato alcun calendario fiscale per una persona giuridica, riceverai un messaggio di errore quando tenti di registrare una transazione in quella persona giuridica.

Per ulteriori informazioni, vedere [Calendari fiscali, anni fiscali e periodi](../budgeting/fiscal-calendars-fiscal-years-periods.md).

## <a name="using-a-balancing-financial-dimension"></a>Utilizzo di una dimensione finanziaria di bilanciamento

Dopo aver selezionato il piano dei conti e aggiunto una o più strutture dei conti, è possibile selezionare facoltativamente una singola dimensione finanziaria da utilizzare come dimensione finanziaria di bilanciamento. La dimensione selezionata deve esistere in tutte le strutture dei conti. Deve inoltre essere bilanciata in tutte le registrazioni contabili. In altre parole, gli addebiti e gli accrediti devono essere uguali per il conto principale e per la dimensione finanziaria di bilanciamento. Il sistema crea automaticamente le transazioni per bilanciare le voci, in base ai conti principali specificati nei campi **Interunità di credito** e **Interunità di debito** nella pagina **Conti per transazione automatica**.

Per ulteriori informazioni sul bilanciamento delle voci, vedi [Giornali bilanciati per contabilizzazione interunità](example-balanced-journals-interunit-accounting.md).

## <a name="configuring-currencies-for-the-ledger"></a>Configurazione delle valute per la contabilità generale

La pagina **Contabilità generale** viene utilizzata anche per controllare e definire le valute che verranno utilizzate quando le transazioni vengono registrate nella contabilità generale. Devi specificare la valuta contabile, che è la valuta utilizzata nella colonna **Valuta contabile** nella contabilità generale su tutti i giustificativi . Inoltre, nella colonna **valuta di dichiarazione** puoi selezionare facoltativamente una seconda valuta. Se selezioni una valuta di dichiarazione, tutte le transazioni verranno registrate in quella valuta nella colonna **Valuta di dichiarazione** nella contabilità generale su tutti i giustificativi.

Se le transazioni vengono registrate in una valuta diversa, il sistema converte automaticamente l'importo della transazione dalla valuta delle transazioni nella valuta contabile e nella valuta di dichiarazione sul giustificativo. Nella pagina **Contabilità generale**, nel campo **Tipo di tasso di cambio valuta contabile** seleziona il tipo di tasso di cambio configurato per i tassi di cambio da utilizzare per convertire i valori dalla valuta della transazione alla valuta contabile su un giustificativo. Se hai selezionato una valuta di dichiarazione, devi anche impostare il campo **Tipo di tasso di cambio valuta di dichiarazione** per indicare il tasso di cambio da utilizzare per convertire i valori dalla valuta della transazione alla valuta di dichiarazione su un giustificativo.

Se utilizzi la funzionalità di definizione del budget, puoi anche impostare il campo **Tipo di tasso di cambio del budget** per indicare il tasso di cambio da utilizzare per convertire le transazioni di budget da una valuta all'altra.

Se utilizzi due valute o se utilizzi un'unica valuta ma le transazioni vengono registrate in una valuta diversa, devi configurare la Scheda dettaglio **Conti per rivalutazione valuta** della pagina **Contabilità generale**. In questa Scheda dettaglio si definiscono i conti profitti e perdite realizzati e non realizzati predefiniti che verranno utilizzati per impostazione predefinita quando vengono registrate le transazioni, se non è specificato nella pagina **Conti di rivalutazione valuta**. La pagina **Conti di rivalutazione valuta** viene utilizzata per configurare conti diversi per guadagni e perdite realizzati e non realizzati per ciascuna valuta.

I profitti e le perdite realizzati sono i profitti e le perdite realizzati dalle transazioni completate. Sono registrati nel rendiconto profitti e perdite. I guadagni e le perdite non realizzati sono profitti e perdite che si sono materializzati, ma la cui transazione non è stata completata. In altre parole, hai registrato una fattura, ad esempio, ma la fattura non è stata ancora liquidata e pagata. I profitti e le perdite non realizzati sono registrati nello stato patrimoniale.

Per ulteriori informazioni su come utilizzare due valute, vedi [Doppia valuta](dual-currency.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]