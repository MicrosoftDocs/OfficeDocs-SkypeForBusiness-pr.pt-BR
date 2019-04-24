---
title: Usar tradução de mensagem embutida no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58e6fb04dd015e939125b75d604fe9692a32c0e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222321"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar tradução de mensagem embutida no Microsoft Teams 
=================================================

A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.

A tradução de mensagem embutida está sendo lançada por padrão para sua organização. Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração.

> [!NOTE]
>Essa distribuição é excluída da assinaturas do Office 365 em nossos ambientes de nuvem de comunidade do Office 365 governamental e Alemanha do Office 365.

## <a name="enable-by-using-powershell"></a>Habilitar usando PowerShell

Você pode ativar o recurso de conversão de mensagem embutida usando a diretiva de mensagens.

1. Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. A política leva alguns minutos para aplicar. Os usuários talvez seja necessário sair e entrar novamente para equipes.

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>Habilitar usando o Centro de administração do Microsoft Teams

No **Centro de administração de equipes da Microsoft**, selecione **Messaging Policies** na barra de ferramentas esquerda, em seguida, tanto criar uma nova política ou editar uma política existente e defina a opção de **Permitir que os usuários para traduzir mensagens** para **ativado**.

> [!NOTE]
>Conversão é feita pelo serviço e entregue ao cliente com nenhum efeito sobre o conteúdo capturado nos registros de conformidade. Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).