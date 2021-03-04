---
title: Parametri per gestione modifiche di progettazione
description: Questo argomento descrive come configurare le funzionalità di gestione delle modifiche per Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 0cf0e56a8aece98379aa0f181d7b7ff665767544
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431601"
---
# <a name="engineering-change-management-parameters"></a>Parametri per gestione modifiche di progettazione

[!include [banner](../includes/banner.md)]

La pagina **Parametri per gestione modifiche di progettazione** contiene parametri di configurazione che modificano il comportamento predefinito correlato alla struttura del prodotto di rilascio e ai processi di gestione delle modifiche di progettazione.

## <a name="open-the-engineering-change-management-parameters-page"></a>Aprire la pagina Parametri per gestione modifiche di progettazione

Per aprire la pagina **Parametri per gestione modifiche di progettazione**, andare a **Gestione modifiche di progettazione \> Imposta \> Parametri per gestione modifiche di progettazione**. È quindi possibile impostare i campi come descritto nelle sezioni rimanenti di questo argomento.

## <a name="release-control-tab"></a>Scheda Controllo rilascio

La tabella seguente descrive i campi disponibili nella scheda **Controllo rilascio** della pagina **Parametri per gestione modifiche di progettazione**. Questi campi interessano il processo correlato alla struttura del prodotto di rilascio.

| Campo | descrizione |
|---|---|
| Regola numero articolo | Selezionare come definire il numero di articolo quando il prodotto viene rilasciato a una persona giuridica. Selezionare *Numero prodotto di progettazione* se il numero del prodotto nella persona giuridica ricevente deve corrispondere al numero del prodotto nella società di progettazione. Selezionare *Sequenza numerica articolo locale* se il prodotto deve acquisire il numero successivo nella sequenza numerica per i numeri di prodotto nella persona giuridica ricevente. |
| Regola nome DBA | Selezionare la modalità di definizione del nome della distinta base (DBA) quando il prodotto viene ricevuto (rilasciato) da una persona giuridica. Selezionare *Nome di progettazione* o *Numero articolo in ricevimento*. |
| Regola nome ciclo di lavorazione | Selezionare la modalità di definizione del nome di ciclo di lavorazione quando il ciclo di lavorazione di un prodotto viene ricevuto (rilasciato) da una persona giuridica. Selezionare *Nome di progettazione* o *Numero articolo in ricevimento*. |
| Esegui controllo DBA | Selezionare se verrà eseguito un controllo DBA quando il prodotto viene ricevuto (rilasciato) da una persona giuridica. |
| Comportamento rilascio DBA inattiva | Selezionare se un prodotto può essere rilasciato se è associato a una DBA inattiva. Selezionare *Accetta*, *Solo avviso* o *Non consentito*. |
| Comportamento rilascio ciclo di lavorazione inattivo | Selezionare se un prodotto può essere rilasciato se è associato a un ciclo di lavorazione inattivo. Selezionare *Accetta*, *Solo avviso* o *Non consentito*.|
| Accettazione prodotto | Selezionare se è necessario un passaggio aggiuntivo per l'accettazione prima che il prodotto possa essere rilasciato alla persona giuridica. Selezionare *Manuale* per aggiungere la fase di accettazione. In questo caso, nella pagina **Rilasci di prodotto aperti** verranno visualizzati i prodotti. Selezionare *Automatico* per mostrare il prodotto direttamente nella pagina **Prodotti rilasciati** nella persona giuridica di destinazione immediatamente dopo il rilascio del prodotto insieme alla struttura del prodotto di rilascio relativa. |

## <a name="engineering-change-management-tab"></a>Scheda Gestione modifiche di progettazione

La tabella seguente descrive i campi disponibili nella scheda **Gestione modifiche di progettazione** della pagina **Parametri per gestione modifiche di progettazione**. Queste impostazioni influiscono sul processo di gestione delle modifiche di progettazione.

| Campo | descrizione |
|---|---|
| Categoria | Categoria predefinita che verrà utilizzata quando viene creata una richiesta di modifica di progettazione. |
| Priorità | Priorità predefinita che verrà utilizzata quando viene creata una richiesta di modifica di progettazione. |
| Regola gravità | Selezionare come stabilire la gravità di un ordine di modifica di progettazione. Selezionare *Manuale* se si prevede che l'utente immetta un valore nel campo **Gravità**. Selezionare *Calcola* per fare in modo che il sistema calcoli il valore di **Gravità** quando si seleziona **Calcola gravità** nel riquadro azioni dell'ordine di modifica di progettazione. In questo caso, il sistema utilizzerà le regole di gravità definite nella pagina **Set regole di gravità**. Selezionare *Calcola automaticamente* in modo che il valore del campo **Gravità** venga calcolato e compilato automaticamente in base ai set di regole di gravità. |
| Nuovo rilascio prodotti interessati | Questo campo è applicabile quando i prodotti vengono nuovamente rilasciati tramite un ordine di modifica di progettazione. È possibile selezionare se proporre tutti i prodotti o solo i prodotti interessati nella finestra di dialogo **Rilasci**. |
| Livelli DBA da rilasciare | Profondità del livello DBA da rilasciare. Se la distinta base ha più livelli (ovvero, se è più profonda) del valore qui specificato, verranno rilasciati solo i livelli fino al valore specificato. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]