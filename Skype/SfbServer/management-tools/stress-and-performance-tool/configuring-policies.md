---
title: Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuração de política para a ferramenta de stress e desempenho do Skype for Business Server 2015.
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299748"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="a1d01-103">Configurando políticas para a ferramenta de stress e desempenho do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1d01-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="a1d01-104">Configuração de política para a ferramenta de stress e desempenho do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a1d01-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="a1d01-105">Há várias políticas e outras áreas que você pode configurar no Skype for Business Server 2015, antes da execução da ferramenta de stress e desempenho:</span><span class="sxs-lookup"><span data-stu-id="a1d01-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="a1d01-106">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="a1d01-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="a1d01-107">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="a1d01-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="a1d01-108">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="a1d01-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="a1d01-109">Política de Federação</span><span class="sxs-lookup"><span data-stu-id="a1d01-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="a1d01-110">Política de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="a1d01-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="a1d01-111">Regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="a1d01-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="a1d01-112">Aplicativo de atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="a1d01-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="a1d01-113">Serviço de estacionamento de chamadas do servidor</span><span class="sxs-lookup"><span data-stu-id="a1d01-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="a1d01-114">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="a1d01-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="a1d01-115">Configurando o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="a1d01-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="a1d01-116">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="a1d01-116">Archiving policy</span></span>
<span data-ttu-id="a1d01-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-117"></span></span>

<span data-ttu-id="a1d01-118">Se você tiver um servidor de arquivamento implantado na topologia do Skype for Business Server, poderá examinar o script ArchivingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="a1d01-119">Se precisar de mais assistência, confira os cmdlets Archiving e Webconferência.</span><span class="sxs-lookup"><span data-stu-id="a1d01-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="a1d01-120">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="a1d01-120">Conferencing policy</span></span>
<span data-ttu-id="a1d01-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-121"></span></span>

<span data-ttu-id="a1d01-122">Para a conferência, temos o script MeetingPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="a1d01-123">Se precisar de mais assistência, confira os cmdlets da Webconferência.</span><span class="sxs-lookup"><span data-stu-id="a1d01-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="a1d01-124">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="a1d01-124">Contacts policy</span></span>
<span data-ttu-id="a1d01-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-125"></span></span>

<span data-ttu-id="a1d01-126">O script ContactsPolicy. ps1 será o exemplo que você precisará revisar.</span><span class="sxs-lookup"><span data-stu-id="a1d01-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="a1d01-127">Os cmdlets de presença e mensagens instantâneas ajudarão se você precisar de mais referências.</span><span class="sxs-lookup"><span data-stu-id="a1d01-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="a1d01-128">Política de Federação</span><span class="sxs-lookup"><span data-stu-id="a1d01-128">Federation policy</span></span>
<span data-ttu-id="a1d01-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-129"></span></span>

<span data-ttu-id="a1d01-130">O script de exemplo para Federação é FederationPolicy. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="a1d01-131">Os cmdlets a serem revisados, se você precisar de mais informações, será servidor de borda, Federação e acesso externo.</span><span class="sxs-lookup"><span data-stu-id="a1d01-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="a1d01-132">Política de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="a1d01-132">Call Admission Control policy</span></span>
<span data-ttu-id="a1d01-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-133"></span></span>

<span data-ttu-id="a1d01-134">Você pode fazer referência a BandwidthPolicy. ps1 para esta política.</span><span class="sxs-lookup"><span data-stu-id="a1d01-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="a1d01-135">Os cmdlets do controle de admissão de chamadas também terão outras informações.</span><span class="sxs-lookup"><span data-stu-id="a1d01-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="a1d01-136">Regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="a1d01-136">Voice Routing rules</span></span>
<span data-ttu-id="a1d01-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-137"></span></span>

<span data-ttu-id="a1d01-138">Você precisará do script de exemplo RoutingRules. ps1 para roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="a1d01-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="a1d01-139">Quando você estiver configurando essas regras, anote o contexto do telefone (ou seja, o perfil do/Location ou/SimpleName) e os códigos de área interna/externa, para que você possa especificá-los ao criar usuários.</span><span class="sxs-lookup"><span data-stu-id="a1d01-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="a1d01-140">Você também precisará deles durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="a1d01-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="a1d01-141">Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules. ps1 deve ser usado para o valor LocationProfile na seguinte imagem do UserProfileGenerator. exe:</span><span class="sxs-lookup"><span data-stu-id="a1d01-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Ferramenta de configuração de carregamento do Skype for Business, guia cenários de voz, configurações avançadas para conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="a1d01-143">Para obter detalhes, você pode examinar os cmdlets do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a1d01-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="a1d01-144">Aplicativo de atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="a1d01-144">Conference Attendant application</span></span>
<span data-ttu-id="a1d01-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-145"></span></span>

<span data-ttu-id="a1d01-146">Primeiro, examine o script ConferenceAutoAttendantConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="a1d01-147">Você desejará anotar o número de telefone ConferencingAutoAttendant (1121111111 por padrão), para que possa inseri-lo na ferramenta de configuração LyncPerfTool para geração de configuração, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="a1d01-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![A guia cenários de voz mostrando o nível de carga de conferência e o número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="a1d01-149">Você encontrará mais detalhes nos cmdlets de conferência discada e conferência.</span><span class="sxs-lookup"><span data-stu-id="a1d01-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="a1d01-150">Serviço de estacionamento de chamadas do servidor</span><span class="sxs-lookup"><span data-stu-id="a1d01-150">Server Call Park service</span></span>
<span data-ttu-id="a1d01-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-151"></span></span>

<span data-ttu-id="a1d01-152">Isso, na verdade, é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a1d01-152">This is actually disabled by default.</span></span> <span data-ttu-id="a1d01-153">Você pode examinar o script de exemplo CallParkConfiguration. ps1 se precisar testá-lo.</span><span class="sxs-lookup"><span data-stu-id="a1d01-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="a1d01-154">Além disso, confira os cmdlets do aplicativo de estacionamento de chamada conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a1d01-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="a1d01-155">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="a1d01-155">Emergency calls</span></span>
<span data-ttu-id="a1d01-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-156"></span></span>

<span data-ttu-id="a1d01-157">Você precisará executar as seguintes etapas para configurar o teste de carga e desempenho das chamadas de emergência:</span><span class="sxs-lookup"><span data-stu-id="a1d01-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="a1d01-158">Configurar uma rota de voz para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="a1d01-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="a1d01-159">Você pode usar o script RoutingRules. ps1 e verificar abaixo do comentário " **Route E911 to PSTN** " para obter um exemplo de como configurar essa rota de voz.</span><span class="sxs-lookup"><span data-stu-id="a1d01-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a1d01-160">O comando de exemplo em RoutingRules. ps1 tem um padrão de número que inclui o número 119 em vez de 911.</span><span class="sxs-lookup"><span data-stu-id="a1d01-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="a1d01-161">Você deve evitar usar o 911 (ou o seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga.</span><span class="sxs-lookup"><span data-stu-id="a1d01-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="a1d01-162">Lembre-se que essa configuração é somente para fins de simulação!</span><span class="sxs-lookup"><span data-stu-id="a1d01-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="a1d01-163">Para configurar endereços, preenchendo os valores na guia **configuração do serviço de informações de localização** no UserProvisioningTool, conforme mostrado na figura a seguir:</span><span class="sxs-lookup"><span data-stu-id="a1d01-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Ferramenta de provisionamento de usuário mostrando o número de endereços, sub-redes, opções e portas.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="a1d01-165">Quando você tiver inserido tudo no UserProvisioningTool, clique no botão **GENERATE Lis config files** .</span><span class="sxs-lookup"><span data-stu-id="a1d01-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="a1d01-166">Agora, os arquivos CSV para portas, sub-redes, opções e pontos de acesso sem fio (WAPs), bem como um arquivo XML para a ferramenta stress e performance serão gerados.</span><span class="sxs-lookup"><span data-stu-id="a1d01-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="a1d01-167">Você pode usar os arquivos CSV para entradas ao configurar o LIS (serviço de informações de localização) com o script LisConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="a1d01-168">Para fazer isso, você precisará mover o arquivo Locations0. xml para a mesma pasta que o executável da ferramenta de sobrecarga e de desempenho (LyncPerfTool. exe).</span><span class="sxs-lookup"><span data-stu-id="a1d01-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="a1d01-169">Isso permitirá que você execute cenários de perfil de localização (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="a1d01-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="a1d01-170">Configurando o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="a1d01-170">Configuring Response Group application</span></span>
<span data-ttu-id="a1d01-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="a1d01-171"></span></span>

<span data-ttu-id="a1d01-172">O script de exemplo é ResponseGroupConfiguration. ps1.</span><span class="sxs-lookup"><span data-stu-id="a1d01-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="a1d01-173">Também há cmdlets de aplicativo de grupo de resposta para analisar mais detalhes de configuração.</span><span class="sxs-lookup"><span data-stu-id="a1d01-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="a1d01-174">O diagrama a seguir mostrará alguns dos detalhes de configuração:</span><span class="sxs-lookup"><span data-stu-id="a1d01-174">The following diagram will show some of the configuration details:</span></span>
  
![A ferramenta de configuração do grupo de resposta mostrando fluxos de trabalho existentes para teste.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

