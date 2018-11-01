---
title: Usar tradução de mensagem embutida no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
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
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: afc415ad4d0c2ed013eaf5f68a72418e66734ff0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2018
ms.locfileid: "25898115"
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

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a>Habilitar usando o Microsoft Teams & Skype para Business Admin Center

No **Microsoft equipes & Skype para Business Admin Center**, selecione **Messaging Policies** na barra de ferramentas esquerda, em seguida, tanto criar uma nova política ou editar uma política existente e definir a opção de **Permitir que os usuários para traduzir mensagens** de **em **.

> [!NOTE]
>Conversão é feita pelo serviço e entregue ao cliente com nenhum efeito sobre o conteúdo capturado nos registros de conformidade. Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).