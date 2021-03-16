---
title: Compartilhar com o Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre o recurso Compartilhar com o Teams, que permite que os usuários compartilhem emails e anexos de email do Outlook para qualquer chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819417"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="411de-103">Compartilhar com o Teams do Outlook</span><span class="sxs-lookup"><span data-stu-id="411de-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="411de-104">Compartilhar com o Teams do Outlook (Compartilhar com o Teams) permite que os usuários compartilhem emails, incluindo anexos, do Outlook para qualquer chat ou canal no Teams.</span><span class="sxs-lookup"><span data-stu-id="411de-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="411de-105">Complemento do Outlook para Compartilhar com o Teams</span><span class="sxs-lookup"><span data-stu-id="411de-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="411de-106">O recurso Compartilhar com o Teams requer um complemento para o Outlook.</span><span class="sxs-lookup"><span data-stu-id="411de-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="411de-107">Esse complemento é instalado automaticamente sempre que um usuário faz logo web no aplicativo Web do Teams ou no cliente da área de trabalho do Teams.</span><span class="sxs-lookup"><span data-stu-id="411de-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="411de-108">Revise os [Complementos](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) do Outlook no Exchange Online e as Regras de Acesso para Cliente no [Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para garantir que seus complementos para o Outlook funcionem corretamente.</span><span class="sxs-lookup"><span data-stu-id="411de-108">Be sure to review [Add-ins for Outlook in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="411de-109">Além disso, desabilitar experiências conectadas pode impedir que os complementos do Outlook funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="411de-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="411de-110">Confira [Experiências conectadas no Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="411de-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="411de-111">O compartilhamento com o Teams usa o mesmo mecanismo de transporte que quando um usuário envia emails para um canal.</span><span class="sxs-lookup"><span data-stu-id="411de-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="411de-112">Para o compartilhamento em chats, os emails (incluindo anexos de email) são copiados para o OneDrive do remetente.</span><span class="sxs-lookup"><span data-stu-id="411de-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="411de-113">Para compartilhar em canais, emails e anexos são copiados para a pasta **Mensagens de email** no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="411de-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="411de-114">O complemento do Outlook para o Share to Teams usa o conjunto de requisitos 1.7, conforme detalhado na documentação de complementos do [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)que inclui detalhes sobre os complementos do Outlook, os requisitos de ambiente para os complementos do Outlook e os clientes específicos do Outlook com suporte com o conjunto de requisitos 1.7.</span><span class="sxs-lookup"><span data-stu-id="411de-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="411de-115">Habilitando ou desabilitando o Compartilhamento no Teams</span><span class="sxs-lookup"><span data-stu-id="411de-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="411de-116">O complemento do Outlook para o Share to Teams pode ser desabilitado ou habilitado seletivamente por usuário usando os seguintes cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="411de-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="411de-117">Desabilitar o complemento só é possível após a instalação do complemento.</span><span class="sxs-lookup"><span data-stu-id="411de-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="411de-118">Se você quiser impor a desabilitação para todos os usuários em seu locatário, execute um script periodicamente.</span><span class="sxs-lookup"><span data-stu-id="411de-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="411de-119">Para desabilitar o complemento do Outlook usado pelo Share to Teams, execute [o cmdlet encontrado aqui](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="411de-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="411de-120">Para habilitar o complemento do Outlook usado pelo Share to Teams, execute [o cmdlet encontrado aqui](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="411de-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="411de-121">Navegadores e Login Único</span><span class="sxs-lookup"><span data-stu-id="411de-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="411de-122">Compartilhar com o Teams, tanto no Outlook na Web quanto nos clientes da área de trabalho do Outlook, depende de um WebView do navegador.</span><span class="sxs-lookup"><span data-stu-id="411de-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="411de-123">Consulte [Navegadores usados pelos Complementos do Office](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obter detalhes sobre quais clientes usam os navegadores específicos.</span><span class="sxs-lookup"><span data-stu-id="411de-123">See [Browsers used by Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="411de-124">O compartilhamento com o Teams exige que cookies de terceiros e acesso de armazenamento local sejam habilitados para navegadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="411de-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="411de-125">O Compartilhamento para o Teams usa o SSO (Single Sign-on), o que significa que os usuários não precisam fornecer suas credenciais ao usar o complemento por meio do Share to Teams.</span><span class="sxs-lookup"><span data-stu-id="411de-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="411de-126">O SSO para Outlook na Web dá suporte https://outlook.office365.com/owa/extSSO.aspx e https://outlook.office.com/owa/extSSO.aspx responde URLs por padrão.</span><span class="sxs-lookup"><span data-stu-id="411de-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="411de-127">Para domínios de vaidade, os administradores precisam adicionar a URL de resposta apropriada do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="411de-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>