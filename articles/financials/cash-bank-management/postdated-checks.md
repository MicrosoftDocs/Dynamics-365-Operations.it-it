---
title: Assegni postdatati
description: "Questo articolo fornisce informazioni sul supporto per gli assegni postdatati in Microsoft Dynamics 365 for Finance and Operations. Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura. Di conseguenza, l'assegno non può più essere incassato fino alla data specificata."
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 8fd721dc3166dcd981b749c673d3c625b4e5ae36
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="postdated-checks"></a>Assegni postdatati

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sul supporto per gli assegni postdatati in Microsoft Dynamics 365 for Finance and Operations. Gli assegni postdatati sono assegni emessi per effettuare e ricevere pagamenti in una data futura. Di conseguenza, l'assegno non può più essere incassato fino alla data specificata.

Microsoft Dynamics 365 for Finance and Operations supporta il ciclo di gestione completo per assegni postdatati sia in Contabilità clienti che in Contabilità fornitori, come illustrato nella seguente tabella.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impostare gli assegni postdatati</td>
<td>È necessario impostare un nuovo metodo di pagamento e specificare la procedura di pagamento per i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</td>
</tr>
<tr class="even">
<td>Registrare un assegno postdatato per un fornitore</td>
<td>Registrare i dettagli di un assegno postdatato da emettere a favore di un fornitore. Quando il pagamento viene registrato, la passività fornitore viene riconosciuta, ma il conto bancario non è ancora accreditato. A questo scopo viene utilizzato invece un conto di compensazione. </td>
</tr>
<tr class="odd">
<td>Registrare un assegno postdatato di un cliente</td>
<td>Registrare i dettagli di un assegno postdatato ricevuto da un cliente. Quando il pagamento viene registrato, la contabilità cliente viene accreditata, ma il conto bancario non è ancora addebitato. A questo scopo viene utilizzato invece un conto di compensazione.</td>
</tr>
<tr class="even">
<td>Registrare un assegno postdatato in sostituzione per un cliente o un fornitore</td>
<td>
Se l'assegno originale per un fornitore o da un cliente viene perso o danneggiato, è possibile emettere un assegno postdatato in sostituzione. Quando si registrano i dettagli dell'assegno, fornire un riferimento all'assegno originale e indicare che il nuovo assegno è in sostituzione di quello originale. È inoltre possibile registrare l'assegno in sostituzione.</td>
</tr>
<tr class="odd">
<td>Trasferire un assegno postdatato del cliente a un fornitore</td>
<td>Quando si riceve un assegno postdatato da un cliente, è possibile trasferirlo a un fornitore come pagamento.</td>
</tr>
<tr class="even">
<td>Liquidare un assegno postdatato per un cliente o un fornitore</td>
<td>Liquidare un assegno postdatato registrato in un conto provvisorio per un cliente o un fornitore nel momento in cui diventa valido. Se l'assegno viene liquidato, la banca viene addebitata o accreditata in base al conto di compensazione utilizzato in precedenza.</td>
</tr>
<tr class="odd">
<td>Annullare un assegno postdatato per un fornitore</td>
<td>È possibile annullare gli assegni postdatati registrati nelle seguenti situazioni: - L'assegno viene restituito dalla banca.
- L'assegno è applicato a una fattura non corretta.
- Un pagamento in contanti viene effettuato a fronte dell'assegno.
  </td>
  </tr>
  <tr class="even">
  <td>Bloccare il pagamento di un assegno postdatato</td>
  <td>È possibile bloccare il pagamento di un assegno postdatato emesso a un fornitore per diversi motivi quali, ad esempio, copertura insufficiente, modifica delle condizioni del contratto con il fornitore, fornitura di merci difettose da parte del fornitore o merce resa al fornitore. È possibile bloccare il pagamento solo degli assegni che non sono stati annullati.</td>
  </tr>
  </tbody>
  </table>



Per ulteriori informazioni, vedere i seguenti argomenti:

[Impostare gli assegni postdatati](tasks/set-up-postdated-checks.md)

[Registrare un assegno postdatato per un cliente](tasks/register-post-postdated-check-customer.md)

[Liquidare un assegno postdatato di un cliente](tasks/settle-postdated-check-customer.md)

[Registrare un assegno postdatato per un fornitore](tasks/register-post-postdated-check-vendor.md) 

[Liquidare un assegno postdatato per un fornitore](tasks/settle-postdated-check-vendor.md)




