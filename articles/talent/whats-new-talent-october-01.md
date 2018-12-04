---
title: "Novità o modifiche in Dynamics 365 for Talent Core HR (1 ottobre 2018)"
description: "Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: c5d4fb53939d88fcb1bd83d70bc361ed9879f298
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (1 ottobre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.1035.0**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Disattivare la convalida di pagamenti elettronici

La convalida delle informazioni di pagamento elettronico si verifica quando si impostano gli esborsi per il deposito diretto tramite l'area di lavoro **Dipendente self-service** (ESS) o direttamente nel modulo del dipendente. Questa opzione offre la flessibilità di rimuovere tale convalida se non sono necessarie le verifiche di convalida per gli importi e i valori delle rimanenze. Questa funzionalità è utile se si effettua l'integrazione con un sistema di retribuzione esterno che prevede requisiti diversi.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Responsabile self-service - Aggiungere obiettivi per i membri del team tramite il riquadro degli obiettivi delle prestazioni del team

Nelle versioni precedenti i responsabili possono aggiungere gli obiettivi ai dipendenti singolarmente tramite gli obiettivi delle prestazioni associati a ciascun dipendente. Con questo aggiornamento, i responsabili possono accedere al riquadro **Obiettivi prestazioni team** e creare nuovi obiettivi selezionando uno dei propri diretti subalterni.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Responsabile self-service - Aggiungere revisioni per i membri del team tramite il riquadro Revisioni prestazioni team

Nelle versioni precedenti i responsabili possono aggiungere le revisioni ai dipendenti singolarmente tramite le revisioni associate a ciascun dipendente. Con questo aggiornamento, i responsabili possono accedere al riquadro **Revisioni prestazioni team** e creare nuove revisioni selezionando uno dei propri diretti subalterni.

## <a name="configure-proration-options-by-leave-plan"></a>Configurare le opzioni di ripartizione in base al piano di congedo

Le organizzazioni attribuiscono permessi in modo diverso in base a quando i dipendenti entrano e lasciano la società. Per alcune organizzazioni, i dipendenti ricevono l'allocazione completa alla data di inizio mentre altri ripartiscono l'attribuzione. In questa versione sono presenti nuove opzioni che consentono di scegliere come ripartire le attribuzioni per chi entra e chi lascia un'organizzazione. Le opzioni sono: Ripartito, Attribuzione per competenza completa e Nessuna attribuzione per competenza.

## <a name="other-changes"></a>Altre modifiche

-   Entità dipendente aggiornata - Il titolo **Personale** può ora essere aggiornato utilizzando il componente aggiuntivo e la gestione dei dati di Excel.

-   Modifica di sicurezza per consentire la rimozione dei pulsanti **Elimina** e **Disattiva** nel self-service del dipendente per le informazioni sul pagamento.

## <a name="known-issue"></a>Problema noto

-   **Problema:** quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** appaiono disattivati. **Soluzione alternativa:** prima di aprire la pagina degli allegati, assicurarsi che i riquadri Dettaglio informazioni nella pagina **Lavoratore** siano chiusi. Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli **Allegati** saranno abilitati. Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.

