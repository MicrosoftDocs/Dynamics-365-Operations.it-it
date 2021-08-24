---
title: Configurare le competenze
description: Puoi tener traccia delle competenze del lavoratore in Dynamics 365 Human Resources. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a8025dd4000a3678e7f7eb7faebfa45852f0054570a2948dadbc21913c63f578
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732155"
---
# <a name="configure-skills"></a>Configurare le competenze

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puoi tener traccia delle competenze del lavoratore in Dynamics 365 Human Resources. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.

Esempi di competenze di cui è possibile tenere traccia includono:

- Supervisione: capacità di supervisionare il lavoro svolto da altre persone.
- Leadership: capacità di guidare dipendenti e reparti di un'azienda.
- Pianificazione: capacità di adattarsi a nuovi scenari, di formulare dichiarazioni di visioni e di vedere oltre queste.
- HTML: capacità di scrivere codice HTML.

Se non hai già impostato tipi di competenze e modelli di valutazione, dovrai aggiungerne alcuni prima di creare competenze.

Le seguenti persone possono inserire le competenze per un lavoratore:

- I lavoratori possono inserire autonomamente le competenze nel self-service dei dipendenti. Queste competenze richiedono l'approvazione del manager.
- I manager possono inserire le competenze per i propri lavoratori. Puoi creare un flusso di lavoro che approva automaticamente queste competenze.

## <a name="create-a-skill-type"></a>Creare un tipo di competenza

I tipi di competenze sono categorie in cui rientrano le competenze individuali, come Amministrazione o Vendite.

1. Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.

2. In **Configurazione delle competenze**, seleziona **Tipi di competenze**.

3. Selezionare **Nuovo**.

4. Completa i seguenti campi:

   - **Tipo di competenza**: immetti un nome univoco per il tipo di competenza.
   - **Descrizione**: immetti una descrizione per il tipo di competenza.

5. Selezionare **Salva**.

## <a name="create-a-rating-model"></a>Creare un modello di valutazione

La valutazione dei modelli contribuisce a valutare l'effettivo livello di competenza di una persona, il livello per cui deve lavorare o il livello di competenza necessario per una posizione lavorativa. Ogni livello in un modello di valutazione viene assegnato a un fattore.

1. Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.

2. In **Configurazione competenza**, seleziona **Modelli di valutazione**.

3. Selezionare **Nuovo**.

4. Completa i seguenti campi:

   - **Valutazione**: immetti un nome per il modello di valutazione, ad esempio **Competenze**.
   - **Descrizione**: immetti una descrizione per il modello di valutazione, ad esempio **Valutazioni delle competenze**.

5. Nella sezione **Livelli**, seleziona **Nuovo**. Per ogni livello che desideri aggiungere, completa i seguenti campi:

   - **Livello**: immetti un nome per il livello.
   - **Descrizione**: immetti una descrizione per il livello.
   - **Fattore**: immetti un valore di fattore compreso tra 0 e 9. I fattori contribuiscono a normalizzare i punteggi di competenze che utilizzano modelli di valutazione diversi. Ogni livello deve avere un fattore univoco. Livelli con valori del fattore maggiori hanno più peso in modello di valutazione.

   Continua ad aggiungere livelli se necessario. È possibile immettere fino a 10 livelli per ogni modello di valutazione.

6. Selezionare **Salva**.

## <a name="create-a-skill"></a>Creare una competenza

Prima di poter assegnare una competenza o creare una ricerca nel mapping delle competenze o un profilo competenze, è necessario immettere informazioni sulle competenze nella pagina **Competenze**. Per ogni competenza, è possibile selezionare un tipo e un modello di valutazione.

1. Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.

2. In **Configurazione delle competenze**, seleziona **Competenze**.

3. Selezionare **Nuovo**.

4. Completa i seguenti campi:

   - **Competenza**: immetti un nome univoco per la competenza.
   - **Descrizione**: immetti una descrizione per la competenza.
   - **Valutazione**: seleziona il modello di valutazione che vuoi utilizzare per la competenza.
   - **Tipo di competenza**: seleziona dall'elenco dei tipi di competenza.

5. Selezionare **Salva**.

## <a name="see-also"></a>Vedere anche

[Immettere le competenze](hr-develop-enter-skills.md)<br>
[Mappare le competenze](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]