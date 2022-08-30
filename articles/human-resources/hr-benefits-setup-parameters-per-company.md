---
title: Configurare i parametri di gestione dei benefit per azienda
description: Questo articolo descrive come configurare i parametri per la gestione dei benefici per azienda in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 8/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f3f8625a8ebbe6812d2f051649ff2a608ed4b54
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323900"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurare i parametri di gestione dei benefit per azienda


Per ogni organizzazione che offre benefit, è necessario configurare le impostazioni per i messaggi di posta elettronica di conferma dei benefit.

## <a name="configure-confirmation-email-settings"></a>Configurare impostazioni di posta elettronica per la conferma

1. Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.

2. Nella scheda **Gestione benefit** specificare i valori per i seguenti campi: 

   | Campo | Descrizione |
   | --- | --- |
   | **Invia messaggio di posta elettronica di conferma** | Quando questa funzione è attiva, un'e-mail di conferma sarà inviata ai dipendenti quando effettuano il check-out dall'esperienza di iscrizione ai benefici in **Self-service dipendente**. |
   | **Modello di messaggio di posta elettronica di conferma** | Selezionare il modello di posta elettronica dell'organizzazione da utilizzare quando si invia la conferma di registrazione. Se non si seleziona un modello, verrà inviata il seguente messaggio di posta elettronica generico:<br><br>%EmployeeFirstName%,<br><br>Congratulazioni. L'iscrizione ai benefit è stata completata.<br><br>Grazie,<br>Benefit di <Nome azienda/Organizzazione>. |
   | **Indirizzo mittente di posta elettronica predefinito** | L'indirizzo di posta elettronica da utilizzare quando si invia il messaggio di posta elettronica di conferma. |

3. Selezionare **Salva**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
