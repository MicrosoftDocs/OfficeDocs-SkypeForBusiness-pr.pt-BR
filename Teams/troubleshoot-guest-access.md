---
title: Solucionar problemas de acesso de convidado no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenha ajuda para solucionar problemas e corrigir problemas de acesso de convidado no Microsoft Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871727"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="8bdec-103">Solucionar problemas de acesso de convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8bdec-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="8bdec-104">Talvez seja necessário aguardar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="8bdec-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="8bdec-105">Para verificar os problemas de suporte atuais com o acesso de convidado no Teams, vá para solução de problemas do Microsoft [Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="8bdec-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="8bdec-106">Para ver se conhecemos o problema, confira os [problemas conhecidos do Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8bdec-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="8bdec-107">Convidados são usuários de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8bdec-107">Guests are users outside your organization.</span></span> <span data-ttu-id="8bdec-108">Se alguém estiver dentro da sua organização (incluindo seus funcionários, prestadores de site ou agentes Onsite), eles não poderão ser adicionados como convidados.</span><span class="sxs-lookup"><span data-stu-id="8bdec-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="8bdec-109">O mesmo se aplica às suas afiliadas.</span><span class="sxs-lookup"><span data-stu-id="8bdec-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="8bdec-110">Saiba mais sobre os futuros recursos de acesso de convidado novos ou atualizados no [roteiro do teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="8bdec-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="8bdec-111">Diga-nos o que você deseja no [UserVoice do teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="8bdec-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="8bdec-112">Se seus convidados estiverem vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="8bdec-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="8bdec-113">O acesso de convidado em equipes usa o Azure Active Directory (Azure AD) Business to Business (B2B) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="8bdec-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="8bdec-114">O acesso de convidados está incluído em todas as inscrições do Office 365 Business Premium, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="8bdec-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="8bdec-115">Não é necessária nenhuma licença adicional do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8bdec-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="8bdec-116">Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar os requisitos de licenciamento para atender às suas necessidades de acesso de convidado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8bdec-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="8bdec-117">As licenças de convidado são contadas em relação à organização que convida.</span><span class="sxs-lookup"><span data-stu-id="8bdec-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="8bdec-118">Considere isso quando você calcular o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="8bdec-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="8bdec-119">As licenças são contadas em relação à sua organização se os convidados convidados vierem de outro locatário do Office 365 ou estiverem usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="8bdec-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="8bdec-120">Suporte para tipos de usuário B2B</span><span class="sxs-lookup"><span data-stu-id="8bdec-120">Support for B2B User types</span></span>
<span data-ttu-id="8bdec-121">Atualmente o Microsoft Teams tem suporte apenas para tipos de estado 1 e estado 2 de usuários convidados [, conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="8bdec-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bdec-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8bdec-122">Related topics</span></span>

[<span data-ttu-id="8bdec-123">Acesso de convidados ao Teams</span><span class="sxs-lookup"><span data-stu-id="8bdec-123">Guest access in Teams</span></span>](guest-access.md)


