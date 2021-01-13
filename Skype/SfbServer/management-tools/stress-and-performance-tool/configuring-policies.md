---
title: Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuração de política para a Ferramenta de Stress and Performance do Skype for Business Server 2015.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815031"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="76606-103">Configurando políticas para a Ferramenta de Stress and Performance do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="76606-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="76606-104">Configuração de política para a Ferramenta de Stress and Performance do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="76606-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="76606-105">Há várias políticas e outras áreas que você pode configurar no Skype for Business Server 2015, antes de executar a Ferramenta de Stress and Performance:</span><span class="sxs-lookup"><span data-stu-id="76606-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="76606-106">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="76606-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="76606-107">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="76606-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="76606-108">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="76606-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="76606-109">Política de federação</span><span class="sxs-lookup"><span data-stu-id="76606-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="76606-110">Política de Controle de Admissão de Chamada</span><span class="sxs-lookup"><span data-stu-id="76606-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="76606-111">Regras de Roteamento de Voz</span><span class="sxs-lookup"><span data-stu-id="76606-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="76606-112">Aplicativo De atendimento de conferência</span><span class="sxs-lookup"><span data-stu-id="76606-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="76606-113">Serviço Estacionamento de Chamada do Servidor</span><span class="sxs-lookup"><span data-stu-id="76606-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="76606-114">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="76606-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="76606-115">Configurando o aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="76606-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="76606-116">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="76606-116">Archiving policy</span></span>
<span data-ttu-id="76606-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="76606-118">Se você tiver um servidor de Arquivamento implantado em sua topologia do Skype for Business Server, poderá ver o ArchivingPolicy.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="76606-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="76606-119">Se precisar de mais ajuda, confira os cmdlets de Arquivamento e Webconferência.</span><span class="sxs-lookup"><span data-stu-id="76606-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="76606-120">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="76606-120">Conferencing policy</span></span>
<span data-ttu-id="76606-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="76606-122">Para conferência, temos o script MeetingPolicy.ps1 aplicativo.</span><span class="sxs-lookup"><span data-stu-id="76606-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="76606-123">Se precisar de mais ajuda, confira os cmdlets de Webconferência.</span><span class="sxs-lookup"><span data-stu-id="76606-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="76606-124">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="76606-124">Contacts policy</span></span>
<span data-ttu-id="76606-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="76606-126">ContactsPolicy.ps1 script será o exemplo que você precisará analisar.</span><span class="sxs-lookup"><span data-stu-id="76606-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="76606-127">Os cmdlets de IM e presença ajudarão se você precisar de mais referências.</span><span class="sxs-lookup"><span data-stu-id="76606-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="76606-128">Política de federação</span><span class="sxs-lookup"><span data-stu-id="76606-128">Federation policy</span></span>
<span data-ttu-id="76606-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="76606-130">O script de exemplo para federação é FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="76606-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="76606-131">Os cmdlets a serem revisados, se você precisar de mais informações, serão Servidor de Borda, federação e acesso externo.</span><span class="sxs-lookup"><span data-stu-id="76606-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="76606-132">Política de Controle de Admissão de Chamada</span><span class="sxs-lookup"><span data-stu-id="76606-132">Call Admission Control policy</span></span>
<span data-ttu-id="76606-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="76606-134">Você pode fazer referência BandwidthPolicy.ps1 para essa política.</span><span class="sxs-lookup"><span data-stu-id="76606-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="76606-135">Os cmdlets de Controle de Admissão de Chamada também terão mais informações.</span><span class="sxs-lookup"><span data-stu-id="76606-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="76606-136">Regras de Roteamento de Voz</span><span class="sxs-lookup"><span data-stu-id="76606-136">Voice Routing rules</span></span>
<span data-ttu-id="76606-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="76606-138">Você precisará do script de RoutingRules.ps1 para Roteamento de Voz.</span><span class="sxs-lookup"><span data-stu-id="76606-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="76606-139">Ao configurar essas regras, anote o contexto do telefone (ou seja, /Location Profile ou /SimpleName) e os Códigos de Área Interna/Externa para que você possa especificá-las ao criar usuários.</span><span class="sxs-lookup"><span data-stu-id="76606-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="76606-140">Você também precisará deles durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="76606-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="76606-141">Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules.ps1 deve ser usado para o valor LocationProfile na seguinte figura de UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="76606-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Ferramenta de configuração de carga do Skype for Business, guia cenários de voz, Configurações avançadas para conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="76606-143">Para obter detalhes, você pode revisar os cmdlets do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="76606-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="76606-144">Aplicativo De atendimento de conferência</span><span class="sxs-lookup"><span data-stu-id="76606-144">Conference Attendant application</span></span>
<span data-ttu-id="76606-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="76606-146">Primeiro revise o ConferenceAutoAttendantConfiguration.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="76606-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="76606-147">Você vai querer anotar o número de telefone de ConferencingAutoAttendant (1121111111 por padrão), para que possa insira-o na ferramenta de configuração LyncPerfTool para geração de configuração, como abaixo:</span><span class="sxs-lookup"><span data-stu-id="76606-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![A guia Cenários de Voz mostrando o nível de Carga de Conferência e o número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="76606-149">Você encontrará mais detalhes nos cmdlets Conferência e Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="76606-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="76606-150">Serviço Estacionamento de Chamada do Servidor</span><span class="sxs-lookup"><span data-stu-id="76606-150">Server Call Park service</span></span>
<span data-ttu-id="76606-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="76606-152">Na verdade, isso é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="76606-152">This is actually disabled by default.</span></span> <span data-ttu-id="76606-153">Você pode revisar o CallParkConfiguration.ps1 script de exemplo se precisar testá-lo.</span><span class="sxs-lookup"><span data-stu-id="76606-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="76606-154">Além disso, confira os cmdlets do Aplicativo de Estacionamento de Chamada conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="76606-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="76606-155">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="76606-155">Emergency calls</span></span>
<span data-ttu-id="76606-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="76606-157">Você precisará executar as seguintes etapas para configurar testes de estresse e desempenho para chamadas de emergência:</span><span class="sxs-lookup"><span data-stu-id="76606-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="76606-158">Configurar uma rota de voz para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="76606-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="76606-159">Você pode usar o script RoutingRules.ps1 e verificar sob o comentário " **Route E911 to PSTN** " para ver um exemplo de como configurar essa rota de voz.</span><span class="sxs-lookup"><span data-stu-id="76606-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="76606-160">O comando de exemplo RoutingRules.ps1 tem um padrão de número que inclui o número 119 em vez de 911.</span><span class="sxs-lookup"><span data-stu-id="76606-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="76606-161">Evite usar 911 (ou seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga.</span><span class="sxs-lookup"><span data-stu-id="76606-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="76606-162">Lembre-se de que essa configuração é apenas para fins de simulação!</span><span class="sxs-lookup"><span data-stu-id="76606-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="76606-163">Configure os endereços preenchendo os valores na guia **Configuração** do Serviço de Informações de Local no UserProvisioningTool, conforme mostrado na figura a seguir:</span><span class="sxs-lookup"><span data-stu-id="76606-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Ferramenta de provisionamento do usuário mostrando o número de endereços, sub-redes, comutadores e portas.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="76606-165">Depois de ter inserido tudo no UserProvisioningTool, clique no **botão Gerar Arquivos de Configuração LIS.**</span><span class="sxs-lookup"><span data-stu-id="76606-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="76606-166">Agora, os arquivos CSV para portas, sub-redes, comutadores e WAPs (pontos de acesso sem fio), bem como um arquivo XML para a ferramenta Stress and Performance serão gerados.</span><span class="sxs-lookup"><span data-stu-id="76606-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="76606-167">Você pode usar os arquivos CSV para entradas ao configurar o LIS (Serviço de Informações de Local) com o script LisConfiguration.ps1 local.</span><span class="sxs-lookup"><span data-stu-id="76606-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="76606-168">Para fazer isso, você precisará mover o arquivo Locations0.xml para a mesma pasta que o executável da Ferramenta de Stress and Performance (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="76606-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="76606-169">Isso permitirá que você execute cenários de perfil de local (plano de discagem).</span><span class="sxs-lookup"><span data-stu-id="76606-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="76606-170">Configurando o aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="76606-170">Configuring Response Group application</span></span>
<span data-ttu-id="76606-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="76606-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="76606-172">O script de exemplo é ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="76606-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="76606-173">Também há cmdlets de aplicativo do Grupo de Resposta para revisar para obter mais detalhes de configuração.</span><span class="sxs-lookup"><span data-stu-id="76606-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="76606-174">O diagrama a seguir mostrará alguns dos detalhes da configuração:</span><span class="sxs-lookup"><span data-stu-id="76606-174">The following diagram will show some of the configuration details:</span></span>
  
![A ferramenta de configuração do Grupo de Resposta mostrando fluxos de trabalho existentes para teste.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

