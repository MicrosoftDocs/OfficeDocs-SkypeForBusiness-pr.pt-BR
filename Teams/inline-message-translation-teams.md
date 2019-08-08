---
title: Ativar a tradução de mensagens embutidas no Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
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
ms.openlocfilehash: 8b6da80dda90c57a55a75c885b42bc08a824b613
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245336"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="edfa4-103">Ativar a tradução de mensagens embutidas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edfa4-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="edfa4-104">A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="edfa4-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="edfa4-105">A tradução de mensagem embutida está sendo lançada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="edfa4-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="edfa4-106">Se você quiser permitir que os usuários usem esse recurso dentro do cliente do Teams, deverá ativar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="edfa4-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="edfa4-107">Esta distribuição é excluída das assinaturas do Office 365 na nuvem da Comunidade do governo do Office 365 e nos ambientes do Office 365 Alemanha.</span><span class="sxs-lookup"><span data-stu-id="edfa4-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="edfa4-108">Usar o PowerShell para ativar a tradução de mensagens embutidas</span><span class="sxs-lookup"><span data-stu-id="edfa4-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="edfa4-109">Você pode usar a política de mensagens para ativar a tradução embutida da mensagem.</span><span class="sxs-lookup"><span data-stu-id="edfa4-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="edfa4-110">Ative a política usando o cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="edfa4-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="edfa4-111">A política demora alguns minutos para se aplicar.</span><span class="sxs-lookup"><span data-stu-id="edfa4-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="edfa4-112">Os usuários podem precisar sair e entrar novamente no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="edfa4-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="edfa4-113">Usar o centro de administração do Microsoft Teams para ativar a tradução de mensagens embutidas</span><span class="sxs-lookup"><span data-stu-id="edfa4-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="edfa4-114">No **centro de administração do Microsoft Teams**, selecione políticas de **mensagens** da navegação à esquerda, crie uma nova política ou edite uma política existente e defina a opção **permitir que os usuários traduzam mensagens** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="edfa4-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="edfa4-115">O serviço faz a tradução e a entrega para o cliente sem nenhum efeito sobre o conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="edfa4-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="edfa4-116">Para saber mais sobre a tradução, confira [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="edfa4-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>