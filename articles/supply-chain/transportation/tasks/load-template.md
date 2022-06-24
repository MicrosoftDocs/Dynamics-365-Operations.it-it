---
title: Modelli di carico
description: In questo articolo viene descritto come impostare i modelli di carico e come associare un modello di carico a un nuovo carico.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 47b4925c528b64b835ce3e88659ee6ab0572eb2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844182"
---
# <a name="load-templates"></a>Modelli di carico

[!include [banner](../../includes/banner.md)]

Quando si crea un nuovo carico, è possibile assegnare un modello di carico. Il modello di carico contiene informazioni sull'attrezzatura e sulle misure quali altezza, larghezza, profondità e volume del carico.

In questo articolo viene descritto come impostare i modelli di carico e come associare un modello di carico a un nuovo carico.

## <a name="set-up-a-load-template"></a>Impostare un modello di carico

1. Andare a **Gestione trasporti \> Impostazione \> Allestimento del carico \> Modello carico**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un nuovo modello oppure **Modifica** per modificare un modello esistente.
1. Nella riga del modello nuovo o esistente, impostare i seguenti campi:

    - **ID modello di carico** – Immettere un identificatore (ID) univoco per il modello di carico.
    - **Attrezzatura** - Selezionare l'attrezzatura da utilizzare per spedire il carico.
    - **Altezza carico**, **Larghezza carico** e **Profondità carico** - Immettere le dimensioni del carico.
    - **Volume carico massimo consentito** e **Peso carico massimo consentito** - Immettere il volume e il peso massimi consentiti del carico.
    - **Peso lordo massimo consentito** - Immettere il peso lordo massimo consentito del carico. Il peso lordo del carico include la tara e il peso di carico.
    - **Numero massimo di colli consentito** - Immettere il numero massimo di pezzi di trasporto che il carico può contenere.
    - **Impila carico su piano** - Selezionare questa casella di controllo per utilizzare il caricamento di reparto. In uno scenario di caricamento di reparto le scatole vengono impilate dal pavimento al soffitto, da parete a parete all'interno del contenitore per ottimizzare la capacità.

1. Nel riquadro azioni selezionare **Salva**.

## <a name="associate-a-load-template-with-a-new-load"></a>Associare un modello di carico a un nuovo carico

1. Andare a **Gestione trasporto \> Pianificazione \> Workbench pianificazione carico**.
1. Nella parte superiore della pagina, selezionare una delle seguenti schede, a seconda del tipo di documento di origine per il quale si sta creando un carico: **Spedizioni**, **Righe vendita**, **Righe trasferimento** o **Righe ordine fornitore**. 
1. Selezionare il documento specifico per cui pianificare il carico.
1. Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**.
1. Nella finestra di dialogo **Modello carico**,nel campo **ID modello di carico** selezionare il modello da applicare.
1. Selezionare **OK** per applicare il modello.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]