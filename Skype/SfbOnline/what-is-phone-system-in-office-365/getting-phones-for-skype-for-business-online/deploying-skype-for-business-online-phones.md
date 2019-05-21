---
title: Implantando telefones do Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba quais são as etapas de implantação para obter o firmware correto, atualize-o, se necessário, atribua licenças e defina as configurações para telefones do Skype for Business Online
ms.openlocfilehash: 1e83c240b5406fbb3e7a247200d2b38d74ba8ef5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298004"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="029be-103">Implantando telefones do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="029be-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="029be-104">Este guia de implantação vai ajudá-lo a implantar os telefones IP do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="029be-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="029be-105">Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é uma exigência importante para fazer negócios.</span><span class="sxs-lookup"><span data-stu-id="029be-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="029be-106">Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os dispositivos Skype for Business, incluindo telefones IP, computadores e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="029be-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="029be-107">Você pode saber mais sobre os telefones IP do Skype for Business lendo [obtendo telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="029be-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="029be-108">Etapas de implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="029be-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="029be-109">Etapa 1-baixar os guias do administrador e os manuais do telefone do fabricante</span><span class="sxs-lookup"><span data-stu-id="029be-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="029be-110">Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e os manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="029be-111">Para telefones Polycom, consulte o [Guia de implantação do Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="029be-111">For Polycom phones, see the [Polycom Deployment Guide](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="029be-112">Para telefones Yealink, consulte a [solução Yealink Skype for Business HD SIP phones](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="029be-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="029be-113">Para telefones AudioCodes, consulte o [Guia de gerenciamento de provisionamento do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="029be-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="029be-114">Etapa 2: Verifique se você está comprando ou migrando um telefone IP e firmware compatíveis com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="029be-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="029be-115">Um telefone e firmware compatíveis com o Skype for Business online também são compatíveis com o Skype for Business Server, mas o oposto não é sempre verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="029be-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="029be-116">Para verificar se você está comprando ou provisionando um número de telefone e um firmware com suporte, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="029be-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="029be-117">Etapa 3-verificando se o firmware correto está instalado e atualize o firmware, se necessário</span><span class="sxs-lookup"><span data-stu-id="029be-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="029be-118">Verifique a versão do firmware em seus telefones.</span><span class="sxs-lookup"><span data-stu-id="029be-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="029be-119">De</span><span class="sxs-lookup"><span data-stu-id="029be-119">For:</span></span>
  
- <span data-ttu-id="029be-120">**Polycom VVX**, vá para **configurações** > **status** > \*\*\*\* > **aplicativo** > plataforma**principal**.</span><span class="sxs-lookup"><span data-stu-id="029be-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="029be-121">**Telefones Yealink**, vá até **status** na tela principal do telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="029be-122">**Telefones AudioCodes**, vá para **menu** > \*\*\*\* > **versão firmware** do status do dispositivo na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="029be-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="029be-123">Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="029be-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="029be-124">Veja os links acima para os guias do usuário e os manuais do telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="029be-125">**Lync Phone Edition (LPe) phones**, vá para o **menu** > **informações do sistema** na tela iniciar.</span><span class="sxs-lookup"><span data-stu-id="029be-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="029be-126">Etapa 4-considerações sobre atualização de dispositivos</span><span class="sxs-lookup"><span data-stu-id="029be-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="029be-127">O firmware do Polycom antes do 5.5.1. X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por um "Phone-Lock" de implementação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="029be-128">A atualização de um telefone de 5.4. X. X que foi protegido com "Device-Lock" como 5.5.1. X com "Phone-Lock" não herdará o código PIN de "Device-Lock", o que pode deixar o telefone desprotegido.</span><span class="sxs-lookup"><span data-stu-id="029be-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="029be-129">Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro de perfil de dispositivo Polycom para dar aos usuários o controle do tempo de atualização (Lync. deviceUpdate. popUpSK. Enabled = 1).</span><span class="sxs-lookup"><span data-stu-id="029be-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="029be-130">As atualizações de firmware são gerenciadas pelo serviço Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="029be-131">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="029be-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="029be-132">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente as compilações certificadas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="029be-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="029be-133">Você pode desativar as configurações de atualização de dispositivo usando o cmdlet [set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo __ o parâmetro EnableDeviceUpdate `false`como.</span><span class="sxs-lookup"><span data-stu-id="029be-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Implantação de telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="029be-135">Quando um novo firmware estiver disponível e estiver pronto para download e instalação, o telefone notificará o usuário.</span><span class="sxs-lookup"><span data-stu-id="029be-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="029be-136">Os telefones Polycom notificarão o usuário e fornecerão uma opção para **Atualizar** ou **adiar**o usuário.</span><span class="sxs-lookup"><span data-stu-id="029be-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Implantação de telefones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="029be-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="029be-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Implantação de telefones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="029be-140">Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros.</span><span class="sxs-lookup"><span data-stu-id="029be-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="029be-141">Para gerenciamento de sistema de provisionamento de parceiros, incluindo personalização de telefone avançada, consulte guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="029be-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="029be-142">Verifique se você tem uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="029be-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="029be-143">Etapa 5-configurações e configurações de telefone de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="029be-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="029be-144">Você pode configurar as opções de telefone mais usadas e políticas usando cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="029be-145">Consulte [set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="029be-145">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="029be-146">Para o planejamento de infraestrutura de rede, consulte a [estrutura de operações do Skype](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="029be-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="029be-147">Etapa 6 – preparando para os usuários entrarem</span><span class="sxs-lookup"><span data-stu-id="029be-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="029be-148">Para permitir que os usuários se conectem com êxito a um telefone do Skype for Business Online e façam chamadas, você precisa ter certeza de que os usuários receberam as licenças corretas.</span><span class="sxs-lookup"><span data-stu-id="029be-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="029be-149">No mínimo, você precisará atribuir uma licença do sistema de telefonia e um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="029be-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="029be-150">Para obter informações adicionais, você pode ver [Licenciamento do complemento do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [atribuir licenças do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="029be-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="029be-151">Você pode saber mais sobre os planos de chamadas lendo [sistema telefônico e planos de chamada](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="029be-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="029be-152">**As opções de entrada** que estão disponíveis para usuários online são:</span><span class="sxs-lookup"><span data-stu-id="029be-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="029be-153">Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Implantação de telefones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="029be-155">Os usuários com os telefones **YEALINK T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="029be-157">Para obter detalhes sobre as opções de entrada aceitas pelo fabricante, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="029be-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="029be-158">**ID de usuário** Usando o teclado numérico do telefone ou o teclado virtual (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="029be-159">Por exemplo, eles devem usar o formato UPN, como <em>amosm@contoso.com</em> para o nome de usuário dele.</span><span class="sxs-lookup"><span data-stu-id="029be-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Implantação de telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="029be-161">Não há suporte para a autenticação de PIN no Skype for Business online para LPE e telefones IP de parceiros.</span><span class="sxs-lookup"><span data-stu-id="029be-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="029be-162">**Usando um computador** Quando o software da Ethernet (BToE) melhor está instalado no computador do usuário e habilitado, os usuários podem entrar em seus telefones usando a janela de autenticação no aplicativo Windows Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="029be-163">Veja [a etapa 7 (opcional)-se você tiver o emparelhamento de dispositivos e melhor em conjunto com a Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.</span><span class="sxs-lookup"><span data-stu-id="029be-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="029be-164">Os usuários precisam usar o nome de usuário e a senha da organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="029be-165">Por exemplo, eles devem usar o formato UPN, como <em>amosm@contoso.com</em> para o nome de usuário dele.</span><span class="sxs-lookup"><span data-stu-id="029be-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Implantação de telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="029be-167">**Usando uma entrada na Web**: essa é uma nova maneira de os usuários online se autenticarem usando um navegador da Web padrão.</span><span class="sxs-lookup"><span data-stu-id="029be-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="029be-168">Os usuários serão fornecidos com um conjunto de instruções a serem seguidas quando usarem um navegador para entrar.</span><span class="sxs-lookup"><span data-stu-id="029be-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="029be-169">Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Implantação de telefones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="029be-171">Os usuários com os telefones **YEALINK T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink logon no telefone.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="029be-173">O código gerado irá expirar em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="029be-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="029be-174">Quando ele expirar, o usuário terá que clicar em **repetir** ou em **OK** para gerar um novo código, dependendo do telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="029be-175">Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Código PIN expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="029be-177">Os usuários com os telefones **YEALINK T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="029be-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="029be-179">Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome de usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Implantação de telefones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="029be-181">Digite o código exibido no telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-181">Enter the code shown on the phone.</span></span>
    
     ![Implantação de telefones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="029be-183">Verifique se o site mostra "[nome do fabricante do telefone] **telefone certificado pelo Skype for Business**" e clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="029be-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Implantação de telefones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="029be-185">Clique nas credenciais do usuário ou clique em **usar outra conta**:</span><span class="sxs-lookup"><span data-stu-id="029be-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Implantação de telefones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="029be-187">Quando a página a seguir é exibida, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="029be-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Implantação de telefones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="029be-189">Telefones LPE para suporte do Skype for Business online com o compartilhamento somente para compartilhamento por USB.</span><span class="sxs-lookup"><span data-stu-id="029be-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="029be-190">**Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação com suporte no momento, incluindo integração com o Exchange, autenticação moderna com autenticação multifator (MFA) e Skype for Business Online e local.</span><span class="sxs-lookup"><span data-stu-id="029be-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="029be-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="029be-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="029be-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="029be-192">**Exchange**</span></span> <br/> |<span data-ttu-id="029be-193">**Método de entrada no telefone**</span><span class="sxs-lookup"><span data-stu-id="029be-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="029be-194">**Acesso ao Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="029be-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="029be-195">**Acesso do Exchange com autenticação moderna e MFA desabilitadas**</span><span class="sxs-lookup"><span data-stu-id="029be-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="029be-196">**Acesso do Exchange com autenticação moderna e MFA habilitados**</span><span class="sxs-lookup"><span data-stu-id="029be-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="029be-197">Online</span><span class="sxs-lookup"><span data-stu-id="029be-197">Online</span></span>  <br/> |<span data-ttu-id="029be-198">Online</span><span class="sxs-lookup"><span data-stu-id="029be-198">Online</span></span>  <br/> |<span data-ttu-id="029be-199">Entrada na Web</span><span class="sxs-lookup"><span data-stu-id="029be-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="029be-200">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-200">Yes</span></span>  <br/> |<span data-ttu-id="029be-201">Sim </span><span class="sxs-lookup"><span data-stu-id="029be-201">Yes</span></span>  <br/> |<span data-ttu-id="029be-202">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-202">Yes</span></span>  <br/> |
|<span data-ttu-id="029be-203">Online</span><span class="sxs-lookup"><span data-stu-id="029be-203">Online</span></span>  <br/> |<span data-ttu-id="029be-204">Online</span><span class="sxs-lookup"><span data-stu-id="029be-204">Online</span></span>  <br/> |<span data-ttu-id="029be-205">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="029be-205">Username/Password</span></span>  <br/> |<span data-ttu-id="029be-206">Sim </span><span class="sxs-lookup"><span data-stu-id="029be-206">Yes</span></span>  <br/> |<span data-ttu-id="029be-207">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-207">Yes</span></span>  <br/> |<span data-ttu-id="029be-208">Não</span><span class="sxs-lookup"><span data-stu-id="029be-208">No</span></span>  <br/> |
|<span data-ttu-id="029be-209">Online</span><span class="sxs-lookup"><span data-stu-id="029be-209">Online</span></span>  <br/> |<span data-ttu-id="029be-210">Local</span><span class="sxs-lookup"><span data-stu-id="029be-210">On-premises</span></span>  <br/> |<span data-ttu-id="029be-211">Entrada na Web</span><span class="sxs-lookup"><span data-stu-id="029be-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="029be-212">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-212">Yes</span></span>  <br/> |<span data-ttu-id="029be-213">Não</span><span class="sxs-lookup"><span data-stu-id="029be-213">No</span></span>  <br/> |<span data-ttu-id="029be-214">Não</span><span class="sxs-lookup"><span data-stu-id="029be-214">No</span></span>  <br/> |
|<span data-ttu-id="029be-215">Online</span><span class="sxs-lookup"><span data-stu-id="029be-215">Online</span></span>  <br/> |<span data-ttu-id="029be-216">Local</span><span class="sxs-lookup"><span data-stu-id="029be-216">On-Premises</span></span>  <br/> |<span data-ttu-id="029be-217">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="029be-217">Username/Password</span></span>  <br/> |<span data-ttu-id="029be-218">Sim </span><span class="sxs-lookup"><span data-stu-id="029be-218">Yes</span></span>  <br/> |<span data-ttu-id="029be-219">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-219">Yes</span></span>  <br/> |<span data-ttu-id="029be-220">Não</span><span class="sxs-lookup"><span data-stu-id="029be-220">No</span></span>  <br/> |
|<span data-ttu-id="029be-221">Local</span><span class="sxs-lookup"><span data-stu-id="029be-221">On-premises</span></span>  <br/> |<span data-ttu-id="029be-222">Online/local</span><span class="sxs-lookup"><span data-stu-id="029be-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="029be-223">Autenticação de PIN</span><span class="sxs-lookup"><span data-stu-id="029be-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="029be-224">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-224">Yes</span></span>  <br/> |<span data-ttu-id="029be-225">Não</span><span class="sxs-lookup"><span data-stu-id="029be-225">No</span></span>  <br/> |<span data-ttu-id="029be-226">Não</span><span class="sxs-lookup"><span data-stu-id="029be-226">No</span></span>  <br/> |
|<span data-ttu-id="029be-227">Local</span><span class="sxs-lookup"><span data-stu-id="029be-227">On-premises</span></span>  <br/> |<span data-ttu-id="029be-228">Online/local</span><span class="sxs-lookup"><span data-stu-id="029be-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="029be-229">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="029be-229">Username/Password</span></span>  <br/> |<span data-ttu-id="029be-230">Sim </span><span class="sxs-lookup"><span data-stu-id="029be-230">Yes</span></span>  <br/> |<span data-ttu-id="029be-231">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-231">Yes</span></span>  <br/> |<span data-ttu-id="029be-232">N/D</span><span class="sxs-lookup"><span data-stu-id="029be-232">N/A</span></span>  <br/> |
|<span data-ttu-id="029be-233">Local</span><span class="sxs-lookup"><span data-stu-id="029be-233">On-premises</span></span>  <br/> |<span data-ttu-id="029be-234">Online/local</span><span class="sxs-lookup"><span data-stu-id="029be-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="029be-235">Entrada via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="029be-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="029be-236">Sim </span><span class="sxs-lookup"><span data-stu-id="029be-236">Yes</span></span>  <br/> |<span data-ttu-id="029be-237">Sim</span><span class="sxs-lookup"><span data-stu-id="029be-237">Yes</span></span>  <br/> |<span data-ttu-id="029be-238">N/D</span><span class="sxs-lookup"><span data-stu-id="029be-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="029be-239">**Recursos de telefone** O conjunto de recursos pode variar um pouco de acordo com o parceiro de telefone IP.</span><span class="sxs-lookup"><span data-stu-id="029be-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="029be-240">Para obter o conjunto de recursos completo e obter mais informações sobre os recursos para cada fabricante de telefone, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="029be-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="029be-241">**Phone-Lock** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business que é usado para proteger um telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="029be-242">Se habilitada, os usuários serão solicitados a criar um PIN após uma autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="029be-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="029be-243">Após a criação, os telefones serão bloqueados quando o tempo limite ocioso definido expirar, um usuário bloqueará manualmente o telefone ou sincronizará seus telefones com o bloqueio do computador usando o emparelhamento por telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="029be-244">Se o PIN de bloqueio de telefone for digitado várias vezes, o telefone desconectará o usuário ou exigirá um código de administrador para desbloquear o telefone, mas isso varia de acordo com o parceiro de telefone.</span><span class="sxs-lookup"><span data-stu-id="029be-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="029be-245">O PIN do usuário deve ter entre 6 e 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="029be-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="029be-246">Você pode desativar o bloqueio de telefone para sua organização (que é habilitado por padrão), alterar o tempo limite de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto estiverem bloqueados ou não usando as configurações de inband.</span><span class="sxs-lookup"><span data-stu-id="029be-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="029be-247">Consulte [set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter mais detalhes sobre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="029be-247">See [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="029be-248">Etapa 7 (opcional)-se você tiver o emparelhamento de dispositivos e melhor em conjunto com a Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="029be-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="029be-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="029be-249"></span></span>

<span data-ttu-id="029be-250">BToE é um mecanismo de inatividade do telefone para telefones IP do parceiro que emparelham o telefone de um usuário com o aplicativo do Windows Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="029be-251">O BToE permite que os usuários:</span><span class="sxs-lookup"><span data-stu-id="029be-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="029be-252">Entre em seu telefone IP usando o aplicativo da área de trabalho do Skype for Business (usando um PC)</span><span class="sxs-lookup"><span data-stu-id="029be-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="029be-253">Sincronizar o telefone-bloquear com o bloqueio do computador</span><span class="sxs-lookup"><span data-stu-id="029be-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="029be-254">Clicar para chamar</span><span class="sxs-lookup"><span data-stu-id="029be-254">Click to call</span></span>
    
<span data-ttu-id="029be-255">O BToE pode ser configurado para operar em dois modos: *automático* (padrão) e *manual* .</span><span class="sxs-lookup"><span data-stu-id="029be-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="029be-256">Ele também pode ser habilitado (padrão)/Disabled para usuários que usam as configurações em banda do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="029be-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="029be-257">Ao operar no modo *manual* , os usuários precisarão fazer uma etapa adicional para emparelhar o telefone com o aplicativo do Windows.</span><span class="sxs-lookup"><span data-stu-id="029be-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="029be-258">**Para implantar o BToE para os usuários**</span><span class="sxs-lookup"><span data-stu-id="029be-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="029be-259">Conecte o computador ao telefone usando a porta do computador.</span><span class="sxs-lookup"><span data-stu-id="029be-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Implantação de telefones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="029be-261">Baixe e instale o software BToE mais recente do website do fabricante nos links abaixo.</span><span class="sxs-lookup"><span data-stu-id="029be-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="029be-262">Para melhorar a experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração, como o System Center Configuration Manager (SCCM).</span><span class="sxs-lookup"><span data-stu-id="029be-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM).</span></span> <span data-ttu-id="029be-263">Para obter ajuda sobre como usar o SCCM, consulte [pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="029be-263">For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="029be-264">Site de download de software do Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="029be-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="029be-265">Download de software do Yealink BToE</span><span class="sxs-lookup"><span data-stu-id="029be-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="029be-266">Downloads de software do AudioCodes BToE</span><span class="sxs-lookup"><span data-stu-id="029be-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="029be-267">A configuração do servidor para BToE é definida como **Enabled** e **modo automático** por padrão.</span><span class="sxs-lookup"><span data-stu-id="029be-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="029be-268">Para alterar essas configurações, consulte [set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="029be-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="029be-269">BToE atualmente não é compatível com plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="029be-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="029be-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="029be-270">Related topics</span></span>
[<span data-ttu-id="029be-271">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="029be-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="029be-272">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="029be-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="029be-273">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="029be-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
