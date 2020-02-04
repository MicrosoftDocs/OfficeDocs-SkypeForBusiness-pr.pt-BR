---
title: 'Lync Server 2013: configurar a Unificação de mensagens no Microsoft Exchange'
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
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="3e07c-102">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e07c-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e07c-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="3e07c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="3e07c-104">Este tópico descreve como configurar o Microsoft Exchange Unified Messaging (um) em um servidor do Microsoft Exchange para uso com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3e07c-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e07c-105">Os exemplos de cmdlet neste tópico fornecem a sintaxe para a versão do Exchange 2007 do Shell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e07c-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="3e07c-106">Se você estiver executando o Exchange 2010 ou o Exchange 2013, consulte a documentação apropriada como referenciada.</span><span class="sxs-lookup"><span data-stu-id="3e07c-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="3e07c-107">Para configurar um servidor que esteja executando o Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="3e07c-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="3e07c-108">Crie um plano de discagem de URI (Uniform Resource Identifier) do UM protocolo SIP para cada um dos perfis de local de voz de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="3e07c-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="3e07c-109">Se você optar por usar o console de gerenciamento do Exchange, crie um novo plano de discagem com a configuração de segurança **protegida (preferencial)**.</span><span class="sxs-lookup"><span data-stu-id="3e07c-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3e07c-110">Se você definir seu valor de configuração de segurança como <STRONG>SIP Secured</STRONG> para exigir criptografia somente para tráfego SIP, como recomendado anteriormente, observe que essa configuração de segurança em um plano de discagem é insuficiente se o pool de front-ends estiver configurado para exigir criptografia, o que significa que o pool requer criptografia para tráfego SIP e RTP.</span><span class="sxs-lookup"><span data-stu-id="3e07c-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="3e07c-111">Quando o plano de discagem e as configurações de segurança do pool não forem compatíveis, todas as chamadas para o Exchange UM do pool de front-ends falharão, resultando em um erro, indicando que você tem uma "configuração de segurança incompatível".</span><span class="sxs-lookup"><span data-stu-id="3e07c-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="3e07c-112">Se você usar o Shell de gerenciamento do Exchange, digite:</span><span class="sxs-lookup"><span data-stu-id="3e07c-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="3e07c-113">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="3e07c-113">For details, see:</span></span>
    
      - <span data-ttu-id="3e07c-114">Para o Office Communications Server 2007, consulte "como criar um plano de discagem de URI SIP [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) de Unificação de mensagens" at e "New [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)-UMDialPlan: Exchange 2007 ajuda" em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="3e07c-115">Para o Exchange 2010, consulte "criar um plano de discagem [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) de um" em e "novo-UMDialPlan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)2010 ajuda" em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="3e07c-116">Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span><span class="sxs-lookup"><span data-stu-id="3e07c-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e07c-117">Não importa se você selecionou um nível de segurança do <STRONG>SIPSecured</STRONG> ou <STRONG>protegido</STRONG> depende se o SRTP (protocolo de transporte em tempo real seguro) está ativado ou desativado para criptografia de mídia.</span><span class="sxs-lookup"><span data-stu-id="3e07c-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="3e07c-118">Para a integração do Lync Server 2010 com o Exchange UM, isso deve corresponder ao nível de criptografia na configuração de mídia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="3e07c-119">A configuração de mídia do Lync Server pode ser exibida executando o cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3e07c-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="3e07c-120">Para obter detalhes, consulte Get-CsMediaConfiguration na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="3e07c-121">Para obter detalhes sobre como selecionar a configuração de segurança de VoIP apropriada, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integrar a Unificação de mensagens local e o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e07c-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="3e07c-122">Execute o cmdlet a seguir para obter o nome de domínio totalmente qualificado (FQDN) de cada plano de discagem do UM:</span><span class="sxs-lookup"><span data-stu-id="3e07c-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="3e07c-123">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="3e07c-123">For details, see:</span></span>
    
      - <span data-ttu-id="3e07c-124">Para o Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="3e07c-125">Para o Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="3e07c-126">Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span><span class="sxs-lookup"><span data-stu-id="3e07c-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="3e07c-127">Grave o nome do plano de discagem de cada plano de discagem do UM.</span><span class="sxs-lookup"><span data-stu-id="3e07c-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="3e07c-128">Dependendo da sua versão do Exchange Server, talvez seja necessário usar o FQDN de cada nome de plano de discagem posteriormente como o nome de cada plano de discagem do Lync Server correspondente para que os nomes dos planos de discagem sejam correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3e07c-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e07c-129">Os nomes dos planos de discagem do Lync Server devem coincidir com nomes de plano de discagem do UM apenas se o plano de discagem do UM estiver sendo executado em uma versão do Exchange <EM>anterior</EM> ao Exchange 2010 SP1</span><span class="sxs-lookup"><span data-stu-id="3e07c-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="3e07c-130">Adicione o plano de discagem ao servidor que executa o UM do Exchange da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3e07c-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="3e07c-131">Se você optar por usar o console de gerenciamento do Exchange, poderá adicionar o plano de discagem na folha de propriedades do servidor.</span><span class="sxs-lookup"><span data-stu-id="3e07c-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="3e07c-132">Para obter instruções específicas, consulte a documentação do produto Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="3e07c-133">Para o Exchange 2007, consulte "como adicionar um servidor de Unificação de mensagens a [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)um plano de discagem" em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="3e07c-134">Para o Exchange 2010, consulte "exibir ou configurar as propriedades de um servidor de um [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)" em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="3e07c-135">Para o Exchange 2013, consulte "mensagens unificadas" em [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span><span class="sxs-lookup"><span data-stu-id="3e07c-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="3e07c-136">Se você usar o Shell de gerenciamento do Exchange, execute o seguinte para cada um dos seus servidores do Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="3e07c-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e07c-137">Antes de executar a etapa a seguir, certifique-se de que todos os usuários do Enterprise Voice foram configurados com uma caixa de correio do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="3e07c-138">Para o Exchange 2007, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>Server 2007 em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="3e07c-139">Para o Exchange 2010, consulte a biblioteca do TechNet do Exchange <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>Server 2010 em.</span><span class="sxs-lookup"><span data-stu-id="3e07c-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="3e07c-140">Ao especificar uma política de caixa de correio para cada plano de discagem que você criou na etapa 1, selecione a política padrão ou uma que você tenha criado.</span><span class="sxs-lookup"><span data-stu-id="3e07c-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="3e07c-141">Navegue até \<os scripts do\>\\diretório de instalação do Exchange e, se o Exchange estiver implantado em uma única floresta, digite:</span><span class="sxs-lookup"><span data-stu-id="3e07c-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="3e07c-142">Ou, se o Exchange estiver implantado em várias florestas, digite:</span><span class="sxs-lookup"><span data-stu-id="3e07c-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="3e07c-143">em que floresta FQDN especifica a floresta na qual o Lync Server é implantado.</span><span class="sxs-lookup"><span data-stu-id="3e07c-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="3e07c-144">Se você tiver um ou mais planos de discagem de UM associados a vários gateways IP, vá para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="3e07c-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="3e07c-145">Se seus planos de discagem estiverem associados a apenas um único gateway IP, pule a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="3e07c-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e07c-146">Certifique-se de reiniciar o serviço de <STRONG>front-end do Lync Server</STRONG> (RtcSrv. exe) <EM>depois</EM> de executar ExchUCUtil. ps1.</span><span class="sxs-lookup"><span data-stu-id="3e07c-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="3e07c-147">Caso contrário, o Lync Server não irá detectar a Unificação de mensagens na topologia.</span><span class="sxs-lookup"><span data-stu-id="3e07c-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="3e07c-148">Usando o Shell de gerenciamento do Exchange ou o console de gerenciamento do Exchange, desabilite as chamadas de saída para todos, exceto um dos gateways IP associados a cada um dos planos de discagem.</span><span class="sxs-lookup"><span data-stu-id="3e07c-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e07c-149">Esta etapa é necessária para garantir que as chamadas de saída do servidor que executam a Unificação de mensagens do Exchange Server sejam feitas a usuários externos (por exemplo, se o caso com cenários de reprodução sob o telefone) atravessará com confiança o firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="3e07c-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e07c-150">Ao selecionar o gateway IP de UM por meio do qual permitir chamadas feitas, escolha o que você pode manipular mais o tráfego.</span><span class="sxs-lookup"><span data-stu-id="3e07c-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="3e07c-151">Não permita o tráfego de saída por meio de um gateway IP que se conecta a um pool de diretores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="3e07c-152">Evite também pools em outro site central ou em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="3e07c-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="3e07c-153">Você pode usar qualquer um dos seguintes métodos para impedir que chamadas feitas passem por um gateway IP:</span><span class="sxs-lookup"><span data-stu-id="3e07c-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="3e07c-154">Se você usar o Shell de gerenciamento do Exchange, desabilite cada gateway IP executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3e07c-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="3e07c-155">Para o Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="3e07c-156">Para o Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="3e07c-157">Se você usar o console de gerenciamento do Exchange, desmarque a caixa de seleção **Permitir chamadas de saída por meio deste gateway de IP** .</span><span class="sxs-lookup"><span data-stu-id="3e07c-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e07c-158">Se o seu plano de discagem de URI SIP SIP estiver associado a um único gateway IP, não permita chamadas de saída por meio desse gateway.</span><span class="sxs-lookup"><span data-stu-id="3e07c-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="3e07c-159">Crie um atendedor automático da UM para cada plano de discagem do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e07c-160">Não inclua espaços no nome do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="3e07c-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="3e07c-161">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="3e07c-161">For details, see:</span></span>
    
      - <span data-ttu-id="3e07c-162">Para o Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="3e07c-163">Para o Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="3e07c-164">A etapa a seguir deve ser realizada para cada usuário depois que você habilitar usuários do Lync Server para Enterprise Voice e conhecer seus URIs SIP.</span><span class="sxs-lookup"><span data-stu-id="3e07c-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="3e07c-165">Associe usuários do Exchange UM (cada um deve ser configurado com uma caixa Exchange mail) com o plano de discagem da UM e crie um URI SIP para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="3e07c-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e07c-166">O <STRONG>SIPResourceIdentifier</STRONG> no exemplo a seguir deve ser o endereço SIP do usuário do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e07c-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="3e07c-167">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="3e07c-167">For details, see:</span></span>
    
      - <span data-ttu-id="3e07c-168">Para o Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="3e07c-169">Para o Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)at.</span><span class="sxs-lookup"><span data-stu-id="3e07c-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

