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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851564"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="ab2d5-103">Usar tradução de mensagem embutida no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab2d5-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="ab2d5-104">A tradução de mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir automaticamente as mensagens do Teams para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado nas configurações pessoais de idioma para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="ab2d5-105">A tradução de mensagem embutida está sendo lançada por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="ab2d5-106">Se desejar permitir que os usuários usem esse recurso no cliente do Teams, será necessário ativar essa configuração usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="ab2d5-107">No momento, essa opção não está disponível no Microsoft Teams nem no Skype for Business Admin Center, mas estará em breve.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="ab2d5-108">Esse lançamento está excluído das assinaturas do Office 365 em nossos ambientes Office 365 Government Community Cloud e Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="ab2d5-109">Habilitar usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab2d5-109">Enable by using PowerShell</span></span>

<span data-ttu-id="ab2d5-110">É possível ativar o recurso de tradução de mensagem embutida usando a Diretiva de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="ab2d5-111">Ative a política usando o cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ab2d5-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="ab2d5-112">A política leva alguns minutos para ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="ab2d5-113">Os usuários podem precisar sair e fazer login novamente no Teams.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="ab2d5-114">Habilitar usando o Microsoft Teams & Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="ab2d5-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="ab2d5-115">A opção para ativar o recurso de conversão de mensagem embutida usando o Microsoft Teams & Skype para Business Admin Center estarão disponíveis em breve.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="ab2d5-116">A tradução ocorre estritamente no lado do cliente e não tem nenhum efeito no conteúdo capturado nos registros de conformidade.</span><span class="sxs-lookup"><span data-stu-id="ab2d5-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="ab2d5-117">Para saber mais sobre a tradução, consulte [O que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="ab2d5-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>