---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Federação XMPP define uma implantação externa com base nas mensagens extensível e protocolo de presença (XMPP). Uma configuração de XMPP permite que os usuários acessem usuários de domínio XMPP por:'
ms.openlocfilehash: 2ec2440365907632523728238c51cc90e894c84e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027855"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="634f1-104">Configurar políticas e certificados de acesso ao gateway de XMPP</span><span class="sxs-lookup"><span data-stu-id="634f1-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="634f1-105">Federação XMPP define uma implantação externa com base nas mensagens extensível e protocolo de presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="634f1-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="634f1-106">Uma configuração de XMPP permite que os usuários acessem usuários de domínio XMPP por:</span><span class="sxs-lookup"><span data-stu-id="634f1-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="634f1-107">IM e presença - apenas entre duas pessoas</span><span class="sxs-lookup"><span data-stu-id="634f1-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="634f1-108">Criação de contatos federados XMPP no Skype para o cliente de negócios</span><span class="sxs-lookup"><span data-stu-id="634f1-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="634f1-109">Quando você configura políticas para suporte de XMPP federados parceiros, as diretivas serão aplicadas aos usuários de domínios XMPP federado, mas não para usuários de protocolo de iniciação de sessão (SIP) serviço (IM) de mensagens instantâneas provedores ou SIP domínios federados.</span><span class="sxs-lookup"><span data-stu-id="634f1-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="634f1-110">Você configurar um parceiro federado de XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionar contatos e comunique-se com.</span><span class="sxs-lookup"><span data-stu-id="634f1-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="634f1-111">Depois que as diretivas estão no lugar, você precisa configurar os certificados do Gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="634f1-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="634f1-112">Funcionalidade XMPP foi preterida no Skype para Business Server 2019, mas pode ser continuada em um servidor herdado em coexistência com o Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="634f1-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="634f1-113">Certificar-se de que você já implantou o servidor herdado (Skype para Business Server 2015 / Lync Server 2013) Gateway XMPP e configurar as políticas de acesso para habilitar usuários para o Gateway de XMPP herdado.</span><span class="sxs-lookup"><span data-stu-id="634f1-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="634f1-114">Para obter detalhes, consulte [Migrando federação de XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="634f1-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="634f1-115">Configurar uma política de acesso externo para habilitar usuários para o Gateway de XMPP herdado</span><span class="sxs-lookup"><span data-stu-id="634f1-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="634f1-116">Abra o Skype herdado para o painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="634f1-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="634f1-117">Na barra de navegação à esquerda, clique em **federação e acesso externo**e, em seguida, clique em **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="634f1-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="634f1-118">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="634f1-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="634f1-119">Insira um nome para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="634f1-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="634f1-120">Forneça uma descrição para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="634f1-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="634f1-121">Selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="634f1-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="634f1-122">Selecione **Habilitar comunicações com XMPP usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="634f1-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="634f1-123">Clique em **Confirmar** para salvar suas alterações na política de site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="634f1-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

