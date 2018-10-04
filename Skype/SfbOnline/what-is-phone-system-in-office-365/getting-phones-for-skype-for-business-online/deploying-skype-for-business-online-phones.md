---
title: Implantar telefones para o Skype for Business Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para Skype para telefones online de negócios
ms.openlocfilehash: 26748f79d62b2f4b40a249dcf1af1736bae2d06f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374568"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="43d86-103">Implantar telefones para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="43d86-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="43d86-104">Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="43d86-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="43d86-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span><span class="sxs-lookup"><span data-stu-id="43d86-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="43d86-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span><span class="sxs-lookup"><span data-stu-id="43d86-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="43d86-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="43d86-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="43d86-108">Etapas da implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="43d86-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="43d86-109">Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone</span><span class="sxs-lookup"><span data-stu-id="43d86-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="43d86-110">Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="43d86-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="43d86-111">Para telefones Polycom, consulte o [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="43d86-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="43d86-112">Para telefones Yealink, consulte [Yealink Skype para a solução de telefones SIP do negócios HD](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="43d86-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="43d86-113">Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="43d86-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="43d86-114">Etapa 2 - Certifique-se de que você está migrando para um telefone IP e firmware compatíveis com o Skype for Business ou adquirindo um assim.</span><span class="sxs-lookup"><span data-stu-id="43d86-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="43d86-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span><span class="sxs-lookup"><span data-stu-id="43d86-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="43d86-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="43d86-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="43d86-117">Etapa 3 - Verificar se o firmware certo foi instalado e atualizar o firmware, se necessário</span><span class="sxs-lookup"><span data-stu-id="43d86-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="43d86-118">Check the firmware version on your phones.</span><span class="sxs-lookup"><span data-stu-id="43d86-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="43d86-119">For:</span><span class="sxs-lookup"><span data-stu-id="43d86-119">For:</span></span>
  
- <span data-ttu-id="43d86-120">**Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="43d86-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="43d86-121">**Telefones Yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="43d86-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="43d86-122">**Telefones AudioCodes**, acesse **Menu** > **Status do Dispositivo** > **Versão do firmware** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="43d86-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="43d86-123">For remote access to phone details, refer to manufacturer administration guides.</span><span class="sxs-lookup"><span data-stu-id="43d86-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="43d86-124">See the links above for the user guides and phone manuals.</span><span class="sxs-lookup"><span data-stu-id="43d86-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="43d86-125">**Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="43d86-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="43d86-126">Etapa 4 - Considerações sobre atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="43d86-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="43d86-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span><span class="sxs-lookup"><span data-stu-id="43d86-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="43d86-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span><span class="sxs-lookup"><span data-stu-id="43d86-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="43d86-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="43d86-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="43d86-130">Firmware updates are managed by the Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="43d86-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="43d86-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="43d86-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="43d86-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span><span class="sxs-lookup"><span data-stu-id="43d86-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="43d86-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="43d86-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Implementar telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="43d86-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span><span class="sxs-lookup"><span data-stu-id="43d86-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="43d86-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span><span class="sxs-lookup"><span data-stu-id="43d86-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Implementar telefones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="43d86-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="43d86-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Implementar telefones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="43d86-p108">Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="43d86-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="43d86-142">[!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="43d86-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="43d86-143">Etapa 5 - configuração e definições de telefone de infra-estrutura</span><span class="sxs-lookup"><span data-stu-id="43d86-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="43d86-p109">Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="43d86-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="43d86-146">Para o planejamento da infra-estrutura de rede, consulte [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="43d86-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="43d86-147">Etapa 6 - Preparando os usuários entrem em</span><span class="sxs-lookup"><span data-stu-id="43d86-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="43d86-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span><span class="sxs-lookup"><span data-stu-id="43d86-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="43d86-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="43d86-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="43d86-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="43d86-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="43d86-151">Você pode encontrar mais informações sobre Planos de Chamadas em [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="43d86-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="43d86-152">As **opções de logon** que estão disponíveis para os usuários online são:</span><span class="sxs-lookup"><span data-stu-id="43d86-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="43d86-153">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Implementar telefones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="43d86-155">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="43d86-157">Para obter detalhes sobre as opções de entrar suportadas pelo fabricante, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="43d86-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="43d86-p111">**ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="43d86-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="43d86-161">[!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros.</span><span class="sxs-lookup"><span data-stu-id="43d86-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="43d86-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span><span class="sxs-lookup"><span data-stu-id="43d86-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="43d86-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="43d86-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="43d86-p113">[!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="43d86-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="43d86-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span><span class="sxs-lookup"><span data-stu-id="43d86-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="43d86-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span><span class="sxs-lookup"><span data-stu-id="43d86-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="43d86-169">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Implementar telefones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="43d86-171">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Logon de telefone Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="43d86-173">The code that is generated will expire in 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="43d86-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="43d86-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span><span class="sxs-lookup"><span data-stu-id="43d86-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="43d86-175">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Código PIN expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="43d86-177">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="43d86-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="43d86-179">Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="43d86-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Implementar telefones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="43d86-181">Digite o código mostrado no telefone.</span><span class="sxs-lookup"><span data-stu-id="43d86-181">Enter the code shown on the phone.</span></span>
    
     ![Implementar telefones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="43d86-183">Verifique se o site mostra "[nome do fabricante do telefone] **Skype para negócios Certified Phone**," e clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="43d86-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Implementar telefones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="43d86-185">Clique nas credenciais do usuário ou clique em **Usar outra conta**:</span><span class="sxs-lookup"><span data-stu-id="43d86-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Implementar telefones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="43d86-187">Quando for exibida a página seguinte, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="43d86-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Implementar telefones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="43d86-189">[!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB.</span><span class="sxs-lookup"><span data-stu-id="43d86-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="43d86-190">**Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.</span><span class="sxs-lookup"><span data-stu-id="43d86-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43d86-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="43d86-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="43d86-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="43d86-192">**Exchange**</span></span> <br/> |<span data-ttu-id="43d86-193">**Método de entrada de telefone**</span><span class="sxs-lookup"><span data-stu-id="43d86-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="43d86-194">**Skype para acesso de negócios**</span><span class="sxs-lookup"><span data-stu-id="43d86-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="43d86-195">**Acesso do Exchange com Autenticação Multifator e MFA desabilitados**</span><span class="sxs-lookup"><span data-stu-id="43d86-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="43d86-196">**Acesso do Exchange com Autenticação Multifator e MFA habilitados**</span><span class="sxs-lookup"><span data-stu-id="43d86-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="43d86-197">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-197">Online</span></span>  <br/> |<span data-ttu-id="43d86-198">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-198">Online</span></span>  <br/> |<span data-ttu-id="43d86-199">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="43d86-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="43d86-200">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-200">Yes</span></span>  <br/> |<span data-ttu-id="43d86-201">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-201">Yes</span></span>  <br/> |<span data-ttu-id="43d86-202">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-202">Yes</span></span>  <br/> |
|<span data-ttu-id="43d86-203">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-203">Online</span></span>  <br/> |<span data-ttu-id="43d86-204">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-204">Online</span></span>  <br/> |<span data-ttu-id="43d86-205">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="43d86-205">Username/Password</span></span>  <br/> |<span data-ttu-id="43d86-206">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-206">Yes</span></span>  <br/> |<span data-ttu-id="43d86-207">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-207">Yes</span></span>  <br/> |<span data-ttu-id="43d86-208">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-208">No</span></span>  <br/> |
|<span data-ttu-id="43d86-209">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-209">Online</span></span>  <br/> |<span data-ttu-id="43d86-210">Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-210">On-premises</span></span>  <br/> |<span data-ttu-id="43d86-211">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="43d86-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="43d86-212">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-212">Yes</span></span>  <br/> |<span data-ttu-id="43d86-213">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-213">No</span></span>  <br/> |<span data-ttu-id="43d86-214">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-214">No</span></span>  <br/> |
|<span data-ttu-id="43d86-215">Online</span><span class="sxs-lookup"><span data-stu-id="43d86-215">Online</span></span>  <br/> |<span data-ttu-id="43d86-216">Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-216">On-Premises</span></span>  <br/> |<span data-ttu-id="43d86-217">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="43d86-217">Username/Password</span></span>  <br/> |<span data-ttu-id="43d86-218">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-218">Yes</span></span>  <br/> |<span data-ttu-id="43d86-219">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-219">Yes</span></span>  <br/> |<span data-ttu-id="43d86-220">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-220">No</span></span>  <br/> |
|<span data-ttu-id="43d86-221">Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-221">On-premises</span></span>  <br/> |<span data-ttu-id="43d86-222">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="43d86-223">Autenticação de PIN</span><span class="sxs-lookup"><span data-stu-id="43d86-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="43d86-224">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-224">Yes</span></span>  <br/> |<span data-ttu-id="43d86-225">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-225">No</span></span>  <br/> |<span data-ttu-id="43d86-226">Não</span><span class="sxs-lookup"><span data-stu-id="43d86-226">No</span></span>  <br/> |
|<span data-ttu-id="43d86-227">Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-227">On-premises</span></span>  <br/> |<span data-ttu-id="43d86-228">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="43d86-229">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="43d86-229">Username/Password</span></span>  <br/> |<span data-ttu-id="43d86-230">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-230">Yes</span></span>  <br/> |<span data-ttu-id="43d86-231">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-231">Yes</span></span>  <br/> |<span data-ttu-id="43d86-232">N/D</span><span class="sxs-lookup"><span data-stu-id="43d86-232">N/A</span></span>  <br/> |
|<span data-ttu-id="43d86-233">Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-233">On-premises</span></span>  <br/> |<span data-ttu-id="43d86-234">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="43d86-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="43d86-235">Entrada via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="43d86-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="43d86-236">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-236">Yes</span></span>  <br/> |<span data-ttu-id="43d86-237">Sim</span><span class="sxs-lookup"><span data-stu-id="43d86-237">Yes</span></span>  <br/> |<span data-ttu-id="43d86-238">N/D</span><span class="sxs-lookup"><span data-stu-id="43d86-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="43d86-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span><span class="sxs-lookup"><span data-stu-id="43d86-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="43d86-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="43d86-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="43d86-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span><span class="sxs-lookup"><span data-stu-id="43d86-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="43d86-242">If enabled, users will be asked to create a PIN upon successful authentication.</span><span class="sxs-lookup"><span data-stu-id="43d86-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="43d86-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span><span class="sxs-lookup"><span data-stu-id="43d86-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="43d86-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span><span class="sxs-lookup"><span data-stu-id="43d86-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="43d86-245">The user's PIN should be between 6 and 15 digits.</span><span class="sxs-lookup"><span data-stu-id="43d86-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="43d86-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span><span class="sxs-lookup"><span data-stu-id="43d86-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="43d86-247">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span><span class="sxs-lookup"><span data-stu-id="43d86-247">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="43d86-248">Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="43d86-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="43d86-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="43d86-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="43d86-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="43d86-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="43d86-251">BToE enables users to:</span><span class="sxs-lookup"><span data-stu-id="43d86-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="43d86-252">Entrar no seu telefone IP usando seu Skype para aplicativos da área de trabalho de negócios (usando um PC)</span><span class="sxs-lookup"><span data-stu-id="43d86-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="43d86-253">Sincronizar o bloqueio de telefone com o bloqueio de PC</span><span class="sxs-lookup"><span data-stu-id="43d86-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="43d86-254">Clique para chamar</span><span class="sxs-lookup"><span data-stu-id="43d86-254">Click to call</span></span>
    
<span data-ttu-id="43d86-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span><span class="sxs-lookup"><span data-stu-id="43d86-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="43d86-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span><span class="sxs-lookup"><span data-stu-id="43d86-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="43d86-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span><span class="sxs-lookup"><span data-stu-id="43d86-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="43d86-258">**Implantar BToE para os usuários**</span><span class="sxs-lookup"><span data-stu-id="43d86-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="43d86-259">Conecte o PC deles ao telefone usando a porta do PC.</span><span class="sxs-lookup"><span data-stu-id="43d86-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Implementar telefones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="43d86-p121">Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="43d86-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="43d86-264">Site de Download de Software do Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="43d86-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="43d86-265">Download de software BToE Yealink</span><span class="sxs-lookup"><span data-stu-id="43d86-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="43d86-266">Downloads de software BToE AudioCodes</span><span class="sxs-lookup"><span data-stu-id="43d86-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="43d86-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="43d86-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="43d86-269">[!OBSERVAçãO] O BToE não é permitido atualmente nas plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="43d86-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="43d86-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="43d86-270">Related topics</span></span>
[<span data-ttu-id="43d86-271">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43d86-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="43d86-272">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="43d86-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="43d86-273">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="43d86-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
