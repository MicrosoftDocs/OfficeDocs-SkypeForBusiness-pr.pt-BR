---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="b0c1e-102">Configurar políticas e certificados de acesso ao gateway de XMPP</span><span class="sxs-lookup"><span data-stu-id="b0c1e-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0c1e-103">_**Última modificação do tópico:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="b0c1e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="b0c1e-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="b0c1e-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="b0c1e-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span><span class="sxs-lookup"><span data-stu-id="b0c1e-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="b0c1e-106">IM e Presença – apenas pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="b0c1e-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="b0c1e-107">Criação de contatos federados XMPP no cliente Lync</span><span class="sxs-lookup"><span data-stu-id="b0c1e-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="b0c1e-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="b0c1e-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="b0c1e-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0c1e-111">Para começar a migração de Gateway XMPP, você precisa implantar o Gateway XMPP do Lync Server 2013 e configurar as políticas de acesso para habilitar usuários para o gateway do Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="b0c1e-112">Todos os usuários devem ser movidos para a implantação do Lync Server 2013 antes de executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="b0c1e-113">Para obter detalhes, consulte <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b0c1e-114">Configurar uma Política de acesso externo para habilitar usuários para o Gateway XMPP do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0c1e-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b0c1e-115">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b0c1e-116">Na barra de navegação esquerda, clique em **Acesso externo e Federação** e em **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="b0c1e-117">Clique em **Novo** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="b0c1e-118">Insira um nome para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="b0c1e-119">Ofereça uma descrição para a política do usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="b0c1e-120">Selecione **Habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="b0c1e-121">Selecione **Habilitar comunicações com usuários federados XMPP**.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="b0c1e-122">Clique em **Confirmar** para salvar suas alterações na política de usuário ou local.</span><span class="sxs-lookup"><span data-stu-id="b0c1e-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

