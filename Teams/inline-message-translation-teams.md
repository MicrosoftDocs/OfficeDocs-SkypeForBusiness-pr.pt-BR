---
title: Usar tradução de mensagem embutida no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882904"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar tradução de mensagem embutida no Microsoft Teams 
=================================================

A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.

A tradução de mensagem embutida está sendo lançada por padrão para sua organização. Se desejar permitir que os usuários usem esse recurso no cliente do Teams, será necessário ativar essa configuração usando o PowerShell. No momento, essa opção não está disponível no Microsoft Teams nem no Skype for Business Admin Center, mas estará em breve.

> [!NOTE]
>Esse lançamento está excluído das assinaturas do Office 365 em nossos ambientes Office 365 Government Community Cloud e Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Habilitar usando o PowerShell

É possível ativar o recurso de tradução de mensagem embutida usando a Diretiva de Mensagens. 

1. Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. A política leva alguns minutos para ser aplicada. Os usuários podem precisar sair e fazer login novamente no Teams.

## <a name="enable-by-using-the-teams-admin-center"></a>Ativar usando o Centro de administração do Teams

A opção para ativar o recurso de tradução de mensagem embutida usando o Centro de administração do Teams estará disponível em breve.

> [!NOTE]
>A tradução ocorre estritamente no lado do cliente e não tem nenhum efeito no conteúdo capturado nos registros de conformidade. Para saber mais sobre a tradução, consulte [O que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).