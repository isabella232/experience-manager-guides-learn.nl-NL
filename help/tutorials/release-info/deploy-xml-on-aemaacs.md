---
title: Toevoegen [!DNL AEM Guides] aan uw [!DNL AEM as a Cloud Service] milieu
description: Meer informatie over toevoegen [!DNL AEM Guides] aan uw [!DNL AEM as a Cloud Service] milieu
exl-id: a1e020c2-360c-4d71-b5fd-8179d9ceacda
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# [!DNL AEM Guides] as a Cloud Service implementatie

Meer informatie over toevoegen [!DNL Guides] aan uw [!DNL AEM as a Cloud Service] milieu.

## Handmatige implementatie via de vastlegging in Cloud Manager

Als u [!DNL AEM Guides] as a Cloud Service vóór 29 maart 2022, volg deze plaatsingsinstructies:

* Als u vers start, kunt u de code vervangen die automatisch wordt gegenereerd door [!UICONTROL Cloud Manager] met de code uit de onderstaande repo die al een XML-insteekmodule heeft: https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Als u al aanpassingen hebt aangemeld in [!UICONTROL Cloud Manager] git repo, kunt u naar het onderstaande repo verwijzen voor instructies over het toevoegen van een XML-insteekmodule in uw bestaande code: https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Implementatie via Cloud Manager

Als u een klant bent die [!DNL AEM Guides] as a Cloud Service op of na 29-03-2022 volgt u deze instructies om [!DNL Guides] aan uw [!DNL AEM as a Cloud Service] milieu:

1. Aanmelden bij [!UICONTROL Cloud Manager].

1. Bewerk het programma waarvoor u wilt configureren [!DNL AEM Guides].

1. Overschakelen op **[!UICONTROL Solutions and Add-ons]** tab.

1. In de **[!UICONTROL Solutions and Add-ons]** tabel, klik op **[!UICONTROL Assets]**.

1. Selecteren **[!UICONTROL Guides]** en selecteert u **[!UICONTROL Save]**.

U hebt met succes uw programma voor automatische levering van AEM oplossing van Gidsen gevormd.

![Oplossing voor AEM hulplijnen configureren](assets/addon-configuration.png)

>[!NOTE]
>
>Om te installeren [!DNL AEM Guides] op elk milieu in het kader van het geïntegreerde programma moet u de pijpleiding voor het milieu in werking stellen . Er is geen aanvullende configuratie vereist in uw CM-it-codebase voor installatie [!DNL AEM Guides].
