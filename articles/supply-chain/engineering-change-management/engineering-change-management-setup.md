---
title: Stabilire valori comuni per la gestione delle modifiche di progettazione
description: In questo argomento viene descritto come stabilire valori comuni utilizzati per i parametri in varie parti della gestione delle modifiche di progettazione.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: ee2be7d59f327876b92386c66433aeaf06df489c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262359"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Stabilire valori comuni per la gestione delle modifiche di progettazione

[!include [banner](../includes/banner.md)]

Quando si imposta la gestione delle modifiche di progettazione, è necessario stabilire diverse raccolte di valori che verranno utilizzate per compilare elenchi a discesa in altre parti dell'interfaccia utente. È necessario specificare questi valori in base ai tipi di prodotti che si realizzano e alle esigenze aziendali specifiche.

## <a name="engineering-change-categories"></a>Categorie delle modifiche di progettazione

Le categorie di modifiche di progettazione vengono utilizzate per organizzare gli ordini di modifica di progettazione in modo che siano più facili da gestire e rivedere. Ad esempio, potrebbe risultare utile impostare un flusso di lavoro in cui, a seconda della categoria, un reparto specifico deve esaminare le modifiche proposte. Pertanto, l'ordine di modifica di progettazione include un campo **Categoria**.

Per stabilire la raccolta di categorie delle modifiche di progettazione utilizzate nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Categorie modifiche di progettazione**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="engineering-change-priorities"></a>Priorità delle modifiche di progettazione

Le priorità di modifica di progettazione vengono utilizzate per indicare l'importanza o l'urgenza di un ordine di modifica di progettazione. Possono aiutarti a tenere traccia dell'importanza di un ordine di modifica di progettazione, in modo da identificare facilmente quali ordini devono essere elaborati per primi e quanto velocemente.

Per stabilire la raccolta di priorità delle modifiche di progettazione utilizzate nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Priorità modifiche di progettazione**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="engineering-change-reasons"></a>Motivi della modifica di progettazione

I motivi della modifica di progettazione indicano la causa o la natura della modifica nell'ordine di modifica.

Per stabilire la raccolta di motivi delle modifiche di progettazione utilizzati nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Motivi modifiche di progettazione**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="material-disposal-codes"></a>Codici di dismissione materiale

I codici di smaltimento dei materiali vengono utilizzati per classificare i materiali utilizzati nei prodotti finiti o i componenti da smaltire in modo specifico o che richiedono un trattamento prima che sia possibile aggiungerli ai rifiuti normali. Quando si aggiunge un prodotto rilevante a un ordine di modifica di progettazione, è possibile assegnare un codice di smaltimento come parte dei dettagli della modifica.

Per stabilire la raccolta dei codici di smaltimento dei materiali utilizzati nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Codici di smaltimento materiali**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="received-customer-approval"></a>Approvazione del cliente ricevuta

Quando si progettano prodotti per un cliente specifico, il progetto e le specifiche spesso devono essere convalidati prima che il prodotto possa essere impostato come pronto. Il campo **Approvazione cliente ricevuta** consente di indicare a che punto del processo di approvazione del cliente si trova il prodotto e/o se l'approvazione è stata ricevuta.

Per stabilire la raccolta dei valori di approvazione del cliente ricevuti utilizzati nella propria azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Approvazione cliente ricevuta**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Modifica di progettazione - Codici di salute e sicurezza ambientali

Se durante la realizzazione di un prodotto è necessario prendere in considerazione normative o procedure standard in materia di salute e sicurezza ambientale o regolamenti o procedure specifici dell'azienda, è possibile utilizzare i codici di salute e sicurezza ambientali per definirli. Nell'ordine di modifica di progettazione è possibile indicare quali codici si applicano alla realizzazione di un prodotto mentre si modificano i dettagli del prodotto interessato.

Per stabilire la raccolta di valori di salute e sicurezza utilizzati nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Modifica di progettazione - Codici di salute e sicurezza ambientali**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

## <a name="engineering-change-severities"></a>Gravità della modifica di progettazione

Le gravità delle modifiche di progettazione consentono di indicare il livello di impatto che si applica ai prodotti in un ordine di modifica di progettazione.

Per stabilire la raccolta di gravità delle modifiche di progettazione utilizzate nell'azienda, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Gravità modifiche di progettazione**. È quindi possibile utilizzare i pulsanti nel riquadro azioni per aggiungere, rimuovere e modificare i valori e per disporli nell'ordine in cui devono essere visualizzati negli elenchi a discesa in cui vengono visualizzati.

È possibile stabilire regole che si applicano a ogni livello di gravità creato. Per ulteriori informazioni su come assegnare queste regole, vedere la sezione successiva.

## <a name="engineering-change-severity-rule-sets"></a>Set di regole di gravità modifica di progettazione

I set di regole di gravità delle modifiche di progettazione vengono utilizzati per stabilire un gruppo di regole che è possibile utilizzare per calcolare automaticamente la gravità dell'ordine di modifica, in base al tipo di modifiche nei prodotti interessati. Per utilizzare le regole di gravità, aprire la pagina **Parametri per gestione modifiche di progettazione** e impostare il campo **Regola di gravità** su *Calcola* o su *Calcola automaticamente*.

Quando il sistema valuta la gravità, elabora le regole nell'ordine in cui appaiono sulla pagina, dall'alto verso il basso. Affinché una regola possa essere selezionata e avere una priorità stabilita, devono essere soddisfatte tutte le regole presenti in un set.

Per impostare le regole che si applicano a ogni livello di gravità di modifica definito, andare a **Gestione modifiche di progettazione \> Imposta \> Gestione modifiche di progettazione \> Set di regole di gravità modifiche di progettazione**. Eseguire quindi uno dei passaggi seguenti.

- Per creare un nuovo set di regole, selezionare **Nuovo** sul riquadro azioni e quindi impostare i campi descritti più avanti in questa sezione.
- Per modificare un set di regole esistente, selezionarlo nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi impostare i campi come descritto più avanti in questa sezione.
- Per eliminare un set di regole esistente, selezionarlo nel riquadro dell'elenco, quindi selezionare **Elimina** nel riquadro azioni.
- Per ridisporre l'elenco delle serie di regole, selezionare una serie di regole nel riquadro dell'elenco, quindi utilizzare i pulsante **Su** e **Giù** nel riquadro azioni per riposizionarlo.

Per ciascuno set di regole, impostare il campo seguente:

- **Gravità** - Selezionare il livello di gravità per cui stabilire le regole. Utilizzare la pagina **Gravità modifiche di progettazione** per creare i livelli e assegnarvi un nome. Per ulteriori informazioni, vedere la sezione precedente.

Utilizzare i pulsanti nella Scheda dettaglio **Regole** per aggiungere o rimuovere una regola per l'impostazione di gravità corrente. Per ogni regola è presente un campo **Regola** e un campo **Nome**. Le regole sono stabilite dal sistema e indicano i tipi di modifiche che un prodotto può subire. Il nome indica il tipo di modifica.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]