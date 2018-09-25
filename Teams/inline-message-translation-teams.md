---
title: Usar tradução de mensagem embutida no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016833"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar tradução de mensagem embutida no Microsoft Teams 
=================================================

A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.

Tradução de mensagem embutida está sendo distribuída por padrão para sua organização. Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração usando o PowerShell. Atualmente, essa opção não está disponível no Microsoft Teams e Skype para centro de administração de negócios, mas estará em breve.

> [!NOTE]
>Esse lançamento está excluído das assinaturas do Office 365 em nossos ambientes Office 365 Government Community Cloud e Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Habilitar usando o PowerShell

É possível ativar o recurso de tradução de mensagem embutida usando a Diretiva de Mensagens. 

1. Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. A política leva alguns minutos para aplicar. Os usuários talvez seja necessário sair e entrar novamente para equipes.

## <a name="enable-by-using-the-teams-admin-center"></a>Ativar usando o Centro de administração do Teams

A opção para ativar o recurso de tradução de mensagem embutida usando o Centro de administração do Teams estará disponível em breve.

> [!NOTE]
>A conversão é estritamente do cliente e não capturou nenhum efeito sobre o conteúdo dos registros de conformidade. Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).