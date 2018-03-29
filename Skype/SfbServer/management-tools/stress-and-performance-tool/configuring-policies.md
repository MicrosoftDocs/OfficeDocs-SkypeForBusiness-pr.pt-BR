---
title: Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuração de diretiva para Skype em ferramenta de desempenho e estresse do Business Server 2015.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2ed87-103">Configurando políticas para o Skype para Business Server 2015 ferramenta de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="2ed87-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="2ed87-104">Configuração de diretiva para Skype em ferramenta de desempenho e estresse do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2ed87-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="2ed87-105">Há várias políticas e outras áreas que você pode configurar no Skype para negócios 2015 do servidor, antes de executar a ferramenta de Stress e desempenho:</span><span class="sxs-lookup"><span data-stu-id="2ed87-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="2ed87-106">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="2ed87-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="2ed87-107">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="2ed87-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="2ed87-108">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="2ed87-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="2ed87-109">Política de Federação</span><span class="sxs-lookup"><span data-stu-id="2ed87-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="2ed87-110">Política de controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="2ed87-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="2ed87-111">Regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="2ed87-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="2ed87-112">Aplicativo Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="2ed87-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="2ed87-113">Serviço estacionamento de chamada do servidor</span><span class="sxs-lookup"><span data-stu-id="2ed87-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="2ed87-114">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="2ed87-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="2ed87-115">Configurando o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="2ed87-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="2ed87-116">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="2ed87-116">Archiving policy</span></span>
<span data-ttu-id="2ed87-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-117"></span></span>

<span data-ttu-id="2ed87-118">Se você tiver um servidor de arquivamento implantado em sua Skype para topologia de servidores corporativos, você pode examinar o script ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="2ed87-119">Se você precisar de mais ajuda, confira os cmdlets de arquivamento e de webconferência.</span><span class="sxs-lookup"><span data-stu-id="2ed87-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="2ed87-120">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="2ed87-120">Conferencing policy</span></span>
<span data-ttu-id="2ed87-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-121"></span></span>

<span data-ttu-id="2ed87-122">Para conferências, temos o script MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="2ed87-123">Se você precisar de mais ajuda, confira os cmdlets de webconferência.</span><span class="sxs-lookup"><span data-stu-id="2ed87-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="2ed87-124">Política de contatos</span><span class="sxs-lookup"><span data-stu-id="2ed87-124">Contacts policy</span></span>
<span data-ttu-id="2ed87-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-125"></span></span>

<span data-ttu-id="2ed87-126">Script de ContactsPolicy.ps1 será a amostra, que você precisará analisar.</span><span class="sxs-lookup"><span data-stu-id="2ed87-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="2ed87-127">Os cmdlets IM e presença ajudará a se precisar de mais referências.</span><span class="sxs-lookup"><span data-stu-id="2ed87-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="2ed87-128">Política de Federação</span><span class="sxs-lookup"><span data-stu-id="2ed87-128">Federation policy</span></span>
<span data-ttu-id="2ed87-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-129"></span></span>

<span data-ttu-id="2ed87-130">O script de exemplo para federação é FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="2ed87-131">Os cmdlets para revisar, se você precisar de mais insight, será o servidor de borda, Federação e acesso externo.</span><span class="sxs-lookup"><span data-stu-id="2ed87-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="2ed87-132">Política de controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="2ed87-132">Call Admission Control policy</span></span>
<span data-ttu-id="2ed87-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-133"></span></span>

<span data-ttu-id="2ed87-134">É possível fazer referência BandwidthPolicy.ps1 para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="2ed87-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="2ed87-135">Os cmdlets de controle de admissão de chamada têm outras informações também.</span><span class="sxs-lookup"><span data-stu-id="2ed87-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="2ed87-136">Regras de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="2ed87-136">Voice Routing rules</span></span>
<span data-ttu-id="2ed87-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-137"></span></span>

<span data-ttu-id="2ed87-138">Você precisará o script de exemplo RoutingRules.ps1 para roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="2ed87-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="2ed87-139">Quando você estiver configurando estas regras, tome nota do contexto de telefone (ou seja, /Location perfil ou /SimpleName) e os códigos de área interno ou externo, para que você possa especificá-los durante a criação de usuários.</span><span class="sxs-lookup"><span data-stu-id="2ed87-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="2ed87-140">Você também precisará-los durante a configuração de LyncPerfTool (especificamente para UC-PSTN e UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="2ed87-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="2ed87-141">Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules.ps1 deve ser usado para o valor de LocationProfile na figura a seguir de UserProfileGenerator.exe:</span><span class="sxs-lookup"><span data-stu-id="2ed87-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Ferramenta de configuração de carga do Skype for Business, guia de cenários de voz, configurações avançadas para as Conversas.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="2ed87-143">Para obter detalhes, você pode revisar os cmdlets do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2ed87-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="2ed87-144">Aplicativo Atendedor de conferência</span><span class="sxs-lookup"><span data-stu-id="2ed87-144">Conference Attendant application</span></span>
<span data-ttu-id="2ed87-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-145"></span></span>

<span data-ttu-id="2ed87-146">Primeiro, revise o script ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="2ed87-147">Você vai querer tome nota do número de telefone ConferencingAutoAttendant (1121111111 por padrão), para que você pode inseri-lo na ferramenta de configuração de LyncPerfTool para geração de configuração, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ed87-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![O guia de cenários de voz que mostra o nível de carga da conferência e o número de telefone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="2ed87-149">Você encontrará mais detalhes na conferência discada e conferência cmdlets.</span><span class="sxs-lookup"><span data-stu-id="2ed87-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="2ed87-150">Serviço estacionamento de chamada do servidor</span><span class="sxs-lookup"><span data-stu-id="2ed87-150">Server Call Park service</span></span>
<span data-ttu-id="2ed87-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-151"></span></span>

<span data-ttu-id="2ed87-152">Isso realmente é desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2ed87-152">This is actually disabled by default.</span></span> <span data-ttu-id="2ed87-153">Você pode revisar o script de exemplo CallParkConfiguration.ps1 se precisar testar isso.</span><span class="sxs-lookup"><span data-stu-id="2ed87-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="2ed87-154">Além disso, confira os cmdlets do aplicativo de estacionamento de chamada conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2ed87-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="2ed87-155">Chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="2ed87-155">Emergency calls</span></span>
<span data-ttu-id="2ed87-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-156"></span></span>

<span data-ttu-id="2ed87-157">Você precisará executar as seguintes etapas para configurar os testes para chamadas de emergência de desempenho e estresse:</span><span class="sxs-lookup"><span data-stu-id="2ed87-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="2ed87-158">Configure uma rota de voz para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="2ed87-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="2ed87-159">Você pode usar o script RoutingRules.ps1 e verificar sob o comentário " **E911 rota para PSTN** " para obter um exemplo de como configurar esta rota de voz.</span><span class="sxs-lookup"><span data-stu-id="2ed87-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="2ed87-160">O comando de exemplo no RoutingRules.ps1 tem um padrão de número que inclui o número 119 ao invés 911.</span><span class="sxs-lookup"><span data-stu-id="2ed87-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="2ed87-161">Evite usar 911 (ou seu número de emergência local real) para evitar acidentais chamadas para os operadores de emergências locais durante seu teste de carga.</span><span class="sxs-lookup"><span data-stu-id="2ed87-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="2ed87-162">Lembre-se de que essa configuração é apenas para fins de simulação!</span><span class="sxs-lookup"><span data-stu-id="2ed87-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="2ed87-163">Configure endereços ao preencher os valores na guia **Configuração do serviço de informações de local** no UserProvisioningTool, conforme mostrado na figura a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ed87-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Ferramenta de provisionamento do usuário que mostra o número de endereços, sub-redes, comutadores e portas.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="2ed87-165">Quando você inseriu tudo para o UserProvisioningTool, clique no botão de **Gerar arquivos de configuração do LIS** .</span><span class="sxs-lookup"><span data-stu-id="2ed87-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="2ed87-166">Agora arquivos CSV para portas, sub-redes, comutadores e pontos de acesso sem fio (WAPs), bem como um arquivo XML para a ferramenta de Stress e desempenho será gerado.</span><span class="sxs-lookup"><span data-stu-id="2ed87-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="2ed87-167">Você pode usar os arquivos CSV para entradas ao configurar o serviço de informações de local (LIS) com o script LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="2ed87-168">Para fazer isso, você precisará mover o arquivo de Locations0.xml na mesma pasta como a ferramenta de Stress e desempenho executável (LyncPerfTool.exe).</span><span class="sxs-lookup"><span data-stu-id="2ed87-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="2ed87-169">Isso permitirá que você execute cenários (plano de discagem) de perfil de local.</span><span class="sxs-lookup"><span data-stu-id="2ed87-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="2ed87-170">Configurando o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="2ed87-170">Configuring Response Group application</span></span>
<span data-ttu-id="2ed87-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="2ed87-171"></span></span>

<span data-ttu-id="2ed87-172">O exemplo de script é ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="2ed87-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="2ed87-173">Também há cmdlets do aplicativo de grupo de resposta para analisar para obter mais detalhes de configuração.</span><span class="sxs-lookup"><span data-stu-id="2ed87-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="2ed87-174">O diagrama a seguir mostrará alguns dos detalhes de configuração:</span><span class="sxs-lookup"><span data-stu-id="2ed87-174">The following diagram will show some of the configuration details:</span></span>
  
![A ferramenta de configuração do Grupo de Resposta que mostra os fluxos de trabalho existentes para testes.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

