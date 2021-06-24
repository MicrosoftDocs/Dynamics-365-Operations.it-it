---
title: Dashboard di gestione dell'utilizzo
description: Questo argomento spiega come utilizzare il dashboard di gestione dell'utilizzo per monitorare l'utilizzo del servizio di fatturazione elettronica mantenendo la conformità.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130508"
---
# <a name="usage-management-dashboard"></a>Dashboard di gestione dell'utilizzo

[!include [banner](../includes/banner.md)]

Il dashboard **Gestione dell'utilizzo** permette di monitorare l'utilizzo del servizio di fatturazione elettronica e quindi aiuta l'organizzazione a rimanere conforme in termini di utilizzo mensile. La conformità viene determinata calcolando il volume di invii e confrontandolo con il volume di invii acquisito per identificare eventuali scostamenti tra il volume acquisito e il volume utilizzato.

La dashboard include i seguenti indicatori:

- Un indicatore dei costi che è possibile utilizzare per monitorare il consumo ai fini della conformità delle licenze:

    - Utilizzo mensile (esportazione)

- Tre indicatori operativi che è possibile utilizzare per monitorare l'utilizzo del servizio di fatturazione elettronica a fini gestionali:

    - Utilizzo per funzionalità
    - Utilizzo per ambiente
    - Utilizzo mensile (importazione)

## <a name="measurement-scope"></a>Ambito della misurazione

- Unità di misura: 

    Il dashboard **Gestione dell'utilizzo** conta l'invio di documenti aziendali e fatture elettroniche importate.

- Organizzazione: 

    Il conteggio viene riepilogato dall'ID tenant dell'organizzazione, indipendentemente dal numero di istanze di Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management, ovvero il numero di persone giuridiche in cui è abilitato il servizio di fatturazione elettronica.


## <a name="indicator-usage-per-month-export"></a>Indicatore: utilizzo mensile (esportazione)

Questo indicatore fornisce dettagli sulle fatture elettroniche emesse dall'organizzazione durante un periodo definito.

### <a name="scope"></a>Ambito
- Il numero di documenti commerciali inviati da Finance e Supply Chain Management al servizio di fatturazione elettronica, indipendentemente dal numero di righe contenute in tali documenti commerciali.
- Il numero di documenti commerciali inviati che vengono elaborati correttamente dal servizio di fatturazione elettronica. Un documento viene considerato elaborato correttamente quando viene completato il flusso di azioni definito nell'impostazione della funzionalità.

> [!NOTE]
> Quando una fattura elettronica viene inviata a un servizio Web esterno, il conteggio è indipendente dai risultati dell'elaborazione del servizio Web (accettato, rifiutato o errore di convalida dello schema). Se il servizio Web ha ricevuto e risposto alla richiesta del servizio di fatturazione elettronica, l'invio è considerato un conteggio valido.

- **Eccezione:** i documenti commerciali non vengono conteggiati se vengono reinviati da Finance e Supply Chain Management al servizio di fatturazione elettronica, ad esempio negli scenari in cui è necessario inviare nuovamente lo stesso documento commerciale per modificare lo stato della fattura elettronica. Ad esempio, l'emissione di una fattura elettronica brasiliana (documento fiscale) viene considerata valida, ma la richiesta di annullamento non viene conteggiata.


### <a name="calculation"></a>Calcolo

Il calcolo del saldo è calcolato come segue:

Saldo = Gratuito + Acquistato – Usato

Percorso:

- Gratuito:
  
    Un volume gratuito di documenti commerciali che il cliente può inviare ogni mese. Include un pacchetto di 100 documenti commerciali che possono essere inviati al servizio di fatturazione elettronica. Il volume gratuito non è cumulativo e l'eventuale saldo residuo non viene riportato al periodo successivo.
  
- Acquistato:
  
    Un pacchetto di 1.000 documenti commerciali che possono essere inviati al servizio di fatturazione elettronica. Questo pacchetto deve essere acquistato per l'organizzazione su base mensile. Il volume acquistato non è cumulativo e l'eventuale saldo residuo non viene riportato al periodo successivo.
  
- Usato: 

    Il conteggio dei documenti commerciali inviati al servizio di fatturazione elettronica secondo criteri definiti.
   
> [!IMPORTANT]
> Se l'organizzazione prevede di superare il volume mensile di 100 invii gratuiti, sarà necessari acquistare il volume di picco per garantire la conformità ai criteri di licenza Microsoft per il servizio di fatturazione elettronica.
>
> Attualmente, il volume acquistato deve essere immesso manualmente, in base alla data di acquisizione, come pacchetti multipli di 1.000 invii.

## <a name="indicator-usage-by-feature"></a>Indicatore: utilizzo per funzione

Questo indicatore mostra l'utilizzo delle funzionalità di fatturazione elettronica per l'emissione di fatture elettroniche durante un periodo definito.

- Calcolo:
  
    Usato = Il numero di volte in cui ciascuna funzionalità di fatturazione elettronica è stata utilizzata durante l'invio di documenti commerciali al servizio di fatturazione elettronica.

## <a name="indicator-usage-by-environment"></a>Indicatore: utilizzo per ambiente

Questo indicatore mostra l'utilizzo degli ambienti del servizio di fatturazione elettronica durante un periodo definito.

- Calcolo:
    
    Usato = Il numero di volte in cui ciascun ambiente del servizio di fatturazione elettronica è stato utilizzato durante l'invio di documenti commerciali al servizio di fatturazione elettronica.

## <a name="indicator-usage-per-month-import"></a>Indicatore: utilizzo mensile (importazione)

Questo indicatore mostra il volume di importazione delle fatture elettroniche da parte del servizio di fatturazione elettronica in Finance e Supply Chain Management durante un periodo definito.

- Ambito:

    Fatture elettroniche importate in Finance e Supply Chain Management, indipendentemente dal numero di righe contenute in tali fatture elettroniche.

- Calcolo:

    Ricevute = Il conteggio delle fatture elettroniche importate in Finance e Supply Chain Management.

## <a name="functions"></a>Funzioni
### <a name="purchase"></a>Acquisti

Nella scheda **Utilizzo mensile (esportazione)**, selezionare **Acquisto** per registrare manualmente l'importo degli invii acquisiti.

Per una data specifica, selezionare **Nuovo** e immettere il numero di **pacchetti** acquisiti in quella data.

La **quantità** viene calcolata nel seguente modo:

Quantità = Pacchetti * 1.000

La **quantità** calcolata si riflette in **Acquistato** dall'indicatore **Utilizzo mensile (esportazione)**.

### <a name="update"></a>Aggiornamento

Nel riquadro delle azioni, selezionare **Aggiorna** per aggiornare il calcolo e i dati mostrati nella pagina e nel grafico.

### <a name="reset-history-data"></a>Reimposta dati dello storico

Nel riquadro delle azioni, selezionare **Ripristina dati cronologia** per aggiornare il database da cui vengono calcolati gli indicatori.




> [!NOTE]
> Il dashboard **Gestione dell'utilizzo** non mostra gli importi monetari. Al contrario, mostra solo il volume degli invii conteggiati e dei documenti importati.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
