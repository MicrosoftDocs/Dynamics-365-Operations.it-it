---
title: Crea articoli prestito
description: Gli articoli prestito sono record che consentono di tenere traccia degli articoli fisici, ad esempio telefoni o computer, che la società presta ai lavoratori.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 75b2f17eb41ead7422276f72429eb6ede2ef4759
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178581"
---
# <a name="create-loan-items"></a>Crea articoli prestito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Gli articoli prestito sono record che consentono di tenere traccia degli articoli fisici, ad esempio telefoni o computer, che la società presta ai lavoratori. Ogni articolo fisico deve avere un articolo prestito corrispondente. Per ciascun record articolo prestito dovranno essere descritti la tipologia, il responsabile del prestito e la durata in giorni consentita per il prestito. È possibile creare più articoli prestito, ad esempio chiavi, schede di accesso o divise, contemporaneamente. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-loan-types"></a>Creare Tipi di prestito
1. Andare a Risorse umane > Lavoratori > Articoli prestito > Tipi di prestito.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Tipo di prestito.
4. Nel campo Descrizione digitare un valore.
5. Immettere il numero di giorni in cui gli articoli assegnati a questo tipo di prestito possono essere scaduti. 
6. Fare clic su Salva.
7. Chiudere la pagina.
8. Aggiorna la pagina.

## <a name="create-loan-items"></a>Creare articoli prestito
1. Andare a Risorse umane > Lavoratori > Articoli prestito > Articoli prestito.
2. Fare clic su Crea articoli prestito.
3. Nel campo Qtà immettere un numero.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di prestito fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Immettere il numero di giorni per cui l'articolo può rimanere in prestito.
    * Il valore predefinito per il campo Prevista restituzione nella pagina Attrezzature concesse in prestito viene calcolato in base alla data corrente a cui viene aggiunto questo numero.  
9. Nel campo Incaricato fare clic sul pulsante a discesa per aprire la ricerca.
10. Fare clic su Seleziona.
11. Nel campo Valore iniziale immettere un numero.
12. Nel campo Intervallo immettere un numero.
13. Digitare un valore nel campo Formato.
    * Se ad esempio il numero iniziale per un articolo in prestito è 10, immettere due simboli di numero nel campo Formato.  
14. Fare clic su OK.
15. Aggiorna la pagina.
