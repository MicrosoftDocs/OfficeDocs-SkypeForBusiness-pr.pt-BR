---
title: Acessando o site de provisionamento da conectividade de IM pública do Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e57bac3460c8feb5b3417f433aa228825d824a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529748"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a><span data-ttu-id="3ab40-102">Acessando o site de provisionamento da conectividade de IM pública do Lync Server do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ab40-102">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ab40-103">_**Última modificação do tópico:** 2019-03-22_</span><span class="sxs-lookup"><span data-stu-id="3ab40-103">_**Topic Last Modified:** 2019-03-22_</span></span>

<span data-ttu-id="3ab40-104">O processo de provisionamento para Lync-Skype conectividade mudou, em comparação aos métodos de provisionamento PIC anteriores.</span><span class="sxs-lookup"><span data-stu-id="3ab40-104">The provisioning process for Lync-Skype connectivity has changed, as compared to previous PIC provisioning methods.</span></span> <span data-ttu-id="3ab40-105">Esse processo de provisionamento pode levar até trinta dias para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="3ab40-105">This provisioning process can take up to thirty days to complete.</span></span> <span data-ttu-id="3ab40-106">Recomendamos que você inicie esse processo primeiro, antes de concluir as etapas restantes deste documento.</span><span class="sxs-lookup"><span data-stu-id="3ab40-106">We recommend that you start this process first, prior to completing the remaining steps in this document.</span></span> <span data-ttu-id="3ab40-107">Após a conclusão do processo de provisionamento do Lync-Skype para sua conta, a conta é ativada e seus usuários qualificados estão habilitados para conectividade de IM pública.</span><span class="sxs-lookup"><span data-stu-id="3ab40-107">After the Lync-Skype provisioning process is completed for your account, the account is activated and your eligible users are enabled for public IM connectivity.</span></span>

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a><span data-ttu-id="3ab40-108">Para provisionar a conectividade Lync-Skype, você precisará das seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3ab40-108">To provision Lync-Skype connectivity, you need the following information:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="3ab40-109">Número de contrato da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ab40-109">Microsoft Agreement Number</span></span></p></li>
<li><p><span data-ttu-id="3ab40-110">Nome de domínio totalmente qualificado (FQDN) do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="3ab40-110">Access Edge service fully qualified domain name (FQDN)</span></span></p></li>
<li><p><span data-ttu-id="3ab40-111">Domínio (s) do protocolo de iniciação de sessão (SIP)</span><span class="sxs-lookup"><span data-stu-id="3ab40-111">Session Initiation Protocol (SIP) domain(s)</span></span></p></li>
<li><p><span data-ttu-id="3ab40-112">Todos os FQDNs de serviço de borda de acesso adicional</span><span class="sxs-lookup"><span data-stu-id="3ab40-112">Any additional Access Edge service FQDNs</span></span></p></li>
<li><p><span data-ttu-id="3ab40-113">Informações de contato</span><span class="sxs-lookup"><span data-stu-id="3ab40-113">Contact information</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3ab40-114">A partir de abril de 2019, interromperemos a coleta e a retenção de informações de contato para clientes que foram provisionados para Federação do Skype por meio do site do pic.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3ab40-114">Beginning in April 2019, we will stop the collection and retention of contact information for customers who are provisioned for Skype Federation via the pic.lync.com website.</span></span> <span data-ttu-id="3ab40-115">Essa alteração está sendo feita para garantir que o sistema de provisionamento do pic.lync.com esteja em conformidade com as políticas de privacidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ab40-115">This change is being made to ensure that the pic.lync.com provisioning system adheres to Microsoft privacy policies.</span></span> 

<span data-ttu-id="3ab40-116">Assim que essa alteração for ativa, não será mais possível fornecer atualizações de email em alterações de provisionamento pendentes.</span><span class="sxs-lookup"><span data-stu-id="3ab40-116">Once this change goes live, we will no longer be able to provide email updates on pending provisioning changes.</span></span> <span data-ttu-id="3ab40-117">As alterações de provisionamento de PIC normalmente são concluídas em 24-48 horas após serem inseridas.</span><span class="sxs-lookup"><span data-stu-id="3ab40-117">PIC provisioning changes typically complete within 24-48 hours after being entered.</span></span> <span data-ttu-id="3ab40-118">Se você ainda estiver enfrentando problemas de Federação do Skype 48 horas após o envio de uma solicitação de provisionamento, envolva o suporte técnico da Microsoft para investigar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="3ab40-118">If you are still experiencing Skype Federation issues 48 hours after submitting a provisioning request, please engage Microsoft Technical Support to investigate further.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ab40-119">Como parte dessa alteração, todas as informações de contato inseridas anteriormente serão removidas do nosso sistema até o final de abril de 2019.</span><span class="sxs-lookup"><span data-stu-id="3ab40-119">As part of this change, all previously entered contact information will be purged from our system by the end of April, 2019.</span></span>

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a><span data-ttu-id="3ab40-120">Para iniciar o processo de provisionamento para Lync-Skype conectividade:</span><span class="sxs-lookup"><span data-stu-id="3ab40-120">To initiate the provisioning process for Lync-Skype connectivity:</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><span data-ttu-id="3ab40-121">Entre no site, <strong>https://pic.lync.com</strong> usando o Microsoft Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="3ab40-121">Sign in to the website, <strong>https://pic.lync.com</strong>, using your Microsoft Windows Live ID.</span></span></p></li>
<li><p><span data-ttu-id="3ab40-122">Selecione o tipo de contrato de licenciamento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ab40-122">Select the Microsoft licensing agreement type.</span></span></p></li>
<li><p><span data-ttu-id="3ab40-123">Marque a caixa de seleção, verificando se você leu e aceitou os direitos de uso do produto para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ab40-123">Select the check box, verifying that you have read and accept the Product Use Rights for Lync Server.</span></span></p></li>
<li><p><span data-ttu-id="3ab40-124">Na página <strong>iniciar uma solicitação de provisionamento</strong> , clique no link apropriado para iniciar uma solicitação de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="3ab40-124">On the <strong>Initiate a Provisioning Request</strong> page, click the appropriate link to initiate a provisioning request:</span></span></p></li>
<li><p><span data-ttu-id="3ab40-125">Na página <strong>especificar informações de provisionamento</strong> , insira o FQDN do <strong>serviço de borda de acesso</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ab40-125">On the <strong>Specify Provisioning Information</strong> page, enter the <strong>Access Edge service FQDN</strong>.</span></span> <span data-ttu-id="3ab40-126">Por exemplo, <strong>SIP.contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ab40-126">For example, <strong>sip.contoso.com</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="3ab40-127">Após 1º de julho de 2017 a Microsoft exigirá que os clientes tenham o registro SRV DNS de Federação implantado para conectividade de IM pública para continuar funcionando.</span><span class="sxs-lookup"><span data-stu-id="3ab40-127">After July 1st, 2017 Microsoft will additionally require customers have the Federation DNS SRV record deployed for Public IM connectivity to continue to work.</span></span>

</li>
<li><p><span data-ttu-id="3ab40-128">Insira pelo menos um ou mais nomes de domínio SIP e clique em <strong>Adicionar</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ab40-128">Enter at least one or more SIP domain names, and then click <strong>Add</strong>.</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="3ab40-129">É necessário pelo menos um servidor de borda de acesso e um domínio SIP para concluir o processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="3ab40-129">At least one Access Edge server and one SIP domain are required to complete the provisioning process.</span></span> <span data-ttu-id="3ab40-130">O domínio SIP e o servidor de borda de acesso devem estar ativos, funcionando e alcançáveis na rede.</span><span class="sxs-lookup"><span data-stu-id="3ab40-130">The SIP domain and the Access Edge server must be active, functioning, and reachable on the network.</span></span>

</li>
<li><p><span data-ttu-id="3ab40-131">Na lista de <strong>provedores de serviço de mensagens instantâneas públicas</strong>, selecione <strong>Skype</strong> e clique em <strong>Avançar</strong> para adicionar informações de contato e enviar a solicitação de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="3ab40-131">In the list of <strong>Public IM Service providers</strong>, select <strong>Skype,</strong> and click <strong>Next</strong> to add contact information, and submit the provisioning request.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3ab40-132">Após o envio da solicitação de provisionamento, pode levar até 30 dias para que a conta seja ativada e para que os usuários sejam habilitados para conectividade de IM pública.</span><span class="sxs-lookup"><span data-stu-id="3ab40-132">After the provisioning request has been submitted, it can take up to 30 days for the account to activate and for users to be enabled for public IM connectivity.</span></span>

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="3ab40-133">Habilitando Federação e conectividade pública de IM (PIC)</span><span class="sxs-lookup"><span data-stu-id="3ab40-133">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="3ab40-134">Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar a conectividade do Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="3ab40-134">After you have submitted the provisioning request, you can focus on the Lync Server environment and administrative tasks required to configure Lync-Skype connectivity.</span></span> <span data-ttu-id="3ab40-135">Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="3ab40-135">In this section, we assume that the Lync Server administrator has deployed Lync Server and configured external access.</span></span> <span data-ttu-id="3ab40-136">Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte "planejando o acesso de usuários externos" em [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) e "Implantando o acesso de usuário externo" em [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) .</span><span class="sxs-lookup"><span data-stu-id="3ab40-136">For additional information on configuring external access for Lync Server, see "Planning for External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) and "Deploying External User Access" at [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).</span></span>

<span data-ttu-id="3ab40-137">Para preparar o ambiente do Lync Server para Lync-Skype conectividade, o administrador do Lync Server deve concluir as três tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="3ab40-137">To prepare the Lync Server environment for Lync-Skype connectivity, the Lync Server administrator must complete the following three tasks:</span></span>

<div>

## <a name="1-configure-federation-and-pic"></a><span data-ttu-id="3ab40-138">1\.</span><span class="sxs-lookup"><span data-stu-id="3ab40-138">1\.</span></span> <span data-ttu-id="3ab40-139">Configurar a Federação e a PIC</span><span class="sxs-lookup"><span data-stu-id="3ab40-139">Configure Federation and PIC</span></span>

<span data-ttu-id="3ab40-140">A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3ab40-140">Federation is required to enable Skype users to communicate with Lync users in your organization.</span></span> <span data-ttu-id="3ab40-141">A PIC (conectividade de mensagens instantâneas públicas) é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com os usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="3ab40-141">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Lync users to communicate with Skype users.</span></span> <span data-ttu-id="3ab40-142">A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="3ab40-142">Federation and PIC are configured by using the Lync Server Control Panel, shown below.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3ab40-143">A Federação de PIC não é mais suportada pelo Live Communication Server 2005 SP1 ou pelo Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3ab40-143">PIC federation is no longer supported by Live Communication Server 2005 SP1 or by Office Communications Server 2007.</span></span> <span data-ttu-id="3ab40-144">As plataformas suportadas para Federação img incluem Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3ab40-144">The supported platforms for PIC federation include Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2.</span></span>



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="3ab40-145">2\.</span><span class="sxs-lookup"><span data-stu-id="3ab40-145">2\.</span></span> <span data-ttu-id="3ab40-146">Configurar pelo menos uma política para suportar o acesso de usuário federado</span><span class="sxs-lookup"><span data-stu-id="3ab40-146">Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="3ab40-147">Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ab40-147">Using the Lync Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Lync Server users.</span></span>

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a><span data-ttu-id="3ab40-148">3\.</span><span class="sxs-lookup"><span data-stu-id="3ab40-148">3\.</span></span> <span data-ttu-id="3ab40-149">Definir a configuração do provedor de PIC do Skype para Lync</span><span class="sxs-lookup"><span data-stu-id="3ab40-149">Configure the Skype PIC provider setting for Lync</span></span>

<span data-ttu-id="3ab40-150">Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.</span><span class="sxs-lookup"><span data-stu-id="3ab40-150">Using the Lync Server Management Shell, an administrator must configure the Lync client policy to display Skype as an additional PIC provider.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3ab40-151">Os usuários dos provedores de serviços públicos da PIC (conectividade de mensagens instantâneas) não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de IM pública.</span><span class="sxs-lookup"><span data-stu-id="3ab40-151">Users of the Public Instant Messaging Connectivity (PIC) service providers can’t participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span><BR><span data-ttu-id="3ab40-152">Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar Federação e conectividade de IM pública" em <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> .</span><span class="sxs-lookup"><span data-stu-id="3ab40-152">To configure federation and PIC, see "Enable or Disable Federation and Public IM Connectivity" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>.</span></span><BR><span data-ttu-id="3ab40-153">Para configurar pelo menos uma política para suportar o acesso de usuário federado, consulte "configurar políticas para controlar o acesso de usuário público" em <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> .</span><span class="sxs-lookup"><span data-stu-id="3ab40-153">To configure at least one policy to support federated user access, see "Configure Policies to Control Public User Access" at <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>.</span></span>



</div>

1.  <span data-ttu-id="3ab40-154">Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ab40-154">From a Lync Server Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3ab40-155">Execute os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="3ab40-155">Run the following two commands:</span></span>
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3ab40-156">Se você ainda não tem um provedor de PIC em seu ambiente e está criando um novo provedor de PIC, não é necessário executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3ab40-156">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the <STRONG>Remove-CsPublicProvider</STRONG> cmdlet.</span></span>

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3ab40-157">Adicionado ao Lync Server 2013 CU5 &amp; Lync Desktop Client no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList aprimoram a situação em que os usuários do Lync adicionando contatos do Skype necessários para "decorar" domínios que não são da Microsoft para identificar e encaminhá-los ao Skype (o formato de: usuário (contoso. com) @msn. com).</span><span class="sxs-lookup"><span data-stu-id="3ab40-157">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to “decorate” non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="3ab40-158">Essas novas configurações permitirão a formatação automática do usuário do endereço Enter na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios no NameDecorationExcludedDomainList (no momento, podemos oferecer suporte a msn.com, live.com, Hotmail.com, outlook.com).</span><span class="sxs-lookup"><span data-stu-id="3ab40-158">These new settings will allow automatic formatting of the address user’s enter in the “Add Skype contact” dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span>

        
        </div>

3.  <span data-ttu-id="3ab40-159">A partir de um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ab40-159">From a Lync client, you can now select Skype as the PIC provider, and add a Skype client by specifying their Microsoft account.</span></span> <span data-ttu-id="3ab40-160">Além disso, um usuário do Skype que tenha sido mesclado e conectado com a sua conta da Microsoft pode enviar solicitações de contato aos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="3ab40-160">In addition, a Skype user who has merged and logged in with their Microsoft account can send contact request to Lync users.</span></span> <span data-ttu-id="3ab40-161">Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span><span class="sxs-lookup"><span data-stu-id="3ab40-161">For more information about Microsoft accounts, see [What is a Microsoft account?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account).</span></span> <span data-ttu-id="3ab40-162">Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [Using Lync-Skype Connectivity in Lync Server 2013 como um usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span><span class="sxs-lookup"><span data-stu-id="3ab40-162">For additional information on adding clients to Lync, see [Using Lync-Skype connectivity in Lync Server 2013 as an end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).</span></span>

4.  <span data-ttu-id="3ab40-163">Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP hospedados" em [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .</span><span class="sxs-lookup"><span data-stu-id="3ab40-163">For detailed information on modifying hosted providers, see "Create or Edit Hosted SIP Federated Providers" at [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).</span></span>

<span data-ttu-id="3ab40-164">Isso conclui as tarefas administrativas que devem ser executadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="3ab40-164">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="3ab40-165">Agora você está pronto para a conectividade do Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="3ab40-165">You are now set up for Lync-Skype connectivity.</span></span>

</div>

</div>

<div>

## <a name="additional-resources"></a><span data-ttu-id="3ab40-166">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3ab40-166">Additional Resources</span></span>

[<span data-ttu-id="3ab40-167">Usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final</span><span class="sxs-lookup"><span data-stu-id="3ab40-167">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[<span data-ttu-id="3ab40-168">Guia de provisionamento para Lync-Skype conectividade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ab40-168">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

