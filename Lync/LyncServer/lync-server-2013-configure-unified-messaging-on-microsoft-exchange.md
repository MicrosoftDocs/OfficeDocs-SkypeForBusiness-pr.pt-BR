---
title: 'Lync Server 2013: configurar a Unificação de mensagens no Microsoft Exchange'
description: 'Lync Server 2013: configurar a Unificação de mensagens no Microsoft Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577517"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="790e8-103">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="790e8-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="790e8-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="790e8-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="790e8-105">Este tópico descreve como configurar a Unificação de mensagens (UM) do Exchange em um servidor do Microsoft Exchange para uso com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="790e8-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="790e8-106">Os exemplos de cmdlet neste tópico fornecem sintaxe para a versão do Exchange 2007 do Shell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="790e8-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="790e8-107">Se você estiver executando o Exchange 2010 ou o Exchange 2013, consulte a documentação apropriada como referenciada.</span><span class="sxs-lookup"><span data-stu-id="790e8-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="790e8-108">Para configurar um servidor que executa o UM do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="790e8-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="790e8-109">Crie um plano de discagem do protocolo SIP para cada um dos seus perfis de local do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="790e8-109">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="790e8-110">Se você optar por usar o console de gerenciamento do Exchange, crie um novo plano de discagem com a configuração de segurança **protegida (preferencial)**.</span><span class="sxs-lookup"><span data-stu-id="790e8-110">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="790e8-111">Se você definir o valor de configuração de segurança como <STRONG>SIP protegido</STRONG> para exigir criptografia para o tráfego SIP, como anteriormente recomendado, observe que essa configuração de segurança em um plano de discagem é insuficiente se o pool de front-ends estiver configurado para exigir criptografia, o que significa que o pool requer criptografia para o tráfego SIP e RTP.</span><span class="sxs-lookup"><span data-stu-id="790e8-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="790e8-112">Quando o plano de discagem e as configurações de segurança do pool não forem compatíveis, todas as chamadas para o UM do Exchange a partir do pool de front-ends falharão, resultando em um erro indicando que você tem uma "configuração de segurança incompatível".</span><span class="sxs-lookup"><span data-stu-id="790e8-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="790e8-113">Se você usar o Shell de gerenciamento do Exchange, digite:</span><span class="sxs-lookup"><span data-stu-id="790e8-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="790e8-114">Veja mais detalhes em:</span><span class="sxs-lookup"><span data-stu-id="790e8-114">For details, see:</span></span>
    
      - <span data-ttu-id="790e8-115">Para o Office Communications Server 2007, consulte "como criar um plano de discagem URI SIP de Unificação de mensagens" em [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) e "New-UMDialplan: Exchange 2007 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .</span><span class="sxs-lookup"><span data-stu-id="790e8-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="790e8-116">Para o Exchange 2010, consulte "criar um plano de discagem de UM" em [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) e "New-UMDialplan: Exchange 2010 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .</span><span class="sxs-lookup"><span data-stu-id="790e8-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="790e8-117">Para o Exchange 2013, consulte "Unificação de mensagens" em [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="790e8-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="790e8-118">Se você selecionar um nível de segurança de <STRONG>SIPSecured</STRONG> ou <STRONG>protegido</STRONG> depende do protocolo SRTP (Secure real-time Transport Protocol) ser ativado ou desativado para criptografia de mídia.</span><span class="sxs-lookup"><span data-stu-id="790e8-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="790e8-119">Para a integração do Lync Server 2010 com o UM do Exchange, isso deve corresponder ao nível de criptografia na configuração de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="790e8-120">A configuração de mídia do Lync Server pode ser exibida executando o cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="790e8-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="790e8-121">Para obter detalhes, consulte Get-CsMediaConfiguration na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="790e8-122">Para obter detalhes sobre como selecionar a configuração de segurança VoIP apropriada, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="790e8-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="790e8-123">Execute o cmdlet a seguir para obter o FQDN (nome de domínio totalmente qualificado) para cada plano de discagem de UM:</span><span class="sxs-lookup"><span data-stu-id="790e8-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="790e8-124">Veja mais detalhes em:</span><span class="sxs-lookup"><span data-stu-id="790e8-124">For details, see:</span></span>
    
      - <span data-ttu-id="790e8-125">Para o Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .</span><span class="sxs-lookup"><span data-stu-id="790e8-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="790e8-126">Para o Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .</span><span class="sxs-lookup"><span data-stu-id="790e8-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="790e8-127">Para o Exchange 2013, consulte "Unificação de mensagens" em [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="790e8-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="790e8-128">Registre o nome do plano de discagem de cada plano de discagem de UM.</span><span class="sxs-lookup"><span data-stu-id="790e8-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="790e8-129">Dependendo da sua versão do Exchange Server, talvez seja necessário usar o FQDN de cada nome de plano de discagem posteriormente como o nome de cada plano de discagem do Lync Server correspondente de cada plano de discagem para que os nomes do plano de discagem coincidam.</span><span class="sxs-lookup"><span data-stu-id="790e8-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="790e8-130">Os nomes dos planos de discagem do Lync Server devem coincidir com os nomes dos planos de discagem da UM somente se o plano de discagem da UM estiver sendo executado em uma versão do Exchange <EM>anterior</EM> ao Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="790e8-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="790e8-131">Adicione o plano de discagem ao servidor que está executando o UM do Exchange da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="790e8-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="790e8-132">Se você optar por usar o console de gerenciamento do Exchange, poderá adicionar o plano de discagem da folha de propriedades para o servidor.</span><span class="sxs-lookup"><span data-stu-id="790e8-132">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="790e8-133">Para obter instruções específicas, consulte a documentação do produto do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-133">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="790e8-134">Para o Exchange 2007, consulte "como adicionar um servidor de Unificação de mensagens a um plano de discagem" em [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .</span><span class="sxs-lookup"><span data-stu-id="790e8-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="790e8-135">Para o Exchange 2010, consulte "exibir ou configurar as propriedades de um servidor da UM" em [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .</span><span class="sxs-lookup"><span data-stu-id="790e8-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="790e8-136">Para o Exchange 2013, consulte "Unificação de mensagens" em [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="790e8-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="790e8-137">Se você usar o Shell de gerenciamento do Exchange, execute o seguinte para cada um dos seus servidores de UM do Exchange:</span><span class="sxs-lookup"><span data-stu-id="790e8-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="790e8-138">Antes de executar a etapa a seguir, verifique se todos os usuários do Enterprise Voice foram configurados com uma caixa de correio do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="790e8-139">Para o Exchange 2007, consulte a biblioteca do TechNet do Exchange Server 2007 no <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .</span><span class="sxs-lookup"><span data-stu-id="790e8-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="790e8-140">Para o Exchange 2010, consulte a biblioteca do TechNet do Exchange Server 2010 no <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .</span><span class="sxs-lookup"><span data-stu-id="790e8-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="790e8-141">Ao especificar uma política de caixa de correio para cada plano de discagem que você criou na etapa 1, selecione a política padrão ou uma que você tenha criado.</span><span class="sxs-lookup"><span data-stu-id="790e8-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="790e8-142">Navegue até \<Exchange installation directory\> \\ scripts e, se o Exchange estiver implantado em uma única floresta, digite:</span><span class="sxs-lookup"><span data-stu-id="790e8-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="790e8-143">Se o Exchange estiver implantado em várias florestas, digite:</span><span class="sxs-lookup"><span data-stu-id="790e8-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="790e8-144">onde FQDN da floresta especifica a floresta na qual o Lync Server está implantado.</span><span class="sxs-lookup"><span data-stu-id="790e8-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="790e8-145">Se você tiver um ou mais planos de discagem de UM associados a vários gateways IP, vá para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="790e8-145">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="790e8-146">Se seus planos de discagem são associados a um único gateway IP, pule a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="790e8-146">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="790e8-147">Certifique-se de reiniciar o serviço de <STRONG>Front-End do Lync Server</STRONG> (rtcsrv.exe) <EM>depois</EM> de executar exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="790e8-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="790e8-148">Caso contrário, o Lync Server não detectará a Unificação de mensagens na topologia.</span><span class="sxs-lookup"><span data-stu-id="790e8-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="790e8-149">Usando o Shell de gerenciamento do Exchange ou o console de gerenciamento do Exchange, desabilite a chamada de saída para todos os gateways IP associados a cada um dos planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="790e8-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="790e8-150">Essa etapa é necessária para garantir que as chamadas de saída do servidor que está executando a Unificação de mensagens do Exchange Server para usuários externos (por exemplo, como é o caso dos cenários de toque no telefone) atravessam com segurança o firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="790e8-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="790e8-151">Ao selecionar o gateway IP da UM para permitir chamadas de saída, escolha o que é provavelmente para lidar com a maior parte do tráfego.</span><span class="sxs-lookup"><span data-stu-id="790e8-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="790e8-152">Não permitir tráfego de saída por meio de um gateway IP que se conecta a um pool de diretores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="790e8-153">Além disso, evite pools em outro site central ou em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="790e8-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="790e8-154">Você pode usar um dos seguintes métodos para bloquear chamadas de saída passando por um gateway IP:</span><span class="sxs-lookup"><span data-stu-id="790e8-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="790e8-155">Se você usar o Shell de gerenciamento do Exchange, desabilite cada gateway IP executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="790e8-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="790e8-156">Para o Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .</span><span class="sxs-lookup"><span data-stu-id="790e8-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="790e8-157">Para o Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .</span><span class="sxs-lookup"><span data-stu-id="790e8-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="790e8-158">Se você usar o console de gerenciamento do Exchange, desmarque a caixa de seleção **Permitir chamadas de saída por meio deste gateway IP** .</span><span class="sxs-lookup"><span data-stu-id="790e8-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="790e8-159">Se o plano de discagem de URI SIP da UM estiver associado a um único gateway IP, não desautorizar chamadas de saída através desse gateway.</span><span class="sxs-lookup"><span data-stu-id="790e8-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="790e8-160">Crie um atendedor automático da UM para cada plano de discagem do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="790e8-161">Não inclua espaços no nome do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="790e8-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="790e8-162">Veja mais detalhes em:</span><span class="sxs-lookup"><span data-stu-id="790e8-162">For details, see:</span></span>
    
      - <span data-ttu-id="790e8-163">Para o Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .</span><span class="sxs-lookup"><span data-stu-id="790e8-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="790e8-164">Para o Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .</span><span class="sxs-lookup"><span data-stu-id="790e8-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="790e8-165">A etapa a seguir deve ser executada para cada usuário depois que você habilitar usuários do Lync Server para o Enterprise Voice e conhecer seus URIs SIP.</span><span class="sxs-lookup"><span data-stu-id="790e8-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="790e8-166">Associar usuários de UM do Exchange (cada um deles deve ser configurado com uma caixa de correio do Exchange) com o plano de discagem de UM e criar um URI SIP para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="790e8-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="790e8-167">O <STRONG>SIPResourceIdentifier</STRONG> no exemplo a seguir deve ser o endereço SIP do usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="790e8-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="790e8-168">Veja mais detalhes em:</span><span class="sxs-lookup"><span data-stu-id="790e8-168">For details, see:</span></span>
    
      - <span data-ttu-id="790e8-169">Para o Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .</span><span class="sxs-lookup"><span data-stu-id="790e8-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="790e8-170">Para o Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" em [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .</span><span class="sxs-lookup"><span data-stu-id="790e8-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

