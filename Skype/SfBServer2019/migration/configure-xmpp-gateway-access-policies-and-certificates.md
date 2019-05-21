---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP). Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:'
ms.openlocfilehash: c5231016729cd40619bbcfe48ebfcf59eff9182a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275570"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="55d13-104">Configurar políticas e certificados de acesso ao gateway de XMPP</span><span class="sxs-lookup"><span data-stu-id="55d13-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="55d13-105">A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="55d13-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="55d13-106">Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:</span><span class="sxs-lookup"><span data-stu-id="55d13-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="55d13-107">Mensagem instantânea e presença-pessoa somente para pessoa</span><span class="sxs-lookup"><span data-stu-id="55d13-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="55d13-108">Criação de contatos federados do XMPP no cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="55d13-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="55d13-109">Quando você configura políticas para dar suporte a XMPP parceiros federados, as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas (IM) do protocolo de início de sessão (IM) ou domínios do SIP federado.</span><span class="sxs-lookup"><span data-stu-id="55d13-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="55d13-110">Você configura um parceiro federado do XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="55d13-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="55d13-111">Depois que as políticas estiverem em vigor, você precisará configurar os certificados de gateway do XMPP.</span><span class="sxs-lookup"><span data-stu-id="55d13-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="55d13-112">A funcionalidade do XMPP foi preterida no Skype for Business Server 2019, mas pode continuar em um servidor herdado em coexistência com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="55d13-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="55d13-113">Verifique se você já implantou o servidor herdado (Skype for Business Server 2015/Lync Server 2013) XMPP o gateway e configurou as políticas de acesso para permitir aos usuários do gateway herdado do XMPP.</span><span class="sxs-lookup"><span data-stu-id="55d13-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="55d13-114">Para obter detalhes, consulte Migrando a [Federação do XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="55d13-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="55d13-115">Configurar uma política de acesso externo para permitir que os usuários do gateway herdado XMPP</span><span class="sxs-lookup"><span data-stu-id="55d13-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="55d13-116">Abra o painel de controle herdado do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="55d13-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="55d13-117">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="55d13-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="55d13-118">Clique em **Novo** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="55d13-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="55d13-119">Digite um nome para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="55d13-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="55d13-120">Forneça uma descrição para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="55d13-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="55d13-121">Selecione **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="55d13-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="55d13-122">Selecione **habilitar comunicações com usuários federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="55d13-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="55d13-123">Clique em **confirmar** para salvar as alterações no site ou na política de usuário.</span><span class="sxs-lookup"><span data-stu-id="55d13-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

