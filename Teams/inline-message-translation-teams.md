---
title: Usar conversão de mensagem embutida no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855817"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar conversão de mensagem embutida no Microsoft Teams 
=================================================

Tradução de mensagem embutida é um novo recurso de Teams da Microsoft que permite que os usuários automaticamente traduzir mensagens de equipes para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por suas configurações de idioma pessoal para o Office 365.

Tradução de mensagem embutida está sendo distribuída por padrão para sua organização. Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração usando o PowerShell. Atualmente, essa opção não está disponível no Microsoft Teams e Skype para centro de administração de negócios, mas estará em breve.

> [!NOTE]
>Essa distribuição é excluída da assinaturas do Office 365 em nossos ambientes de nuvem de comunidade do Office 365 governamental e Alemanha do Office 365. 

## <a name="enable-by-using-powershell"></a>Habilitar usando PowerShell

Você pode ativar o recurso de conversão de mensagem embutida usando a diretiva de mensagens. 

1. Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. A política leva alguns minutos para aplicar. Os usuários talvez seja necessário sair e entrar novamente para equipes.

## <a name="enable-by-using-the-teams-admin-center"></a>Habilitar usando o Centro de administração de equipes

A opção para ativar o recurso de conversão de mensagem embutida usando o Centro de administração de equipes estarão disponíveis em breve.

> [!NOTE]
>A conversão é estritamente do cliente e não capturou nenhum efeito sobre o conteúdo dos registros de conformidade. Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).