---
title: Ativar a tradução de mensagem em linha
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Saiba como ativar a tradução em linha no Microsoft Teams usando o Centro de administração do Microsoft Teams ou o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120622"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="56371-103">Desativar a conversão de mensagens em linha no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56371-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="56371-104">A conversão em linha de mensagens é um recurso [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) do Microsoft Teams que permite que os usuários traduzam mensagens do Teams no idioma especificado por suas configurações de idioma pessoal.</span><span class="sxs-lookup"><span data-stu-id="56371-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="56371-105">A conversão de mensagens em linha é rolada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="56371-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="56371-106">Você não precisa fazer alterações se quiser permitir que os usuários usem esse recurso dentro do cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="56371-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="56371-107">Essa adoção é excluída das assinaturas do Office 365 em nossos ambientes do Office 365 Government Community Cloud e Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="56371-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="56371-108">Usar o PowerShell para desativar a conversão de mensagens em linha</span><span class="sxs-lookup"><span data-stu-id="56371-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="56371-109">Você pode usar a política de mensagens para desativar a tradução de mensagem em linha.</span><span class="sxs-lookup"><span data-stu-id="56371-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="56371-110">Desativar a política usando o cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="56371-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="56371-111">A política leva alguns minutos para ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="56371-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="56371-112">Os usuários podem precisar sair e entrar novamente no Teams.</span><span class="sxs-lookup"><span data-stu-id="56371-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="56371-113">Usar o centro de administração do Microsoft Teams para desativar a conversão de mensagens em linha</span><span class="sxs-lookup"><span data-stu-id="56371-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="56371-114">No Centro de administração  do **Microsoft Teams,** selecione Políticas de Mensagens na navegação à esquerda, crie uma nova política ou edite uma política existente e desdole a opção **Traduzir** mensagens como **Off**.</span><span class="sxs-lookup"><span data-stu-id="56371-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="56371-115">O serviço faz a conversão e a entrega ao cliente sem efeito no conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="56371-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="56371-116">Para saber mais sobre tradução, consulte [O que é o Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="56371-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>