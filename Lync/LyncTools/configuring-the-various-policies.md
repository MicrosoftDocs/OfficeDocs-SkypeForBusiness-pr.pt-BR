---
title: Configurando as várias políticas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98cb69c1c83b794292c31c43ba9778e8efb8cb99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="c990c-102">Configurando as várias políticas</span><span class="sxs-lookup"><span data-stu-id="c990c-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c990c-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c990c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="c990c-104">Configurando as várias políticas</span><span class="sxs-lookup"><span data-stu-id="c990c-104">Configuring the Various Policies</span></span>

<span data-ttu-id="c990c-105">Aqui estão as várias políticas que você pode configurar na sua topologia do Lync Server 2013, antes de executar a ferramenta de estresse e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c990c-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="c990c-106">Configurando a política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="c990c-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="c990c-107">Consulte o script de exemplo ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="c990c-108">Você só precisará usar esse script se um servidor de arquivamento estiver implantado em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="c990c-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="c990c-109">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets de arquivamento e monitoramento no Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="c990c-110">Configurando a política de conferência</span><span class="sxs-lookup"><span data-stu-id="c990c-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="c990c-111">Consulte o script de exemplo MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="c990c-112">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets da webconferência no Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="c990c-113">Configurando a política de contatos</span><span class="sxs-lookup"><span data-stu-id="c990c-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="c990c-114">Confira o exemplo ContactsPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="c990c-115">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets de presença e im no Lync server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="c990c-116">Configurando a política de Federação</span><span class="sxs-lookup"><span data-stu-id="c990c-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="c990c-117">Confira o exemplo FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="c990c-118">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do servidor de borda no Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) e [cmdlets de acesso externo e de Federação no Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="c990c-119">Configurando a política de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="c990c-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="c990c-120">Confira o exemplo BandwidthPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="c990c-121">Para obter detalhes, consulte o artigo [visão geral da documentação do Lync server 2013 do controle de admissão de chamadas no Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) e a ajuda do cmdlet para os [cmdlets do controle de admissão de chamadas no Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="c990c-122">Configurando as regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="c990c-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="c990c-123">Confira o exemplo RoutingRules. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="c990c-124">Ao configurar as regras de roteamento de voz, anote o contexto de telefone (ou seja,/Location perfil ou/SimpleName) e códigos de área interna/externa para que você possa especificá-los ao criar usuários e durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="c990c-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="c990c-125">Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo de RoutingRules. ps1 deve ser usado para o valor LocationProfile na seguinte figura de UserProfileGenerator. exe.</span><span class="sxs-lookup"><span data-stu-id="c990c-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="c990c-126">![Exemplo de regra de roteamento de voz.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Exemplo de regra de roteamento de voz.")</span><span class="sxs-lookup"><span data-stu-id="c990c-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="c990c-127">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="c990c-128">Configurando aplicativo de atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="c990c-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="c990c-129">Confira o exemplo ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="c990c-130">Anote o número de telefone do ConferencingAutoAttendant (1121111111, por padrão), para que você possa digitá-lo na ferramenta de configuração da ferramenta LyncPerf para geração de configuração.</span><span class="sxs-lookup"><span data-stu-id="c990c-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="c990c-131">![Configurando o aplicativo de atendedor de conferência](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurando o aplicativo de atendedor de conferência")</span><span class="sxs-lookup"><span data-stu-id="c990c-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="c990c-132">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets da webconferência no Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) e [cmdlets de conferência discada no Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="c990c-133">Configurando o serviço de estacionamento de chamada do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c990c-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="c990c-134">O estacionamento de chamadas está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c990c-134">Call Park is disabled by default.</span></span> <span data-ttu-id="c990c-135">Confira o exemplo CallParkConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="c990c-136">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo de estacionamento de chamada no Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c990c-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="c990c-137">Configurando chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="c990c-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="c990c-138">Execute as seguintes etapas para configurar o estresse e o teste de desempenho para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="c990c-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="c990c-139">Configurar uma rota de voz para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="c990c-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="c990c-140">Consulte o script RoutingRules. ps1 no comentário "Route E911 to PSTN" para obter um exemplo de como configurar essa rota de voz.</span><span class="sxs-lookup"><span data-stu-id="c990c-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c990c-141">O comando de exemplo em RoutingRules. ps1 tem um padrão de número que inclui o número 119 em vez de 911.</span><span class="sxs-lookup"><span data-stu-id="c990c-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="c990c-142">Você deve evitar o uso de 911 (ou seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga.</span><span class="sxs-lookup"><span data-stu-id="c990c-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="c990c-143">Essa configuração é apenas para fins de simulação.</span><span class="sxs-lookup"><span data-stu-id="c990c-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="c990c-144">Configure endereços preenchendo os valores na guia **Lis** no UserProvisioningTool, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c990c-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="c990c-145">![Configurando o serviço de informações de local.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurando o serviço de informações de local.")</span><span class="sxs-lookup"><span data-stu-id="c990c-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="c990c-146">Clique em **gerar arquivos de configuração de Lis**.</span><span class="sxs-lookup"><span data-stu-id="c990c-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="c990c-147">Arquivos CSV para portas, sub-redes, comutadores e pontos de acesso sem fio (WAPs) e um arquivo XML para a ferramenta de estresse e desempenho do Lync Server 2013, são gerados.</span><span class="sxs-lookup"><span data-stu-id="c990c-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="c990c-148">Os arquivos CSV devem ser usados como entradas (na mesma pasta) ao configurar o serviço de informações de local (LIS) com o script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="c990c-149">Mova o arquivo Locations0. XML gerado para a mesma pasta que o executável da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool. exe), que executará cenários de perfil de local (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="c990c-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="c990c-150">Criar, habilitar, configurar e desabilitar usuários</span><span class="sxs-lookup"><span data-stu-id="c990c-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="c990c-151">Você deve criar todos os seus usuários antes de executar os scripts a seguir.</span><span class="sxs-lookup"><span data-stu-id="c990c-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="c990c-152">Siga as instruções em [criar usuários e contatos](create-users-and-contacts.md) para criar usuários.</span><span class="sxs-lookup"><span data-stu-id="c990c-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="c990c-153">Para obter detalhes, consulte a documentação do cmdlet do Lync Server 2013 para os cmdlets [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="c990c-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="c990c-154">Configurando o aplicativo de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c990c-154">Configuring Response Group application</span></span>

<span data-ttu-id="c990c-155">Confira o exemplo ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="c990c-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="c990c-156">Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo grupo de resposta no Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Para revisar a configuração do aplicativo grupo `https://<poolfqdn>/RgsConfig/`de resposta, consulte, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="c990c-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="c990c-157">![A ferramenta de configuração do grupo de resposta.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "A ferramenta de configuração do grupo de resposta.")</span><span class="sxs-lookup"><span data-stu-id="c990c-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

