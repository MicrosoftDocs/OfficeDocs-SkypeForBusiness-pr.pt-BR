---
title: Ativar a tradução de mensagens embutidas
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
description: Saiba como ativar a tradução embutida no Microsoft Teams usando o centro de administração do Microsoft Teams ou o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395380"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="bbb36-103">Desativar a tradução da mensagem embutida no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbb36-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="bbb36-104">A tradução de mensagem embutida é um recurso do Microsoft Teams que permite aos usuários traduzir mensagens de equipes para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado pelas configurações de idioma pessoal.</span><span class="sxs-lookup"><span data-stu-id="bbb36-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="bbb36-105">A tradução da mensagem embutida é implementada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbb36-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="bbb36-106">Não é necessário fazer alterações se você deseja permitir que os usuários usem esse recurso dentro do cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="bbb36-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="bbb36-107">Esta distribuição é excluída das assinaturas do Office 365 na nuvem da Comunidade do governo do Office 365 e nos ambientes do Office 365 Alemanha.</span><span class="sxs-lookup"><span data-stu-id="bbb36-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="bbb36-108">Usar o PowerShell para desativar a tradução da mensagem embutida</span><span class="sxs-lookup"><span data-stu-id="bbb36-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="bbb36-109">Você pode usar a política de mensagens para desativar a tradução da mensagem embutida.</span><span class="sxs-lookup"><span data-stu-id="bbb36-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="bbb36-110">Desative a política usando o cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bbb36-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="bbb36-111">A política demora alguns minutos para se aplicar.</span><span class="sxs-lookup"><span data-stu-id="bbb36-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="bbb36-112">Os usuários podem precisar sair e entrar novamente no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbb36-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="bbb36-113">Usar o centro de administração do Microsoft Teams para desativar a tradução da mensagem embutida</span><span class="sxs-lookup"><span data-stu-id="bbb36-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="bbb36-114">No **centro de administração do Microsoft Teams**, selecione **políticas de mensagens** da navegação à esquerda e, em seguida, crie uma nova política ou edite uma política existente e defina a opção **traduzir mensagens** como **desativada**.</span><span class="sxs-lookup"><span data-stu-id="bbb36-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb36-115">O serviço faz a tradução e a entrega para o cliente sem nenhum efeito sobre o conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="bbb36-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="bbb36-116">Para saber mais sobre a tradução, confira [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="bbb36-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
