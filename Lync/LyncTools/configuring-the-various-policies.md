---
title: Configurando as várias políticas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="d3836-102">Configurando as várias políticas</span><span class="sxs-lookup"><span data-stu-id="d3836-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3836-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d3836-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="d3836-104">Configurando as várias políticas</span><span class="sxs-lookup"><span data-stu-id="d3836-104">Configuring the Various Policies</span></span>

<span data-ttu-id="d3836-105">Aqui estão as várias políticas que você pode configurar na sua topologia do Lync Server 2013, antes de executar a ferramenta de stress e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3836-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="d3836-106">Configurar a política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="d3836-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="d3836-107">Consulte o script de exemplo ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="d3836-108">Você só precisará usar esse script se um servidor de arquivamento estiver implantado na sua topologia.</span><span class="sxs-lookup"><span data-stu-id="d3836-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="d3836-109">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [arquivamento e monitoramento de cmdlets no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="d3836-110">Configurar a política de conferência</span><span class="sxs-lookup"><span data-stu-id="d3836-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="d3836-111">Consulte o script de exemplo MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="d3836-112">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para cmdlets de [Webconferência no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="d3836-113">Configurando a política de contatos</span><span class="sxs-lookup"><span data-stu-id="d3836-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="d3836-114">Consulte o exemplo ContactsPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="d3836-115">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os cmdlets de [presença e mensagens instantâneas no Lync server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="d3836-116">Configurando a política de Federação</span><span class="sxs-lookup"><span data-stu-id="d3836-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="d3836-117">Consulte o exemplo FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="d3836-118">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para cmdlets do [servidor de borda no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) e cmdlets de [acesso externo e Federação no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="d3836-119">Configurando a política de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="d3836-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="d3836-120">Consulte o exemplo BandwidthPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="d3836-121">Para obter detalhes, consulte a [visão geral da documentação do Lync Server 2013 do controle de admissão de chamadas no Lync server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) e a ajuda do cmdlet para cmdlets de [controle de admissão de chamadas no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="d3836-122">Configurando as regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="d3836-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="d3836-123">Consulte o exemplo RoutingRules. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="d3836-124">Ao configurar as regras de roteamento de voz, anote o contexto do telefone (ou seja, o perfil do/Location ou/SimpleName) e os códigos de área interna/externa para que você possa especificá-los ao criar usuários e durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="d3836-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="d3836-125">Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules. ps1 deve ser usado para o valor LocationProfile na seguinte imagem do UserProfileGenerator. exe.</span><span class="sxs-lookup"><span data-stu-id="d3836-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="d3836-126">![Regra de roteamento de voz de exemplo.] (images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regra de roteamento de voz de exemplo.")</span><span class="sxs-lookup"><span data-stu-id="d3836-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="d3836-127">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para cmdlets do [Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="d3836-128">Configurando o aplicativo de assistente de conferência</span><span class="sxs-lookup"><span data-stu-id="d3836-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="d3836-129">Consulte o exemplo ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="d3836-130">Anote o número de telefone ConferencingAutoAttendant (1121111111, por padrão), para que você possa digitá-lo na ferramenta de configuração da ferramenta LyncPerf para geração de configuração.</span><span class="sxs-lookup"><span data-stu-id="d3836-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="d3836-131">![Configurando o aplicativo assistente de conferência] (images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurando o aplicativo assistente de conferência")</span><span class="sxs-lookup"><span data-stu-id="d3836-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="d3836-132">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para cmdlets de [Webconferência no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) e cmdlets de [conferência discada no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="d3836-133">Configurando o serviço de estacionamento de chamadas do Lync Server</span><span class="sxs-lookup"><span data-stu-id="d3836-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="d3836-134">O parque de chamadas está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="d3836-134">Call Park is disabled by default.</span></span> <span data-ttu-id="d3836-135">Consulte o exemplo CallParkConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="d3836-136">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os cmdlets do [aplicativo de estacionamento de chamada no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="d3836-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="d3836-137">Configurando chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="d3836-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="d3836-138">Execute as etapas a seguir para configurar o teste de stress e desempenho para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="d3836-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="d3836-139">Configurar uma rota de voz para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="d3836-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="d3836-140">Consulte o script RoutingRules. ps1 sob o comentário "Route E911 to PSTN" para obter um exemplo de como configurar essa rota de voz.</span><span class="sxs-lookup"><span data-stu-id="d3836-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d3836-141">O comando de exemplo em RoutingRules. ps1 tem um padrão de número que inclui o número 119 em vez de 911.</span><span class="sxs-lookup"><span data-stu-id="d3836-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="d3836-142">Evite usar o 911 (ou o seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga.</span><span class="sxs-lookup"><span data-stu-id="d3836-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="d3836-143">Essa configuração é somente para fins de simulação.</span><span class="sxs-lookup"><span data-stu-id="d3836-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="d3836-144">Para configurar endereços, preencha os valores na guia **Lis** no UserProvisioningTool, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3836-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="d3836-145">![Configurar o serviço de informações de localização.] (images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurar o serviço de informações de localização.")</span><span class="sxs-lookup"><span data-stu-id="d3836-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="d3836-146">Clique em **gerar arquivos Lis config**.</span><span class="sxs-lookup"><span data-stu-id="d3836-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="d3836-147">Arquivos CSV para portas, sub-redes, opções e pontos de acesso sem fio (WAPs) e um arquivo XML para a ferramenta de stress e desempenho do Lync Server 2013 são gerados.</span><span class="sxs-lookup"><span data-stu-id="d3836-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="d3836-148">Os arquivos CSV devem ser usados como entradas (na mesma pasta) durante a configuração do LIS (serviço de informações de localização) com o script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="d3836-149">Mova o arquivo Locations0. XML gerado para a mesma pasta que o executável da ferramenta de desempenho e sobrecarga do Lync Server 2013 (LyncPerfTool. exe), que executará cenários de perfil de localização (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="d3836-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="d3836-150">Criando, habilitando, Configurando e desabilitando usuários</span><span class="sxs-lookup"><span data-stu-id="d3836-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="d3836-151">Você deve criar todos os usuários antes de executar os scripts a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3836-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="d3836-152">Siga as instruções em [criar usuários e contatos](create-users-and-contacts.md) para criar usuários.</span><span class="sxs-lookup"><span data-stu-id="d3836-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="d3836-153">Para obter detalhes, consulte a documentação do cmdlet do Lync Server 2013 para os cmdlets [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="d3836-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="d3836-154">Configurando o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="d3836-154">Configuring Response Group application</span></span>

<span data-ttu-id="d3836-155">Consulte o exemplo ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="d3836-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="d3836-156">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os cmdlets do [aplicativo grupo de resposta no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)). Para revisar a configuração do aplicativo grupo `https://<poolfqdn>/RgsConfig/`de resposta, consulte, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3836-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="d3836-157">![A ferramenta de configuração de grupo de resposta.] (images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "A ferramenta de configuração de grupo de resposta.")</span><span class="sxs-lookup"><span data-stu-id="d3836-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

