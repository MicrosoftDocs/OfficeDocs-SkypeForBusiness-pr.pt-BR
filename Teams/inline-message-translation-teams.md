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
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532698"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="7e1ec-103">Usar tradução de mensagem embutida no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e1ec-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="7e1ec-104">A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="7e1ec-105">A tradução de mensagem embutida está sendo lançada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="7e1ec-106">Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="7e1ec-107">Essa distribuição é excluída da assinaturas do Office 365 em nossos ambientes de nuvem de comunidade do Office 365 governamental e Alemanha do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="7e1ec-108">Habilitar usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e1ec-108">Enable by using PowerShell</span></span>

<span data-ttu-id="7e1ec-109">Você pode ativar o recurso de conversão de mensagem embutida usando a diretiva de mensagens.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="7e1ec-110">Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7e1ec-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="7e1ec-111">A política leva alguns minutos para aplicar.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="7e1ec-112">Os usuários talvez seja necessário sair e entrar novamente para equipes.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="7e1ec-113">Habilitar usando o Microsoft Teams & Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="7e1ec-113">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="7e1ec-114">No **Microsoft equipes & Skype para Business Admin Center**, selecione **Messaging Policies** na barra de ferramentas esquerda, em seguida, tanto criar uma nova política ou editar uma política existente e definir a opção de **Permitir que os usuários para traduzir mensagens** de \*\*em \*\*.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-114">In the **Microsoft Teams & Skype for Business Admin Center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="7e1ec-115">Conversão é feita pelo serviço e entregue ao cliente com nenhum efeito sobre o conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="7e1ec-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="7e1ec-116">Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="7e1ec-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>