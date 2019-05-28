---
title: Novità o modifiche in Dynamics 365 for Talent (26 marzo 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 568a16a17ed3269c7b72f27f0d4b7bbdbd56630e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518395"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-26-2019"></a>Novità o modifiche in Dynamics 365 for Talent (26 marzo 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="enhancements-to-interview-scheduling"></a>Miglioramenti alla programmazione dei colloqui
I seguenti miglioramenti sono disponibili per la programmazione dei colloqui.

- I responsabili delle assunzioni o i selezionatori ora possono attivare manualmente un promemoria per ricordare a un responsabile del colloquio di inviare il relativo riscontro. Anche il modello di messaggio di posta elettronica associato al promemoria è configurabile.
- Durante la condivisione del riepilogo del colloquio con il candidato, il programmatore del colloquio può scegliere di nascondere i nomi dei responsabili del colloquio nonché le righe nella visualizzazione del riepilogo del colloquio.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

### <a name="embedded-images-in-activities"></a>Immagini incorporate nelle attività
Ora è possibile incorporare immagini direttamente nelle attività. Oltre a poter copiare e incollare immagini dal Web, è possibile caricare immagini dal file system locale. La dimensione dell'attività è limitata a 1 MB. Se l'immagine è troppo grande, ridimensionarla e riprovare a caricarla.

[![Mapping](./media/embedimages.png)](./media/embedimages.png)

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR
**Build 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Supporto per campi personalizzati disponibile per le entità di selezione in Common Data Service 

Le seguenti entità di Common Data Service ora supportano campi dei clienti creati in Dynamics 365 for Talent:

- Lavoro
- Origine etnica
- Stato veterano
- Codice lingua
- Posizione
- Tipo di posizione
- Funzione lavorativa
- Posizione
- Tipo di posizione
 
### <a name="employment-history-not-displayed-chronologically"></a>Storico delle esperienze lavorative non visualizzato in ordine cronologico
Con questa modifica, la pagina dello storico delle esperienze lavorative ora visualizza i record delle esperienze lavorative in ordine cronologico, indipendentemente dalla società. È anche possibile utilizzare opzioni di ordinamento per ordinare i record per società.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>I piani di retribuzione fissa non sono visualizzati quando si limitano gli utenti per società in Sicurezza.
In questa versione, i piani di retribuzione fissa ora sono visualizzati quando si limitano gli utenti per società in Sicurezza. Tutte le impostazioni di sicurezza saranno rispettate e i piani fissi saranno visualizzati per le società per le quali l'utente dispone di autorizzazioni di accesso. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Impossibile eliminare i record relativi alle mansioni utilizzando l'opzione Apri in Excel di Talent
Con questa versione, è ora possibile rimuovere i record relativi alle mansioni utilizzando l'opzione **Apri in Excel** di Dynamics 365 for Talent.

### <a name="upgrade-to-common-data-service"></a>Aggiornamento a Common Data Service
Le scadenze per l'aggiornamento di Common Data Service sono imminenti. Accedere all'interfaccia di amministrazione PowerApps per determinare se il database deve essere aggiornato. Per ulteriori informazioni sulle scadenze e sui passaggi necessari per eseguire l'aggiornamento, vedere [Aggiornamento di Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>In anteprima

Per informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Accesso alle funzionalità di anteprima in Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Consentire la specifica dei codici motivo nei tipi di congedo
Le organizzazioni potrebbero necessitare di informazioni aggiuntive sulle richieste di permesso. Per ottenere queste informazioni, i dipendenti devono includere un codice motivo nelle relative richieste di permesso. In questa versione, è ora possibile specificare i codici motivo associati a un determinato tipo di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Configurare i codici motivo da richiedere quando si inviano richieste di permesso per determinati tipi di congedo
Le organizzazioni potrebbero richiedere l'impostazione di codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Ciò potrebbe essere necessario in base a un requisito normativo nel proprio paese o a un criterio della società. Questa versione consente alle Risorse umane di specificare quali tipi di congedo richiedono un codice motivo. Ciò viene applicato quando i dipendenti inviano richieste di permesso in cui il congedo richiede un codice motivo.

## <a name="coming-soon"></a>Presto disponibili

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Protezione retribuzione avanzata (fissa e variabile)
In molte organizzazioni, i responsabili delle retribuzioni e dei benefit potrebbero avere accesso solo a determinati record di retribuzione. Questi record potrebbero essere per dirigenti o dipendenti regionali. Con questa modifica, le Risorse umane possono gestire i piani di retribuzione per differenti gruppi di dipendenti nell'organizzazione. È possibile assegnare ruoli di sicurezza a piani fissi e variabili che determinano l'accesso ai piani e ai dati dei dipendenti correlati ai piani, ad esempio record di stipendi o premi. Solo i ruoli a cui è consentito l'accesso possono elaborare la retribuzione per quei dipendenti.

###  <a name="email-support-for-alerts"></a>Supporto di messaggi di posta elettronica per avvisi
Grazie all'aggiornamento 25 della piattaforma, gli utenti possono creare regole di avviso che inviano automaticamente notifiche di posta elettronica ai contatti quando avviate da un evento. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Verifiche di dipendenti duplicati: modifiche dell'interfaccia utente
Con questa modifica, i duplicati vengono rilevati durante l'immissione nei campi Nome e uno stato indica il numero di duplicati trovati. È possibile selezionare il collegamento fornito per aprire una nuova pagina e valutare se utilizzare la corrispondenza rilevata. Per evitare di interrompere l'immissione di dati, il modulo Duplicati non viene aperto automaticamente.
