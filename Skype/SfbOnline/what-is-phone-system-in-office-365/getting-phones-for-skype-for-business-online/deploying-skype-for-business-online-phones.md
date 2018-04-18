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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para Skype para telefones online de negócios
ms.openlocfilehash: 2e1ee62dc2cd16a8aeec9b1eb744e4ca3f0155eb
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="d7825-103">Implantar telefones para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7825-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="d7825-104">Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d7825-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="d7825-105">Em todos os tipos de empresas, ter um número de telefone permite aos usuários fazer e receber chamadas de voz e é um requisito importante para fazer negócios.</span><span class="sxs-lookup"><span data-stu-id="d7825-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="d7825-106">Os usuários que possuem números de telefone poderão fazer chamadas de voz entre todos os Skype para dispositivos de negócios, incluindo telefones IP, PCs e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="d7825-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="d7825-107">Você pode aprender mais sobre Skype para telefones IP Business lendo [telefones de Introdução para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="d7825-108">Etapas da implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="d7825-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="d7825-109">Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone</span><span class="sxs-lookup"><span data-stu-id="d7825-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="d7825-110">Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="d7825-111">Para telefones Polycom, consulte o [Polycom Deployment Guide] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="d7825-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="d7825-112">Para telefones Yealink, consulte [Yealink Skype para a solução de telefones SIP do negócios HD](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="d7825-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="d7825-113">Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="d7825-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="d7825-114">Etapa 2 - Certifique-se de que você está migrando para um telefone IP e firmware compatíveis com o Skype for Business ou adquirindo um assim.</span><span class="sxs-lookup"><span data-stu-id="d7825-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="d7825-115">Um telefone e um firmware compatíveis com o Skype for Business Online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é aplicável.</span><span class="sxs-lookup"><span data-stu-id="d7825-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="d7825-116">Para certificar-se você estiver comprar ou um telefone com suporte e firmware de provisionamento, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="d7825-117">Etapa 3 - Verificar se o firmware certo foi instalado e atualizar o firmware, se necessário</span><span class="sxs-lookup"><span data-stu-id="d7825-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="d7825-118">Verifica a versão de firmware em seus telefones.</span><span class="sxs-lookup"><span data-stu-id="d7825-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="d7825-119">No caso de:</span><span class="sxs-lookup"><span data-stu-id="d7825-119">For:</span></span>
  
- <span data-ttu-id="d7825-120">**Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="d7825-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="d7825-121">**Telefones Yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="d7825-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="d7825-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="d7825-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d7825-p104">Para obter acesso remoto para obter detalhes de telefone, consulte guias de administração do fabricante. Consulte os links acima para os guias de usuário e manuais de telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="d7825-125">**Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="d7825-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="d7825-126">Etapa 4 - Considerações sobre atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d7825-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="d7825-127">Polycom firmware antes da 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específicas do fabricante é substituído por um Skype para a implementação de negócios "Telefone-Lock."</span><span class="sxs-lookup"><span data-stu-id="d7825-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="d7825-128">Atualizando um telefone do 5.4.X.X que tenha sido protegido com "Bloqueio de dispositivo" para 5.5.1.X com "Bloqueio de telefone" não herda o código PIN de "Dispositivo-Lock," que pode deixar o telefone não segura.</span><span class="sxs-lookup"><span data-stu-id="d7825-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="d7825-129">Os usuários que ativaram "Bloqueio de dispositivo" precisam habilitar o seguinte parâmetro de perfil do dispositivo Polycom dar aos usuários controle de tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="d7825-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="d7825-130">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d7825-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="d7825-131">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="d7825-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="d7825-132">Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d7825-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="d7825-133">Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ para `false`.</span><span class="sxs-lookup"><span data-stu-id="d7825-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Deploying phones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="d7825-p107">Quando um novo firmware está disponível e pronto para baixar e instalar, o telefone notificará o usuário. Telefones Polycom irá notificar o usuário e fornecer-lhes uma opção para **atualização** ou **Adiar**.</span><span class="sxs-lookup"><span data-stu-id="d7825-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Deploying phones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="d7825-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="d7825-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Deploying phones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="d7825-p108">Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="d7825-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="d7825-142">[!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="d7825-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="d7825-143">Etapa 5 - configuração e definições de telefone de infra-estrutura</span><span class="sxs-lookup"><span data-stu-id="d7825-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="d7825-p109">Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="d7825-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="d7825-146">Para o planejamento da infra-estrutura de rede, consulte [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="d7825-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="d7825-147">Etapa 6 - Preparando os usuários entrem em</span><span class="sxs-lookup"><span data-stu-id="d7825-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="d7825-148">Para habilitar usuários entrar em um Skype para telefone comercial Online e fazer chamadas com êxito, você precisará certificar-se de que os usuários recebem as licenças corretas.</span><span class="sxs-lookup"><span data-stu-id="d7825-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="d7825-149">No mínimo, você precisará atribuir uma licença de sistema telefônico e um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="d7825-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="d7825-150">Para obter informações adicionais, você pode ver [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="d7825-151">Você pode encontrar mais informações sobre planos de chamar lendo [Cite chamar planos no Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="d7825-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)</span></span>
  
- <span data-ttu-id="d7825-152">As **opções de logon** que estão disponíveis para os usuários online são:</span><span class="sxs-lookup"><span data-stu-id="d7825-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="d7825-153">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="d7825-155">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="d7825-157">Para obter detalhes sobre as opções de entrar suportadas pelo fabricante, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="d7825-p111">**ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como *amosm@contoso.com*  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="d7825-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="d7825-161">[!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros.</span><span class="sxs-lookup"><span data-stu-id="d7825-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="d7825-162">**Usando um PC** Quando a união de forças sobre software Ethernet (BToE) está instalado no PC do usuário e habilitado, os usuários podem fazer logon no seus telefones usando a janela de autenticação em seus Skype do Windows para o aplicativo de negócios.</span><span class="sxs-lookup"><span data-stu-id="d7825-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="d7825-163">Consulte a [etapa 7 (opcional) - se você tiver o emparelhamento de dispositivos e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.</span><span class="sxs-lookup"><span data-stu-id="d7825-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d7825-p113">[!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  *amosm@contoso.com*  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="d7825-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Deploying phones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="d7825-167">**Usando um Web entrar**: essa é uma maneira de nova para usuários on-line autenticar usando um navegador da web padrão.</span><span class="sxs-lookup"><span data-stu-id="d7825-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="d7825-168">Os usuários serão fornecidos com um conjunto de instruções a seguir quando utilizarem um navegador para entrar.</span><span class="sxs-lookup"><span data-stu-id="d7825-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="d7825-169">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Deploying phones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="d7825-171">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phone logon.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="d7825-p115">O código que seja gerado expirará em 15 minutos. Quando ela expira, o usuário precisará clique em **Repetir** ou **Okey** para gerar um novo código, dependendo do telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="d7825-175">Usuários com telefones **Polycom VVX 5XX/6XX** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN code expired.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="d7825-177">Usuários com telefones **Yealink T48G/T46G** verá:</span><span class="sxs-lookup"><span data-stu-id="d7825-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink phones logon.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="d7825-179">Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d7825-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Deploying phones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="d7825-181">Digite o código mostrado no telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-181">Enter the code shown on the phone.</span></span>
    
     ![Deploying phones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="d7825-183">Verifique se o site mostra "[nome do fabricante do telefone] **Skype para negócios Certified Phone**," e clique em **continuar**.</span><span class="sxs-lookup"><span data-stu-id="d7825-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Deploying phones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="d7825-185">Clique nas credenciais do usuário ou clique em **Usar outra conta**:</span><span class="sxs-lookup"><span data-stu-id="d7825-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Deploying phones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="d7825-187">Quando for exibida a página seguinte, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="d7825-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Deploying phones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="d7825-189">[!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB.</span><span class="sxs-lookup"><span data-stu-id="d7825-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="d7825-190">**Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.</span><span class="sxs-lookup"><span data-stu-id="d7825-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7825-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d7825-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="d7825-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="d7825-192">**Exchange**</span></span> <br/> |<span data-ttu-id="d7825-193">**Método de entrada de telefone**</span><span class="sxs-lookup"><span data-stu-id="d7825-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="d7825-194">**Skype para acesso de negócios**</span><span class="sxs-lookup"><span data-stu-id="d7825-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="d7825-195">**Acesso do Exchange com Autenticação Multifator e MFA desabilitados**</span><span class="sxs-lookup"><span data-stu-id="d7825-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="d7825-196">**Acesso do Exchange com Autenticação Multifator e MFA habilitados**</span><span class="sxs-lookup"><span data-stu-id="d7825-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="d7825-197">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-197">Online</span></span>  <br/> |<span data-ttu-id="d7825-198">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-198">Online</span></span>  <br/> |<span data-ttu-id="d7825-199">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="d7825-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="d7825-200">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-200">Yes</span></span>  <br/> |<span data-ttu-id="d7825-201">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-201">Yes</span></span>  <br/> |<span data-ttu-id="d7825-202">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-202">Yes</span></span>  <br/> |
|<span data-ttu-id="d7825-203">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-203">Online</span></span>  <br/> |<span data-ttu-id="d7825-204">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-204">Online</span></span>  <br/> |<span data-ttu-id="d7825-205">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="d7825-205">Username/Password</span></span>  <br/> |<span data-ttu-id="d7825-206">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-206">Yes</span></span>  <br/> |<span data-ttu-id="d7825-207">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-207">Yes</span></span>  <br/> |<span data-ttu-id="d7825-208">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-208">No</span></span>  <br/> |
|<span data-ttu-id="d7825-209">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-209">Online</span></span>  <br/> |<span data-ttu-id="d7825-210">Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-210">On-premises</span></span>  <br/> |<span data-ttu-id="d7825-211">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="d7825-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="d7825-212">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-212">Yes</span></span>  <br/> |<span data-ttu-id="d7825-213">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-213">No</span></span>  <br/> |<span data-ttu-id="d7825-214">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-214">No</span></span>  <br/> |
|<span data-ttu-id="d7825-215">Online</span><span class="sxs-lookup"><span data-stu-id="d7825-215">Online</span></span>  <br/> |<span data-ttu-id="d7825-216">Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-216">On-Premises</span></span>  <br/> |<span data-ttu-id="d7825-217">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="d7825-217">Username/Password</span></span>  <br/> |<span data-ttu-id="d7825-218">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-218">Yes</span></span>  <br/> |<span data-ttu-id="d7825-219">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-219">Yes</span></span>  <br/> |<span data-ttu-id="d7825-220">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-220">No</span></span>  <br/> |
|<span data-ttu-id="d7825-221">Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-221">On-premises</span></span>  <br/> |<span data-ttu-id="d7825-222">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="d7825-223">Autenticação de PIN</span><span class="sxs-lookup"><span data-stu-id="d7825-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="d7825-224">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-224">Yes</span></span>  <br/> |<span data-ttu-id="d7825-225">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-225">No</span></span>  <br/> |<span data-ttu-id="d7825-226">Não</span><span class="sxs-lookup"><span data-stu-id="d7825-226">No</span></span>  <br/> |
|<span data-ttu-id="d7825-227">Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-227">On-premises</span></span>  <br/> |<span data-ttu-id="d7825-228">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="d7825-229">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="d7825-229">Username/Password</span></span>  <br/> |<span data-ttu-id="d7825-230">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-230">Yes</span></span>  <br/> |<span data-ttu-id="d7825-231">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-231">Yes</span></span>  <br/> |<span data-ttu-id="d7825-232">N/A</span><span class="sxs-lookup"><span data-stu-id="d7825-232">N/A</span></span>  <br/> |
|<span data-ttu-id="d7825-233">Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-233">On-premises</span></span>  <br/> |<span data-ttu-id="d7825-234">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="d7825-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="d7825-235">Entrada via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="d7825-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="d7825-236">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-236">Yes</span></span>  <br/> |<span data-ttu-id="d7825-237">Sim</span><span class="sxs-lookup"><span data-stu-id="d7825-237">Yes</span></span>  <br/> |<span data-ttu-id="d7825-238">N/A</span><span class="sxs-lookup"><span data-stu-id="d7825-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="d7825-239">**Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro do telefone IP.</span><span class="sxs-lookup"><span data-stu-id="d7825-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="d7825-240">Para o recurso completo definida e para saber mais sobre os recursos para cada fabricante do telefone, consulte [Getting telefones para Skype para negócios Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="d7825-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="d7825-241">**Bloqueio de telefone** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business que é usado para proteger um telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="d7825-242">Se habilitada, os usuários serão solicitados para criar um PIN após a autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="d7825-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="d7825-243">Depois de criado, os telefones serão bloqueados quando o tempo ocioso-limite que você definir expirar, um usuário bloqueia manualmente seu telefone ou ele sincroniza o bloqueio do telefone com o bloqueio do PC usando o Emparelhamento de Telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="d7825-244">Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone irá desconectar o usuário ou requerem código do administrador para desbloquear o telefone, mas isso irá variar dependendo do parceiro de telefone.</span><span class="sxs-lookup"><span data-stu-id="d7825-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="d7825-245">O PIN do usuário deve estar entre 6 e 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="d7825-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="d7825-246">Você pode desabilitar o bloqueio de telefone para sua organização (que é habilitada por padrão), alterar o limite de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto eles estão bloqueadas ou não usando configurações de inband.</span><span class="sxs-lookup"><span data-stu-id="d7825-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="d7825-247">Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter mais detalhes sobre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="d7825-247">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="d7825-248">Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="d7825-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="d7825-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="d7825-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="d7825-250">BToE é um telefone paining mecanismo para telefones IP de parceiro que pares de telefone de um usuário com seus Skype do Windows para o aplicativo de negócios.</span><span class="sxs-lookup"><span data-stu-id="d7825-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="d7825-251">BToE habilita os usuários a:</span><span class="sxs-lookup"><span data-stu-id="d7825-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="d7825-252">Entrar no seu telefone IP usando seu Skype para aplicativos da área de trabalho de negócios (usando um PC)</span><span class="sxs-lookup"><span data-stu-id="d7825-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="d7825-253">Sincronizar o bloqueio de telefone com o bloqueio de PC</span><span class="sxs-lookup"><span data-stu-id="d7825-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="d7825-254">Clique para chamar</span><span class="sxs-lookup"><span data-stu-id="d7825-254">Click to call</span></span>
    
<span data-ttu-id="d7825-255">BToE pode ser configurado para operar em dois modos: *Manual* e *automático* (padrão).</span><span class="sxs-lookup"><span data-stu-id="d7825-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="d7825-256">Ele também pode ser habilitado (padrão)/desabilitado para usuário que usam as configurações em banda do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d7825-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="d7825-257">Ao operar no modo *Manual*  , os usuários terão que executar um passo adicional para emparelhar o telefone ao app Windows.</span><span class="sxs-lookup"><span data-stu-id="d7825-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="d7825-258">**Implantar BToE para os usuários**</span><span class="sxs-lookup"><span data-stu-id="d7825-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="d7825-259">Conecte o PC deles ao telefone usando a porta do PC.</span><span class="sxs-lookup"><span data-stu-id="d7825-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Deploying phones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="d7825-p121">Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="d7825-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="d7825-264">Site de Download de Software do Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="d7825-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="d7825-265">Download de software BToE Yealink</span><span class="sxs-lookup"><span data-stu-id="d7825-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="d7825-266">Downloads de software BToE AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d7825-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="d7825-267">Por padrão, a configuração de servidor para BToE é definida como **ativado** e o **modo automático** .</span><span class="sxs-lookup"><span data-stu-id="d7825-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="d7825-268">Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7825-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="d7825-269">[!OBSERVAçãO] O BToE não é permitido atualmente nas plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="d7825-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="d7825-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d7825-270">Related topics</span></span>
[<span data-ttu-id="d7825-271">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7825-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

<span data-ttu-id="d7825-272">Eis o que você obtém com o [Sistema de Telefonia no Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="d7825-272">[Here's what you get with Phone System in Office 365](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)</span></span>

[<span data-ttu-id="d7825-273">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="d7825-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 
