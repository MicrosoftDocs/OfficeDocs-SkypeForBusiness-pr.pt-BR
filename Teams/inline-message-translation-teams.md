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
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882904"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="b0f6d-103">Usar conversão de mensagem embutida no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0f6d-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="b0f6d-104">Tradução de mensagem embutida é um novo recurso de Teams da Microsoft que permite que os usuários automaticamente traduzir mensagens de equipes para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por suas configurações de idioma pessoal para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="b0f6d-105">Tradução de mensagem embutida está sendo distribuída por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="b0f6d-106">Se você quiser permitir que usuários usem esse recurso no cliente equipes, você deve ativar essa configuração usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="b0f6d-107">Atualmente, essa opção não está disponível no Microsoft Teams e Skype para centro de administração de negócios, mas estará em breve.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="b0f6d-108">Essa distribuição é excluída da assinaturas do Office 365 em nossos ambientes de nuvem de comunidade do Office 365 governamental e Alemanha do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="b0f6d-109">Habilitar usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0f6d-109">Enable by using PowerShell</span></span>

<span data-ttu-id="b0f6d-110">Você pode ativar o recurso de conversão de mensagem embutida usando a diretiva de mensagens.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="b0f6d-111">Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b0f6d-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="b0f6d-112">A política leva alguns minutos para aplicar.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="b0f6d-113">Os usuários talvez seja necessário sair e entrar novamente para equipes.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="b0f6d-114">Habilitar usando o Centro de administração de equipes</span><span class="sxs-lookup"><span data-stu-id="b0f6d-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="b0f6d-115">A opção para ativar o recurso de conversão de mensagem embutida usando o Centro de administração de equipes estarão disponíveis em breve.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="b0f6d-116">A conversão é estritamente do cliente e não capturou nenhum efeito sobre o conteúdo dos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b0f6d-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="b0f6d-117">Para saber mais sobre a conversão, consulte [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="b0f6d-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>