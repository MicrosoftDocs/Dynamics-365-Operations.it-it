---
title: Modulo di check-in per il ritiro
description: In questo argomento viene descritto il modulo di check-in per il ritiro e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e7bae4ae7c2f3367132b03accb31c01c5f3b673e
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937595"
---
# <a name="check-in-for-pickup-module"></a>Modulo di check-in per il ritiro

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

In questo argomento viene descritto il modulo di check-in per il ritiro e la procedura per configurarlo in Microsoft Dynamics 365 Commerce.

Il modulo di check-in per il ritiro fornisce una pagina di conferma per i clienti che utilizzano le funzionalità di check-in dei clienti di Dynamics 365 Commerce per notificare il loro arrivo a un punto vendita. Il modulo di check-in per il ritiro consente inoltre di configurare un modulo che raccoglie informazioni aggiuntive dai clienti per facilitare la consegna degli ordini. Queste informazioni includono il numero di parcheggio del cliente e la marca e il modello del veicolo. 

## <a name="module-properties"></a>Proprietà del modulo

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Testo di conferma | Stringa di testo | Contenuto dell'intestazione che appare nella pagina di conferma del check-in. |
| Mostra codice a matrice | **True** o **False** | Quando questa proprietà è impostata su **True**, la pagina di conferma del check-in mostra un codice a matrice che rappresenta l'ID di conferma dell'ordine. |
| Intestazione di informazioni aggiuntive | Stringa di testo | Contenuto dell'intestazione che appare quando sono stati configurati campi di informazioni aggiuntive. |
| Chiavi di informazioni aggiuntive | Coppia ID risorsa/valore risorsa | Ogni chiave crea un campo modulo e un'etichetta associata che vengono utilizzati per raccogliere informazioni aggiuntive dei clienti. |
| Chiavi di informazioni aggiuntive \> ID risorsa | Stringa di testo | Ogni chiave di informazione crea un campo modulo e un'etichetta associata che vengono utilizzati per raccogliere informazioni aggiuntive dei clienti. Questa proprietà identifica la chiave delle informazioni aggiuntive. Nell'attività creata nel POS, il valore di questa proprietà viene mostrato come etichetta nel campo delle istruzioni. |
| Chiavi di informazioni aggiuntive \> Valore risorsa | Stringa di testo | L'etichetta per il campo di testo dell'attività in POS. |
| Chiavi di informazioni aggiuntive \> Obbligatorio | **True** o **False** | Questa proprietà specifica se i clienti devono compilare il campo modulo prima di poter continuare. Quando questa proprietà è impostata su **True**, viene visualizzato un asterisco accanto all'etichetta del modulo e viene eseguito un controllo di verifica di valori Null per impedire ai clienti di continuare se non viene immesso alcun valore. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Aggiungere il modulo di check-in per il ritiro a una pagina

Il modulo di check-in per il ritiro dovrebbe essere aggiunto alla nuova pagina che crei per la conferma del check-in. Quella pagina servirà come esperienza di conferma del check-in per i clienti che selezionano il collegamento o pulsante **Sono qui** nel loro messaggio e-mail. 

## <a name="configure-the-additional-information-form"></a>Configurare il modulo di informazioni aggiuntive

Per impostazione predefinita, se non sono configurate chiavi di informazioni aggiuntive, il modulo mostra ai clienti la pagina di conferma del check-in. Quando viene visualizzata la conferma del check-in, viene creata un'attività nel POS per il punto vendita in cui viene ritirato l'ordine.

Quando vengono configurate una o più chiavi di informazioni aggiuntive, ai clienti viene prima richiesto di immettere le informazioni. Quando selezionano **Invia**, viene mostrata la conferma del check-in e viene creata un'attività in POS. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare le notifiche di check-in dei clienti nel POS](enable-customer-check-in.md)
