---
title: Designer formula per calcoli TDS
description: Questo articolo fornisce un esempio di come viene calcolata l'imposta dedotta all'origine (TDS) in base alla formula definita per ogni codice imposta TDS nel gruppo TDS associato alla transazione.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1196f7258c898a55f3f29ddce7457e6f527185d8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889863"
---
# <a name="formula-designer-for-tds-calculations"></a>Designer formula per calcoli TDS

[!include [banner](../includes/banner.md)]

Questo articolo fornisce un esempio di come viene calcolata l'imposta dedotta all'origine (TDS) in base alla formula definita per ogni codice imposta TDS. I codici imposta TDS sono definiti nel gruppo TDS associato alla transazione. Prima di progettare le formule TDS, completa la configurazione di base necessaria per TDS come descritto nei passaggi seguenti. 

- Configura i gruppi di componenti TDS utilizzando la pagina **Gruppi componenti ritenuta d'acconto**. 
- Imposta i componenti TDS e associa il gruppo di componenti TDS ai componenti TDS utilizzando la pagina **Componenti ritenuta d'acconto**. 
- Imposta i codici imposta TDS e associa i componenti TDS ai codici imposta utilizzando la pagina **Codici ritenuta d'acconto**. 
- Imposta i gruppi di imposte TDS utilizzando la pagina **Gruppi ritenute d'acconto**. Quindi associa i codici imposta TDS al gruppo di imposte e definisci la formula utilizzando la pagina **Designer formula**. 

**Formula di esempio**

In questo esempio, il gruppo TDS, Affitto, è associato a una fattura di acquisto creata per il fornitore A. L'importo della fattura è $100.000. Fai riferimento alla tabella seguente per visualizzare il calcolo della TDS per la fattura.

| Gruppo TDS                                                   | Codici imposta TDS associati al gruppo TDS | Valore              | Base imponibile (Designer formula) | Espressione di calcolo (Designer formula) | Imponibile | Importo TDS calcolato |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Affitto                                                         | TDS  (componente TDS-TDS)                | 10%                | Importo lordo                      |                                            | 100,000      | 10,000                 |
| Supplemento (componente TDS-Supplemento)                         | 10%                                     | Importo lordo escluso | +TDS                              |                   10000                    | 1.000        |                       |
| PE-Cess (componente TDS-PE-Cess)                            | 2%                                      | Importo lordo escluso | +TDS+Supplemento                    |                   11000                    | 220         |                       |
| SHE Cess (componente TDS-SHE Cess)                          | 1%                                      | Importo lordo escluso | +TDS+Supplemento                    |                   11000                    | 110         |                       |
| **TDS** **totale**  **calcolata** **per** **la** **fattura** | **11,330**                               |                    |                                   |                                            |             |                       |

Le voci del giustificativo vengono create come segue.

| Conto           | Dare  | Credito |
| ----------------- | ------ | ------ |
| Affitto              | 100,000 |        |
| Fornitore A          |        | 100,000 |
| Fornitore A          | 11,330  |        |
| TDS a debito       |        | 10,000  |
| Supplemento a debito |        | 1.000   |
| PE-Cess a debito   |        | 220    |
| SHE Cess a debito  |        | 110    |
