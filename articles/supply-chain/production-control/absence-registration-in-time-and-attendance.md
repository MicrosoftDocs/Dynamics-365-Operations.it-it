---
title: Registrazioni delle assenze in Orario e presenze
description: In questo argomento viene descritto come gestire le registrazioni delle assenze in Orario e presenze.
author: johanhoffmann
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 961b87fb066018f9f6ecc3dcc3cc88e64574bb64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246551"
---
# <a name="absence-registration-in-time-and-attendance"></a>Registrazioni delle assenze in Orario e presenze

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i concetti relativi alle assenze e viene illustrata la modalità di gestione delle assenze in Orario e presenze.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Assenze basate su un orario di lavoro normale

I lavoratori vengono considerati assenti nelle ore in cui non lavorano durante un orario di lavoro normale. Gli orari di lavoro normali sono definiti nel profilo tempo standard di un lavoratore.

Ad esempio, il profilo tempo di un lavoratore prevede l'entrata alle 07.00 e l'uscita alle 15.00. Se un lavoratore entra alle 9:00, è considerato assente dalle 7:00 alle 9:00 in quel giorno.

In questo caso, ai lavoratori viene richiesto di fornire un motivo dell'assenza. Possono specificare un motivo selezionando un codice assenza.

## <a name="absence-codes"></a>Codici assenze

I codici assenze consentono di definire i vari tipi di assenze. I codici assenze sono definiti dalla società.

Varie regole possono essere applicate ai codici assenze. Ad esempio, un codice assenza può essere configurato per detrarre o concedere la retribuzione.

Ad esempio, una società definisce un codice assenza **In ritardo** che i lavoratori utilizzano se arrivano in ritardo e non hanno un valido motivo. La società definisce inoltre un codice assenza **Corso interno** che i lavoratori utilizzano per il tempo speso a frequentare corsi interni. Questi codici assenze possono essere impostati di modo che **In ritardo** venga dedotto dalla retribuzione di un lavoratore mentre **Corso interno** non lo sia.

È possibile impostare codici assenze automatici. Questi codici assenze possono essere utilizzati per calcolare il tempo di un lavoratore quando non viene registrata alcuna assenza. Il profilo tempo del lavoratore determina se viene utilizzato il codice assenza dell'orario standard o dell'orario flessibile.

### <a name="set-up-standard-time-and-flex-time"></a>Configurazione dell'orario standard e dell'orario flessibile

- Configurare i parametri relativi all'orario standard e all'orario flessibile utilizzando le opzioni **Assenza automatica di inserimento** e **Inserimento automatico della flessibilità in difetto-** nella pagina **Parametri Orario e presenze**.

## <a name="absence-groups"></a>Gruppi assenze

I codici assenze sono raggruppati in gruppi assenze. È possibile utilizzare i gruppi assenze per raggruppare codici assenze con caratteristiche comuni. Gli esempi includono codici assenze per un'assenza legale o un'assenza dovuta ad un appuntamento medico, una funzione pubblica o un figlio malato.

## <a name="planned-absence"></a>Assenza pianificata

Se è noto che un lavoratore sarà assente per un periodo, ad esempio in seguito ad una vacanza imminente, è possibile utilizzare l'assenza pianificata. È possibile impostare l'assenza pianificata configurando il codice assenza affinché prenda in considerazione l'assenza pianificata. Quando si imposta un'assenza pianificata, non verrà richiesto di specificare un codice assenza durante il periodo di assenza quando vengono calcolate le registrazioni ore. L'assenza pianificata può essere definita per un singolo lavoratore, oppure è possibile definire un processo batch per aggiornare in blocco l'assenza pianificata dei lavoratori.

### <a name="set-up-planned-absence"></a>Configurare l'assenza pianificata

1. Selezionare **Risorse umane** &gt; **Lavoratori** &gt; **Dipendenti** e selezionare un dipendente.
2. Selezionare **Ora** &gt; **Assegnazione ora** &gt; **Registrazione assenze** e impostare l'assenza pianificata.

## <a name="interrupted-planned-absence"></a>Assenza pianificata interrotta

Se si applica l'opzione **Interrompi** quando si configura un'assenza pianificata, questa verrà interrotta se il lavoratore entra durante il periodo di assenza pianificato. L'assenza pianificata verrà contrassegnata come **Interrotto** e non produrrà alcun effetto sui calcoli futuri.

### <a name="set-up-a-planned-absence-for-interruption"></a>Impostare un'assenza pianificata per l'interruzione

1. Aprire la pagina **Registrazione assenze** come descritto nella procedura per l'impostazione dell'assenza pianificata.
2. Selezionare **Interrompi**.

L'opzione **Interrompi** viene applicata quando il tempo viene registrato tramite il terminale o il dispositivo dello shop floor. L'opzione non viene applicata se le registrazioni vengono immesse nelle pagine di calcolo e approvazione o nella pagina **Scheda elettronica dipendente**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Esempi di utilizzo dell'assenza in un profilo flessibile

I seguenti tre esempi illustrano il modo in cui l'assenza viene calcolata in un profilo con periodi flessibili.

Gli esempi utilizzano il profilo riportato di seguito.

| Entrata | Orario standard    | Interruzione             | Orario standard | Flessibilità in difetto-        | Uscita | Flessibilità in eccesso        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 8     | Dalle 9 alle 11:30 | Dalle 11:30 alle 12 | Dalle 12 alle 15 | Dalle 15 alle 16 | 16      | Dalle 15 alle 16 |

### <a name="example-1-signing-out-during-a-flex--period"></a>Esempio 1: uscita durante il periodo di flessibilità in difetto

Il lavoratore entra alle 8:00 ed esce alle 15:30. In questo caso, poiché il lavoratore esce durante il periodo di flessibilità in difetto, non viene calcolata alcuna assenza e una mezz'ora viene detratta dal saldo flessibilità del lavoratore.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Esempio 2: uscita durante un periodo di tempo standard

Il lavoratore entra alle 8:00 ed esce alle 14:30. In questo caso, poiché il lavoratore esce durante il periodo di tempo standard, l'assenza viene calcolata dalle 14:30 alle 16 e viene registrato un periodo di assenza di 1,5 ore. Un codice assenza per quel periodo è obbligatorio.

### <a name="example-3-signing-out-during-a-flex-period"></a>Esempio 3: uscita durante un periodo di flessibilità in eccesso

Il lavoratore entra alle 8:00 ed esce alle 16:30. In questo caso, poiché il lavoratore esce durante un periodo di flessibilità in eccesso, non viene calcolata alcuna assenza e una mezz'ora viene aggiunta al saldo flessibilità del lavoratore.

## <a name="absence-in-the-calculation-and-approval-process"></a>Assenza nel processo di calcolo e di approvazione

Le registrazioni ore del lavoratore devono essere calcolate e approvate prima di poter essere trasferite in un sistema di retribuzione come elementi retributivi.

Un approvatore può modificare le registrazioni ore di un lavoratore. L'approvatore può anche modificare qualsiasi assenza che il lavoratore ha registrato. Se l'approvatore immette manualmente un periodo di tempo a cui è associato un codice assenza, il codice assenza per quel periodo non viene sostituito dal codice assenza predefinito nei parametri Orario e presenze.

Ad esempio, un lavoratore entra alle 10 e seleziona un codice assenza che indica che è in ritardo. Successivamente, il lavoratore informa il supervisore che aveva un appuntamento medico dalle 8 alle 10. Un appuntamento medico non deve causare una detrazione dalla retribuzione del lavoratore. Di conseguenza, in questo caso, il supervisore può rettificare le due ore di assenza dalle 8 alle 10 immettendo manualmente un codice assenza indicante malattia per quelle due ore.

### <a name="calculate-and-approve-absence"></a>Calcolare e approvare l'assenza

- Selezionare **Orario e presenze** &gt; **Rivedi e approva** &gt; **Approva o Calcola**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]