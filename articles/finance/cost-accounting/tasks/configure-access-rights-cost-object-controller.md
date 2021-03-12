---
title: Configurare i diritti di accesso per un controller oggetto di costo
description: Utilizzare questa procedura per configurare i diritti di accesso per un controller oggetto di costo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88d6208e867bd322ddfc4e599856b1905fa8e19b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969380"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Configurare i diritti di accesso per un controller oggetto di costo

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per configurare i diritti di accesso per un controller oggetto di costo. Questa registrazione utilizza i dati dimostrativi della società USP2.


## <a name="assign-the-cost-object-controller-role"></a>Assegnare il ruolo di controller oggetto di costo
1. Andare a Amministrazione sistema > Utenti > Utenti.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo Nome utente in base al valore "alicia".
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Assegna ruoli.
5. Nell'elenco trovare e selezionare il record desiderato.
6. Fare clic su OK.

## <a name="enable-access-list-security"></a>Abilitare la sicurezza dell'elenco di accessi
1. Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare Organizzazione.  
3. Fare clic su Modifica.
4. Selezionare Sì nel campo Gerarchia elenco accessi.
5. Fare clic su Visualizza gerarchia.

## <a name="assign-access-rights-to-user"></a>Assegnare i diritti di accesso all'utente
1. Fare clic su Nuovo.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo ID utente, immettere o selezionare un valore.
    * Selezionare Amministratore.  
4. Nella struttura selezionare "Organization\CEO\CFO\FIM".
5. Fare clic su Nuovo.
6. Nell'elenco contrassegnare la riga selezionata.
7. Nel campo ID utente, immettere o selezionare un valore.
    * Selezionare Alicia.  
8. Fare clic su Salva.

## <a name="enable-access-rights-in-cost-accounting"></a>Abilitare i diritti di accesso nella contabilità industriale
1. Andare a Contabilità industriale > Impostazioni > Parametri.
2. Fare clic sulla scheda Generale.
3. Selezionare Sì nel campo Abilita accesso in visualizzazione per membri di dimensione oggetto di costo.
4. Fare clic su Salva.
5. Chiudere la pagina.
6. Andare a Contabilità industriale > Impostazioni > Configurazione area di lavoro controllo costi.
7. Fare clic su Modifica.
8. Selezionare Sì nel campo Pubblicato.
    * Se si seleziona Sì, gli utenti assegnati a uno di questi quattro ruoli possono visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile, addetto alla contabilità e controller oggetto di costo. Se si seleziona No, solo un utente assegnato a uno di questi ruoli può visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile e addetto alla contabilità.    
9. Fare clic su Salva.

