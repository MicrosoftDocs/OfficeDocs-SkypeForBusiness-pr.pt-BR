---
title: 'Lync Server 2013: Habilitando conectividade Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0125ff4719cd3dfeb65353df747395e596b45dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="19098-102">Habilitando conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19098-102">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19098-103">_**Tópico da última modificação:** 2014-12-16_</span><span class="sxs-lookup"><span data-stu-id="19098-103">_**Topic Last Modified:** 2014-12-16_</span></span>

<span data-ttu-id="19098-104">Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar o Lync-conectividade com o Skype.</span><span class="sxs-lookup"><span data-stu-id="19098-104">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="19098-105">Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="19098-105">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="19098-106">Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte [planejar o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implantar o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="19098-106">For additional information on configuring external access for Lync Server, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

<span data-ttu-id="19098-107">Para preparar o ambiente do Lync Server para o Lync-conectividade do Skype, o administrador do Lync Server deve completar as três tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="19098-107">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="19098-108">1 \.</span><span class="sxs-lookup"><span data-stu-id="19098-108">1\.</span></span> <span data-ttu-id="19098-109">Configurar a federação e a PIC</span><span class="sxs-lookup"><span data-stu-id="19098-109">Configure Federation and PIC</span></span>

<span data-ttu-id="19098-110">A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização.</span><span class="sxs-lookup"><span data-stu-id="19098-110">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="19098-111">A PIC (conectividade de mensagens instantâneas) pública é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="19098-111">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="19098-112">A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="19098-112">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<span data-ttu-id="19098-113">![Mostrando PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Mostrando PIC")</span><span class="sxs-lookup"><span data-stu-id="19098-113">![Showing PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Showing PIC")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="19098-114">A federação de PIC não tem mais suporte no Live Communication Server 2005 SP1 e no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="19098-114">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="19098-115">As plataformas com suporte para a Federação PIC incluem o Lync Server 2013, o Lync Server 2010 e o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="19098-115">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="19098-116">2 \.</span><span class="sxs-lookup"><span data-stu-id="19098-116">2\.</span></span> <span data-ttu-id="19098-117">Configurar pelo menos uma política para dar suporte ao acesso de usuários federados</span><span class="sxs-lookup"><span data-stu-id="19098-117">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="19098-118">Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso externo do usuário para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19098-118">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

<span data-ttu-id="19098-119">![Políticas](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Políticas")</span><span class="sxs-lookup"><span data-stu-id="19098-119">![Policies](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Policies")</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="19098-120">3 \.</span><span class="sxs-lookup"><span data-stu-id="19098-120">3\.</span></span> <span data-ttu-id="19098-121">Configurar a configuração do provedor de PIC da Skype para o Lync</span><span class="sxs-lookup"><span data-stu-id="19098-121">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="19098-122">Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.</span><span class="sxs-lookup"><span data-stu-id="19098-122">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19098-123">Os usuários dos provedores de serviço de conectividade de mensagens instantâneas (PIC) públicas não podem participar de chats ou videoconferências em sua organização até você também configurar pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de mensagens de chat pública.</span><span class="sxs-lookup"><span data-stu-id="19098-123">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or audio or video conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span>



</div>

1.  <span data-ttu-id="19098-124">Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar a Federação e conectividade de [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)im pública" em.</span><span class="sxs-lookup"><span data-stu-id="19098-124">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).</span></span>

2.  <span data-ttu-id="19098-125">Para configurar pelo menos uma política para dar suporte ao acesso de usuário federado, consulte "configurar políticas para controlar o acesso [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)ao usuário público" em.</span><span class="sxs-lookup"><span data-stu-id="19098-125">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).</span></span>

<span data-ttu-id="19098-126">**Para editar um Messenger existente ou um provedor de PIC da Skype e configurá-lo para o Skype**</span><span class="sxs-lookup"><span data-stu-id="19098-126">**To edit an existing Messenger or Skype PIC provider and configure it for Skype**</span></span>

1.  <span data-ttu-id="19098-127">Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19098-127">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="19098-128">Execute estes dois comandos:</span><span class="sxs-lookup"><span data-stu-id="19098-128">Run the following two commands:</span></span>
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19098-129">Se você ainda não tiver um provedor PIC em seu ambiente e estiver criando um novo provedor PIC, você não precisará executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="19098-129">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19098-130">Adicionado ao Lync Server 2013 CU5 &amp; o cliente de área de trabalho Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionam contatos do Skype necessários para "decorar" domínios não-Microsoft para identificar e roteá-los para o Skype (o formato de: usuário (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="19098-130">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="19098-131">Essas novas configurações permitem a formatação automática dos endereços que o usuário inserir na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser configurado como msn.com) se não contiver os domínios de NameDecorationExcludedDomainList (no momento, damos suporte a msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="19098-131">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

    
    </div>

3.  <span data-ttu-id="19098-132">Em um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando a conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19098-132">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="19098-133">Além disso, um usuário do Skype que mesclou e fez logon com a conta da Microsoft pode enviar solicitação de contato para os usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="19098-133">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="19098-134">Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="19098-134">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="19098-135">Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [usando o Lync-conectividade do Skype no Lync Server 2013 como usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="19098-135">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>
    
    <span data-ttu-id="19098-136">![Adicionar contato do Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Adicionar contato do Skype")</span><span class="sxs-lookup"><span data-stu-id="19098-136">![Add Skype Contact](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Add Skype Contact")</span></span>

4.  <span data-ttu-id="19098-137">Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" em.</span><span class="sxs-lookup"><span data-stu-id="19098-137">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="19098-138">Isso conclui as tarefas administrativas que devem ser executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="19098-138">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="19098-139">Agora você está pronto para o Lync-conectividade com o Skype.</span><span class="sxs-lookup"><span data-stu-id="19098-139">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

