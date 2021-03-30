---
title: Abilitare l'autenticazione Azure Active Directory per l'accesso POS
description: Questo argomento spiega come configurare l'esperienza di accesso per il punto vendita (POS) di Microsoft Dynamics 365 Commerce in modo che utilizzi l'autenticazione Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 234d19bb6659af07c65763e05671742b9581e244
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206681"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Abilitare l'autenticazione Azure Active Directory per l'accesso al POS
[!include [banner](includes/banner.md)]


Molti clienti che usano Microsoft Dynamics 365 Commerce utilizzano anche altri servizi cloud Microsoft e potrebbero utilizzare Azure Active Directory (Azure AD) per gestire le credenziali dell'utente per tali servizi. In questi casi, i clienti potrebbero voler utilizzare lo stesso account Azure AD per tutte le applicazioni. Questo argomento spiega come configurare l'esperienza di accesso per il punto vendita (POS) di Commerce per utilizzare l'autenticazione Azure AD.

## <a name="configure-azure-ad-authentication"></a>Configurare l'autenticazione Azure AD

Per rendere Azure AD disponibile come metodo di autenticazione per l'accesso POS per un negozio, è necessario configurare le impostazioni del profilo di funzionalità del negozio e quindi applicare tali impostazioni ai client POS.

Per configurare un nuovo profilo di funzionalità, completare i passaggi seguenti:

1. Passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione POS** \> **Profili POS** \> **Profili funzionalità**.
1. Selezionare il profilo di funzionalità da modificare.
1. Nella scheda dettaglio **Funzioni**, nella sezione **Accesso personale POS**, modificare il valore del campo **Metodo di autenticazione di accesso** da **ID personale e password** in **Azure Active Directory**.

Per impostazione predefinita, tutti i profili di funzionalità utilizzano **ID personale e password** come metodo di autenticazione POS. Pertanto, è necessario modificare il valore del campo **Metodo di autenticazione di accesso** se si desidera utilizzare Azure AD. Ogni punto vendita al dettaglio collegato al profilo di funzionalità selezionato sarà interessato da questa modifica.

Per applicare le impostazioni ai client POS, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce** \> **Vendita al dettaglio e commercio IT** \> **Programmazione della distribuzione**.
1. Eseguire la programmazione della distribuzione **1070** (**Configurazione canale**).

> [!NOTE]
> L'autenticazione Azure AD richiede una connessione Internet. Non funziona quando il POS è in modalità offline.
> 
> Attualmente, la funzione **Sostituzione del responsabile** non supporta Azure AD come metodo di autenticazione. Sono richiesti un ID operatore e una password anche se Azure AD è configurato come metodo di autenticazione per l'accesso al POS.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Associare un account Azure AD a un lavoratore

Prima che un addetto del negozio possa usare un account Azure AD per accedere all'applicazione POS, l'account Azure AD deve essere associato a quel lavoratore.

Per associare un account Azure AD a un lavoratore, attenersi alla seguente procedura.

1. Passare a **Retail e Commerce** \> **Dipendenti** \> **Lavoratori**.
1. Aprire la pagina dei dettagli per un lavoratore.
1. Nel riquadro azioni, nella scheda **Commerce**, nel gruppo **Identità esterna**, selezionare **Associa identità esistente**.
1. Nella finestra di dialogo **Usa identità esterna esistente**, selezionare **Cerca tramite e-mail**, inserire un indirizzo e-mail Azure AD, quindi selezionare **Cerca**.
1. Selezionare l'account Azure AD che viene restituito, quindi selezionare **OK**.

I campi **Alias**, **UPN** e **Identificatore secondario esterno** nella scheda **Commerce** della pagina dei dettagli del lavoratore verranno compilati.

> [!NOTE]
> Dopo l'aggiornamento di un record lavoratore, ad esempio se viene associato un nuovo account Azure AD, la password viene modificata o la rubrica di un dipendente viene aggiornata, si consiglia di eseguire la pianificazione di distribuzione **1060** (**Personale**) per sincronizzare le informazioni più recenti sul personale con il canale. In questo modo, l'applicazione POS può recuperare i dati corretti per l'autenticazione dell'utente e il controllo delle autorizzazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare la funzionalità di accesso esteso per MPOS e Cloud POS](extended-logon.md)

[Creare un profilo funzionalità di vendita al dettaglio](retail-functionality-profile.md)

[ Configurare un lavoratore](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)


[!INCLUDE[footer-include](../includes/footer-banner.md)]