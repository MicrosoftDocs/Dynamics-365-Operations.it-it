---
title: Novità o modifiche in Dynamics 365 Human Resources (25 febbraio 2020)
description: Questo articolo descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Human Resources al 25 febbraio 2020.
author: andreabichsel
ms.date: 02/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ae5a834c89ac648f7b74080a2cba51e5a7fb1a68fa81a0269c581daee56b5f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770386"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Novità o modifiche in Dynamics 365 Human Resources (25 febbraio 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Dynamics 365 Human Resources. Le modifiche si applicano alla build 8.1.2927. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in LCS per riferimento.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Abilitare l'entità framework di gestione dei dati e navigazione di gestione dei casi (DMF) (414754)

Questa funzione di anteprima consente una navigazione aggiuntiva ai casi di gestione dei casi. È possibile abilitare questa funzione di anteprima nell'area di lavoro **Gestione funzionalità**. Queste voci di menu appaiono nell'area di lavoro **Conformità** di Dynamics 365 Human Resources. Con questa modifica, Human Resources può accedere a:

- Tutti i casi
- Casi personali
- Casi personali aperti
- Casi personali scaduti
- Casi assegnati all'utente tramite un flusso di lavoro

Insieme a queste nuove visualizzazioni dei casi, è disponibile l'entità DMF **Dettaglio caso**.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Abilitare le definizioni di relazione nel rubrica globale (414762)

Le relazioni sono ora abilitate nella rubrica globale. Prima dell'uscita di questa settimana, il riquadro Dettaglio informazioni **Relazioni** mostrava eventuali relazioni definite dal sistema. Ora è possibile definire quelle relazioni all'interno della pagina della rubrica globale.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>Una posizione può essere rimossa quando esistono record di compensazione attivi per la posizione (414568)

Con questa modifica, viene visualizzato un avviso quando si tenta di eliminare una posizione e un lavoratore ha un record di compensazione attivo per quella stessa posizione. In questo caso, è necessario aggiornare il record di retribuzione fissa del dipendente prima di rimuovere la posizione.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>Il flusso di lavoro di revisione delle prestazioni aggiunge occasionalmente le approvazioni da parte di persone che non fanno parte del processo (414171)

Questa modifica risolve un problema in cui i partecipanti di conferma aggiuntivi venivano aggiunti alla revisione delle prestazioni.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>Assegnazione della posizione del lavoratore non creata in Dataverse quando selezionata nella finestra di dialogo Nuovo lavoratore (413479)

Questa modifica corregge un problema durante l'assunzione di un nuovo lavoratore e l'assegnazione della nuova assunzione a una posizione nella finestra di dialogo **Nuovo lavoratore**. Ora l'assegnazione della posizione si riflette in Dataverse.

## <a name="coming-soon"></a>Presto disponibili

### <a name="updated-dataverse-solution"></a>Soluzione Dataverse aggiornata

Una nuova soluzione Dataverse sarà presto disponibile con le seguenti modifiche:

| Descrizione | Modifica |
| ----------------------------------------- | --- |
| Modifiche all'entità **Posizione lavorativa** | Aggiunta di **Paese di retribuzione**</br>Aggiunta di **Dimensioni finanziarie** |
| Modifiche all'entità **Lavoratore** | Aggiunta di **Sequenza nome**</br>Aggiunta di **Lavora da casa**</br>Aggiunta di **Lingua**</br>Aggiunta di **Data di anzianità**</br>Aggiunta di **Data di ricorrenza annuale**</br>Aggiunta di **Data di assunzione originale** |
| Modifiche all'entità **Impiego** | Aggiunta di **Dimensioni finanziarie**</br>Aggiunta di **Motivo fine rapporto**</br>**Data di transizione** rinominata in **Data fine rapporto**</br>Aggiunta di **Date periodo di prova** |
| Modifiche all'entità **Indirizzo lavoratore** | Aggiunta di **Nome della via**</br>**Riga indirizzo 1**, **Riga indirizzo 2** e **Riga indirizzo 3** contrassegnate per deprecamento |
| Nuove entità di impostazione della retribuzione variabile | **Tipo di piano di retribuzione variabile**</br>**Piano di retribuzione variabile**</br>**Regole distribuzione incentivi**</br>**Livello del piano di retribuzione variabile** |
| Nuova entità **Impiego calendario lavoratore** | Aggiunta di **Entità calendario lavoro** |
| Nuova entità **Dettagli posizione di retribuzione** | Aggiunta di **Dettagli posizione di retribuzione** |
| Nuova entità **Titolo** | Aggiunta di **Titolo**. La nuova entità **Titolo** sarà inclusa nel processo di sincronizzazione tra Human Resources e Dataverse. Inizialmente non vi verrà fatto riferimento dalle entità **Posizione lavorativa** o **Posizione**. |

Nelle prossime settimane, questi cambiamenti di entità saranno disponibili in tutti gli ambienti. Per installare manualmente l'ultima soluzione Dataverse per Human Resources:

1.  Accedere all'[Interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selezionare **Ambienti**.

3.  Trovare l'ambiente da aggiornare. L'ambiente deve corrispondere al **nome dell'ambiente** nella sezione **informazioni Common Data Service** del modulo **Informazioni su** in Human Resources.

4.  Selezionare l'ambiente per visualizzare i dettagli dell'ambiente.

5.  Selezionare **Gestisci soluzioni** nella barra di azione superiore. Una nuova finestra del browser viene visualizzata con l'**interfaccia di amministrazione di Dynamics 365** nel contesto dell'ambiente.

6.  Nell'elenco **Soluzione** selezionare **Ancora Dynamics 365 Human Resources**.

7.  Selezionare **Aggiorna** per applicare l'ultima soluzione.

## <a name="in-preview"></a>In anteprima

Le seguenti funzionalità di anteprima diventano disponibili a partire dal 3 febbraio 2020:

- **Funzionalità di anteprima di Congedi e assenza** - Per ulteriori informazioni, vedere [Funzionalità di anteprima di Congedo e assenza](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Funzionalità di anteprima di Gestione benefit** - Per ulteriori informazioni, inclusi problemi noti, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

## <a name="see-also"></a>Vedere anche

[Novità o modifiche in Human Resources](hr-admin-whats-new.md)</br>
[Panoramica della seconda ondata di rilascio di Dynamics 365 Human Resources 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)</br>
[Gestire le funzionalità](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]