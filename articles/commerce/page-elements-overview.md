---
title: Glossario del modello di pagina
description: In questo argomento vengono descritti i vari elementi utilizzati nelle pagine di un sito di Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6e2e2abd8fc712e7973fd807a8236d5d6391ff05
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804627"
---
# <a name="page-model-glossary"></a>Glossario del modello di pagina


[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i vari elementi utilizzati nelle pagine di un sito di Microsoft Dynamics 365 Commerce.

## <a name="page-element-definitions"></a>Definizioni degli elementi di pagina

Nella tabella seguente viene fornito un riepilogo dei termini che è necessario conoscere quando si modifica l'aspetto e il contenuto del sito. Per descrizioni e procedure più dettagliate, seguire i collegamenti.

| Termine | Descrizione e note |
|------|-----------------------|
| [Modulo](work-with-modules.md) | <p>**Definizione:** i moduli sono blocchi predefiniti che possono essere creati e costituiscono lo scheletro di una pagina Web. Alcuni esempi sono i moduli Intestazione, Hero e Sequenza.</p><p>**Selezione:** i moduli distribuiti possono essere selezionati e configurati in varie fasi del flusso di lavoro di creazione di siti, come le fasi di creazione di modelli, layout, pagine e frammenti.</p><p>**Modifica:** i moduli personalizzati sono creati in codice utilizzando il Software Development Kit (SDK). Vengono quindi caricati nel sito, dove diventano disponibili per la selezione.</p> |
| Proprietà del modulo | <p>**Definizione:** le proprietà del modulo sono specifiche impostazioni definite dal modulo. Possono essere modificate negli strumenti di creazione di e-Commerce. Ad esempio, le proprietà del modulo sono utilizzate per impostare l'intestazione e l'immagine di sfondo di un modulo Banner.</p><p>**Configurazione:** le proprietà del modulo sono selezionate e configurate nel riquadro delle proprietà visualizzato negli ambienti di creazione (editor) per modelli, pagine, frammenti e impostazioni di app.</p> |
| [Modello](templates-layouts-overview.md) | <p>**Definizione:** i modelli determinano le opzioni e le combinazioni di moduli che devono essere utilizzate per una categoria di pagine (ad esempio pagine di marketing, pagine categoria e pagine prodotto).</p><p>**Selezione:** i modelli possono essere selezionati durante i flussi di lavoro di creazione di layout o pagine.</p><p>**Modifica:** i modelli sono creati nell'editor di modelli. Non è necessario alcun codice per crearli o modificarli.</p> |
| [Layout](templates-layouts-overview.md) | <p>**Definizione:** i layout definiscono la selezione e la posizione finale dei moduli a partire dal set di opzioni del modello padre. Un layout può essere configurato per una singola pagina (*layout personalizzato*), oppure può essere condiviso da più pagine (*layout preimpostato*).</p><p>**Selezione:** i layout possono essere selezionati durante la creazione di una nuova pagina o quando un layout differente è necessario per una pagina esistente.</p><p>**Modifica:** i layout sono creati nell'editor di layout. Non è necessario alcun codice per crearli o modificarli.</p> |
| [Istanza di pagina](modify-existing-page.md) | <p>**Definizione:** le istanze di pagina determinano il contenuto localizzato finale di una singola pagina. Questo contenuto è derivato dai valori delle proprietà del modulo.</p><p>**Selezione:** le pagine vengono selezionate quando si assegnano URL.</p><p>**Modifica:** le pagine vengono modificate nell'editor di pagine. Non è necessario alcun codice per crearli o modificarli.</p> |
| [Tema](select-site-theme.md) | <p>**Definizione:** i temi determinano definiscono il foglio di stile CSS e determinano l'aspetto dei moduli di cui viene eseguito il rendering in una pagina.</p><p>**Selezione:** dopo il caricamento nel sito utilizzando Microsoft Dynamics Lifecycle Services, un tema può essere selezionato come proprietà del modulo contenitore pagina.</p><p>**Modifica:** i temi vengono correntemente creati e modificati mediante il kit SDK. Sono quindi caricati sul sito utilizzando LCS.</p> |
| [Frammento](work-with-fragments.md) | <p>**Definizione:** i frammenti sono moduli totalmente configurati che hanno contenuto localizzato e che possono essere riutilizzati e aggiornati centralmente in più pagine. Ad esempio, un frammento creato a partire da un modulo Intestazione può essere utilizzato in tutti i modelli e in tutte le pagine del sito e aggiornato centralmente in una posizione.</p><p>**Selezione:** i frammenti possono essere selezionati ovunque sia possibile selezionare dei moduli. Possono sostituire un modulo per aumentare l'efficienza mediante una creazione riutilizzabile e centralizzata.</p><p>**Modifica:** i frammenti sono modificati nell'editor di frammenti. Non è necessario alcun codice per crearli o modificarli.</p> |
| [URL](create-page-URL.md) | <p>**Definizione:** gli URL sono indirizzi che puntano a pagine Web o altri URL.</p><p>**Selezione:** gli URL sono selezionati se sono necessari collegamenti tra pagine.</p><p>**Modifica:** gli URL sono modificati nell'editor di URL. Non è necessario alcun codice per crearli o modificarli.</p> |
| Asset | <p>**Definizione:** gli asset sono file binari con un'estensione, ad esempio .jpg .docx, .pdf, o .mpg.</p><p>**Selezione:** gli asset sono selezionati come proprietà per i moduli che li necessitano.</p><p>**Modifica:** gli asset sono caricati e i metadati associati sono modificati nello strumento di gestione di asset.</p> |

## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di aggiungere contenuti](add-manage-content.md)

[Stato e ciclo di vita documento](document-states-overview.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)

[Abilitare e utilizzare la condivisione multicanale](cross-channel-sharing.md)

[Utilizzare i moduli](work-with-modules.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Panoramica modelli e layout](templates-layouts-overview.md)

[Personalizzare la navigazione del sito](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]