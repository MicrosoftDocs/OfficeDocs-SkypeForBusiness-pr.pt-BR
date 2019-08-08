---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022d396d9d87b0112a24d06ee6a863f98795dec8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="78f4e-102">Configurar políticas e certificados de acesso ao gateway de XMPP</span><span class="sxs-lookup"><span data-stu-id="78f4e-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78f4e-103">_**Tópico da última modificação:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="78f4e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="78f4e-104">A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="78f4e-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="78f4e-105">Uma configuração do XMPP permite que os usuários do Lync acessem usuários de domínio do XMPP:</span><span class="sxs-lookup"><span data-stu-id="78f4e-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="78f4e-106">Mensagem instantânea e presença – pessoa para pessoa apenas</span><span class="sxs-lookup"><span data-stu-id="78f4e-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="78f4e-107">Criação de contatos federados do XMPP no cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="78f4e-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="78f4e-108">Quando você configura políticas para dar suporte a parceiros federados do protocolo de Unificação de mensagens e de protocolo de presença (XMPP), as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) (por exemplo, Windows Live) ou domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="78f4e-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="78f4e-109">Você configura um parceiro federado do XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem.</span><span class="sxs-lookup"><span data-stu-id="78f4e-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="78f4e-110">Depois que as políticas estiverem em vigor, você precisará configurar os certificados de gateway do XMPP.</span><span class="sxs-lookup"><span data-stu-id="78f4e-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78f4e-111">Para começar a migração do Gateway XMPP, você precisa implantar o Gateway XMPP do Lync Server 2013 e configurar políticas de acesso para permitir que os usuários do Lync Server 2013 XMPP gateway.</span><span class="sxs-lookup"><span data-stu-id="78f4e-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="78f4e-112">Todos os usuários devem ser movidos para a implantação do Lync Server 2013 antes de executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="78f4e-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="78f4e-113">Para obter detalhes, consulte <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configurar o Gateway XMPP no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="78f4e-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="78f4e-114">Configurar uma política de acesso externo para permitir aos usuários do Lync Server 2013 XMPP gateway</span><span class="sxs-lookup"><span data-stu-id="78f4e-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="78f4e-115">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="78f4e-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="78f4e-116">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="78f4e-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="78f4e-117">Clique em **novo** e, em seguida, clique em **política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="78f4e-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="78f4e-118">Digite um nome para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="78f4e-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="78f4e-119">Forneça uma descrição para a política de usuário de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="78f4e-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="78f4e-120">Selecione **habilitar comunicações com usuários federados**.</span><span class="sxs-lookup"><span data-stu-id="78f4e-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="78f4e-121">Selecione **habilitar comunicações com usuários federados do XMPP**.</span><span class="sxs-lookup"><span data-stu-id="78f4e-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="78f4e-122">Clique em **confirmar** para salvar as alterações no site ou na política de usuário.</span><span class="sxs-lookup"><span data-stu-id="78f4e-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

