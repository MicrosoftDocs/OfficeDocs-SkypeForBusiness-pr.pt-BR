---
title: Solucionar problemas com o acesso de convidados no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenha ajuda para solucionar e corrigir problemas de acesso de convidados no Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: afa30ad1b264088294f775bd69d52e29c5bb423d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116539"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="ec9b5-103">Solucionar problemas com o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ec9b5-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="ec9b5-104">Para ver se sabemos sobre seu problema, confira [Support Teams em sua organização.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="ec9b5-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="ec9b5-105">Para verificar se há problemas de suporte atuais relacionados ao acesso de convidados no Teams, vá para [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="ec9b5-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="ec9b5-106">Os convidados são pessoas fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-106">Guests are people outside your organization.</span></span> <span data-ttu-id="ec9b5-107">Se alguém estiver dentro da sua organização (incluindo seus funcionários, contratados no local ou agentes no local), essa pessoa não poderá ser adicionada como convidado.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="ec9b5-108">O mesmo se aplica aos seus afiliados.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="ec9b5-109">Descubra os próximos recursos novos ou atualizados de acesso de convidados no [Roteiro do Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="ec9b5-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="ec9b5-110">Diga-nos o que você deseja no [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="ec9b5-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="ec9b5-111">Se seus convidados estiverem vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="ec9b5-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="ec9b5-112">O acesso de convidado no Teams usa o Business to Business (B2B) do Azure Active Directory (Azure AD) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="ec9b5-113">O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ec9b5-114">Não é necessária nenhuma licença adicional do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="ec9b5-115">O Teams deve estar habilitado no locatário da casa de um convidado para que os convidados sejam capazes de entrar e usar o Teams como convidado em outro locatário (recurso).</span><span class="sxs-lookup"><span data-stu-id="ec9b5-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="ec9b5-116">Se você estiver vendo erros de licenciamento, leia o modelo de cobrança para Identidades Externas do [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) para determinar os requisitos de licenciamento para atender às suas necessidades de acesso de convidados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="ec9b5-117">As licenças de convidado são contadas na organização que envia os convites.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="ec9b5-118">Considere isso ao calcular o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="ec9b5-119">As licenças são contadas em sua organização se os convidados vêm de outra organização do Microsoft 365 ou se estão usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="ec9b5-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="ec9b5-120">Suporte para tipos de usuário B2B</span><span class="sxs-lookup"><span data-stu-id="ec9b5-120">Support for B2B User types</span></span>

<span data-ttu-id="ec9b5-121">Atualmente, o Teams tem suporte apenas para os tipos de usuários Convidados dos tipos Estado 1 e Estado 2, [conforme definido pelo Azure B2B](/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="ec9b5-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec9b5-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ec9b5-122">Related topics</span></span>

[<span data-ttu-id="ec9b5-123">Acesso de convidados ao Teams</span><span class="sxs-lookup"><span data-stu-id="ec9b5-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="ec9b5-124">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="ec9b5-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)