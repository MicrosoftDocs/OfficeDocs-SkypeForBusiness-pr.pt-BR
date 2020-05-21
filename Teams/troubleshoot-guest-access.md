---
title: Solucionar problemas com o acesso de convidados no Microsoft Teams
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
description: Obtenha ajuda para solucionar e corrigir problemas de acesso de convidados no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 35598c38ad80e7d1ed75c7aedce021d0d03d2765
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326708"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="9f1c8-103">Solucionar problemas com o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f1c8-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="9f1c8-104">Para ver se conhecemos o problema, confira o [Teams support em sua organização](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="9f1c8-105">Para verificar se há problemas de suporte atuais relacionados ao acesso de convidados no Teams, vá para [Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="9f1c8-106">Convidados são usuários fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-106">Guests are users outside your organization.</span></span> <span data-ttu-id="9f1c8-107">Se alguém estiver dentro da sua organização (incluindo seus funcionários, contratados no local ou agentes no local), essa pessoa não poderá ser adicionada como convidado.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="9f1c8-108">O mesmo se aplica aos seus afiliados.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="9f1c8-109">Descubra os próximos recursos novos ou atualizados de acesso de convidados no [Roteiro do Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="9f1c8-110">Diga-nos o que você deseja no [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="9f1c8-111">Se seus convidados estiverem vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="9f1c8-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="9f1c8-112">O acesso de convidado no Teams usa o Business to Business (B2B) do Azure Active Directory (Azure AD) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="9f1c8-113">O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="9f1c8-114">Não é necessária nenhuma licença adicional do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-114">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="9f1c8-115">As equipes devem estar habilitadas no locatário de casa de um convidado para que os convidados possam entrar e usar o Microsoft Teams como convidado em outro locatário (recurso).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="9f1c8-116">Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar os requisitos de licenciamento para atender às suas necessidades de acesso de convidado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="9f1c8-117">As licenças de convidado são contadas na organização que envia os convites.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="9f1c8-118">Considere isso ao calcular o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="9f1c8-119">As licenças são contadas em sua organização se os convidados convidados vierem de outra organização do Office 365 ou estiverem usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="9f1c8-119">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="9f1c8-120">Suporte para tipos de usuário B2B</span><span class="sxs-lookup"><span data-stu-id="9f1c8-120">Support for B2B User types</span></span>
<span data-ttu-id="9f1c8-121">Atualmente, o Teams tem suporte apenas para os tipos de usuários Convidados dos tipos Estado 1 e Estado 2, [conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="9f1c8-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f1c8-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9f1c8-122">Related topics</span></span>

[<span data-ttu-id="9f1c8-123">Acesso de convidados ao Teams</span><span class="sxs-lookup"><span data-stu-id="9f1c8-123">Guest access in Teams</span></span>](guest-access.md)


