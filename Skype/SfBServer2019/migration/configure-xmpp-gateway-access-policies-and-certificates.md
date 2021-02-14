---
title: Configurar políticas e certificados de acesso ao gateway XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP). Uma configuração XMPP permite que os usuários acessem usuários de domínio XMPP por meio de:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753931"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="cc0c2-104">Configurar políticas e certificados de acesso ao gateway XMPP</span><span class="sxs-lookup"><span data-stu-id="cc0c2-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="cc0c2-105">A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="cc0c2-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="cc0c2-106">Uma configuração XMPP permite que os usuários acessem usuários de domínio XMPP por meio de:</span><span class="sxs-lookup"><span data-stu-id="cc0c2-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="cc0c2-107">IM e Presença - somente pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="cc0c2-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="cc0c2-108">Criação de contatos federados XMPP no cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cc0c2-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="cc0c2-109">Quando você configura políticas para suporte de parceiros federados XMPP, as políticas se aplicam a usuários de domínios federados XMPP, mas não a usuários de provedores de serviços de mensagens instantâneas (IM) SIP ou domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="cc0c2-110">Configure um parceiro federado XMPP para cada domínio federado XMPP com o que você deseja permitir que seus usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="cc0c2-111">Quando as políticas estiverem inseridas, você precisa configurar os certificados de Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc0c2-112">A funcionalidade XMPP foi preterida no Skype for Business Server 2019, mas pode ser continuada em um servidor herdado em coexistência com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="cc0c2-113">Certifique-se de que você já implantou o servidor herdado (Skype for Business Server 2015 / Lync Server 2013) Gateway XMPP e configurou as políticas de acesso para habilitar os usuários para Gateway XMPP herdado.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="cc0c2-114">Para obter detalhes, [consulte Migrating XMPP Federation](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="cc0c2-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="cc0c2-115">Configurar uma política de acesso externo para habilitar usuários para gateway XMPP herdado</span><span class="sxs-lookup"><span data-stu-id="cc0c2-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="cc0c2-116">Abra o Painel de Controle do Skype for Business Server herdado.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="cc0c2-117">Na barra de navegação esquerda, clique em **Acesso externo e Federação** e em **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="cc0c2-118">Clique em **Novo** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="cc0c2-119">Insira um nome para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="cc0c2-120">Ofereça uma descrição para a política do usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="cc0c2-121">Selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="cc0c2-122">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="cc0c2-123">Clique em **Confirmar** para salvar suas alterações na política de usuário ou local.</span><span class="sxs-lookup"><span data-stu-id="cc0c2-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

