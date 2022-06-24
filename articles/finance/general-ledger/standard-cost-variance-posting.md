---
title: Registrazione dello scostamento costo standard
description: Questo articolo fornisce informazioni sulla configurazione dei profili di registrazione per la determinazione costi standard.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: e7b2d04f32b75dbd1354b3ef74a41ea1b6469c8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894879"
---
# <a name="standard-cost-variance-posting"></a>Registrazione dello scostamento costo standard

Quando utilizzi il costo standard per uno o più prodotti nella tua organizzazione, devi configurare i [prerequisiti per la determinazione dei costi standard](/supply-chain/cost-management/prerequisites-standard-costs.md). In questo articolo vengono illustrati i conti di registrazione necessari per il passaggio 3 dei prerequisiti "Assegnare conti CoGe a registrazioni articoli correlate a scostamenti dei costi standard".

Possono verificarsi diversi tipi di scostamenti per gli ordini fornitore e di produzione. Per esempi di scostamenti di produzione, vedi [Origini comuni di scostamenti di produzione](/supply-chain/cost-management/common-sources-of-production-variances.md). Gli scostamenti del prezzo dell'ordine fornitore si verificano quando si utilizza il costo standard per un articolo acquistato ed esiste una differenza tra il costo standard del prodotto e l'importo fatturato nell'ordine fornitore.

## <a name="sample-posting-profile-configuration"></a>Esempio di configurazione del profilo di registrazione

La tabella seguente mostra esempi dei tipi di registrazione predefiniti. Include i conti principali e le descrizioni di esempio.

- La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, la transazione può registrare addebiti o crediti.
- La colonna "Conto di compensazione" indica che il tipo di registrazione è un conto di compensazione. In altre parole, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.
- La colonna "P/F" indica il tipo di registrazione. "P" rappresenta la registrazione fisica e "F" rappresenta la registrazione finanziaria.
- La colonna "Segui" indica se il conto principale per un tipo di registrazione specifico è in genere uguale al conto principale per un altro tipo di registrazione. In particolare, indica il tipo di registrazione generalmente utilizzato.

> [!NOTE]
> I conti principali e i nomi di conti principali nella tabella sono suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | P/F | Segui | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Scostamento prezzi di acquisto | 510310 | Scostamento prezzi di acquisto | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando c'è uno scostamento tra il prezzo di acquisto e il costo standard su un ordine fornitore. |
| Rivalutazione costo di magazzino | 510330 | Rivalutazione costo di magazzino | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando viene attivata una nuova versione di determinazione dei costi per una voce di costo standard per rivalutare le scorte disponibili. |
| Scostamento modifiche costo | 510320 | Scostamento modifiche costo | Spese | O | Numero | V | Non applicabile | Questo account viene utilizzato quando c'è una differenza nei costi standard tra i siti o quando un articolo viene restituito e c'è una modifica tra il costo standard originale e il costo standard corrente per un prodotto. |
| Scostamento dimensioni lotto produzione | 510370 | Scostamento dimensioni lotto produzione | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando esistono differenze tra la base di calcolo della distinta base (DBA) e la quantità effettiva per il calcolo del costo dell'ordine di produzione. |
| Scostamento prezzi di produzione | 510340 | Scostamento prezzi di produzione | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando esistono differenze di prezzo tra il costo stimato e il costo effettivo per un ordine di produzione. |
| Scostamento quantità produzione | 510350 | Scostamento quantità produzione | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando esistono differenze di quantitò tra il costo stimato e i costi effettivi per un ordine di produzione. |
| Scostamento sostitutivo produzione | 510360 | Scostamento sostitutivo produzione | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando si verifica un consumo imprevisto in un ordine di produzione. |
| Scostamento arrotondamento | 618160 | Differenza arrotondamento | Spese | O | Numero | V | Non applicabile | Questo conto viene utilizzato quando è presente una differenza di arrotondamento quando i costi di produzione sono calcolati dai costi standard. |
