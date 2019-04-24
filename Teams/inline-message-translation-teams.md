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
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="45736-103">Usar tradução de mensagem embutida no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45736-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="45736-104">A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="45736-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="45736-105">A tradução de mensagem embutida está sendo lançada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="45736-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="45736-106">Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="45736-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="45736-107">Essa distribuição é excluída da assinaturas do Office 365 em nossos ambientes de nuvem de comunidade do Office 365 governamental e Alemanha do Office 365.</span><span class="sxs-lookup"><span data-stu-id="45736-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="45736-108">Habilitar usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="45736-108">Enable by using PowerShell</span></span>

<span data-ttu-id="45736-109">Você pode ativar o recurso de conversão de mensagem embutida usando a diretiva de mensagens.</span><span class="sxs-lookup"><span data-stu-id="45736-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="45736-110">Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="45736-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="45736-111">A política leva alguns minutos para aplicar.</span><span class="sxs-lookup"><span data-stu-id="45736-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="45736-112">Os usuários talvez seja necessário sair e entrar novamente para equipes.</span><span class="sxs-lookup"><span data-stu-id="45736-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45736-113">Habilitar usando o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45736-113">Enable by using the Microsoft Teams admin center</span></span>

<span data-ttu-id="45736-114">No **Centro de administração de equipes da Microsoft**, selecione **Messaging Policies** na barra de ferramentas esquerda, em seguida, tanto criar uma nova política ou editar uma política existente e defina a opção de **Permitir que os usuários para traduzir mensagens** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="45736-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="45736-115">Conversão é feita pelo serviço e entregue ao cliente com nenhum efeito sobre o conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="45736-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="45736-116">Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="45736-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>