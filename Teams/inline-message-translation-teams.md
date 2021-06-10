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
description: Saiba como ativar a tradução em linha no Microsoft Teams usando o centro de administração Microsoft Teams ou o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855920"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="733a2-103">Desativar a conversão de mensagens em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="733a2-103">Turn off inline message translation in Microsoft Teams</span></span>

<span data-ttu-id="733a2-104">A conversão em linha de mensagens é um recurso Microsoft Teams [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que permite que os usuários traduzam Teams mensagens para o idioma especificado por suas configurações de idioma pessoal.</span><span class="sxs-lookup"><span data-stu-id="733a2-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="733a2-105">A conversão de mensagens em linha é rolada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="733a2-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="733a2-106">Você não precisa fazer alterações se quiser permitir que os usuários usem esse recurso no Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="733a2-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="733a2-107">Essa adoção é excluída Office 365 assinaturas em nossos ambientes Office 365 Government Community Cloud e Office 365 Alemanha.</span><span class="sxs-lookup"><span data-stu-id="733a2-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="733a2-108">Usar o PowerShell para desativar a conversão de mensagens em linha</span><span class="sxs-lookup"><span data-stu-id="733a2-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="733a2-109">Você pode usar a política de mensagens para desativar a tradução de mensagem em linha.</span><span class="sxs-lookup"><span data-stu-id="733a2-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="733a2-110">Desativar a política usando o cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="733a2-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="733a2-111">A política leva alguns minutos para ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="733a2-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="733a2-112">Os usuários podem precisar sair e entrar novamente Teams.</span><span class="sxs-lookup"><span data-stu-id="733a2-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="733a2-113">Use o Microsoft Teams de administração para desativar a conversão de mensagens em linha</span><span class="sxs-lookup"><span data-stu-id="733a2-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="733a2-114">No centro **de** administração Microsoft Teams,  selecione Políticas de Mensagens na navegação à esquerda, crie uma nova política ou edite uma política existente e de definir a opção **Traduzir** mensagens como **Off**.</span><span class="sxs-lookup"><span data-stu-id="733a2-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="733a2-115">O serviço faz a conversão e a entrega ao cliente sem efeito no conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="733a2-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="733a2-116">Para saber mais sobre tradução, consulte [O que é o Microsoft Tradutor?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="733a2-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>