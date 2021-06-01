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
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Saiba as etapas de implantação para obter o firmware correto, atualizá-lo, se necessário, atribuir licenças e configurar configurações para Skype for Business telefones online
ms.openlocfilehash: 1c607f0dd5c3a82c744f26432fe1c65f31263440
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237367"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="68f33-103">Implantando telefones do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="68f33-103">Deploying Skype for Business Online phones</span></span>

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="68f33-104">Este é o guia de implantação que o ajudará a implantar Skype for Business ip online.</span><span class="sxs-lookup"><span data-stu-id="68f33-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="68f33-105">Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é um requisito importante para fazer negócios.</span><span class="sxs-lookup"><span data-stu-id="68f33-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="68f33-106">Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os Skype for Business, incluindo telefones IP, computadores e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="68f33-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="68f33-107">Você pode saber mais sobre os Skype for Business IP lendo Obter telefones para Skype for Business [Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="68f33-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="68f33-108">Etapas de implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="68f33-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="68f33-109">Etapa 1 - Baixar guias de administrador e manuais de telefone do fabricante</span><span class="sxs-lookup"><span data-stu-id="68f33-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="68f33-110">Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="68f33-111">Para telefones Polycom, consulte [a Biblioteca de Documentação Poly.](https://documents.polycom.com/category/voice)</span><span class="sxs-lookup"><span data-stu-id="68f33-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="68f33-112">Para telefones Yealink, consulte [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="68f33-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="68f33-113">Para telefones AudioCodes, consulte o Guia de Gerenciamento de Provisionamento de [Audiocódigos.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)</span><span class="sxs-lookup"><span data-stu-id="68f33-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="68f33-114">Etapa 2 : certifique-se de que você está comprando ou migrando um telefone IP e firmware com suporte Skype for Business ip com suporte</span><span class="sxs-lookup"><span data-stu-id="68f33-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="68f33-115">Um Skype for Business e firmware compatíveis com o Skype for Business Server online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="68f33-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="68f33-116">Para garantir que você está comprando ou provisionando um telefone e firmware com suporte, consulte [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="68f33-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="68f33-117">Etapa 3 - Verificar se o firmware certo está instalado e atualizar o firmware, se necessário</span><span class="sxs-lookup"><span data-stu-id="68f33-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="68f33-118">Verifique a versão do firmware em seus telefones.</span><span class="sxs-lookup"><span data-stu-id="68f33-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="68f33-119">Para:</span><span class="sxs-lookup"><span data-stu-id="68f33-119">For:</span></span>
  
- <span data-ttu-id="68f33-120">**Telefones Polycom VVX**, acesse **Configurações** Aplicativo Principal da Plataforma  >    >    >  **de**  >  **Status.**</span><span class="sxs-lookup"><span data-stu-id="68f33-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="68f33-121">**Telefones yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="68f33-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="68f33-122">**AudioCodes telefones**, vá para **Menu** Versão do Firmware de Status do Dispositivo  >    >   na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="68f33-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="68f33-123">Para obter acesso remoto aos detalhes do telefone, consulte guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="68f33-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="68f33-124">Consulte os links acima para os guias de usuário e manuais de telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="68f33-125">**Telefones do Lync Telefone Edition (LPE),** acesse **Menu**  >  **Informações do Sistema** da tela inicial.</span><span class="sxs-lookup"><span data-stu-id="68f33-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="68f33-126">Etapa 4 - Considerações sobre atualização de dispositivos</span><span class="sxs-lookup"><span data-stu-id="68f33-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="68f33-127">O firmware polycom antes do 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por uma implementação Skype for Business "Telefone-Lock".</span><span class="sxs-lookup"><span data-stu-id="68f33-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="68f33-128">Atualizar um telefone de 5.4.X.X que foi protegido com "Device-Lock" para 5.5.1.X com "Telefone-Lock" não herdará o código PIN de "Device-Lock", o que pode deixar o telefone sem segurança.</span><span class="sxs-lookup"><span data-stu-id="68f33-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="68f33-129">Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro Polycom Device Profile para dar aos usuários o controle do tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="68f33-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="68f33-130">As atualizações de firmware são gerenciadas pelo Skype for Business Service.</span><span class="sxs-lookup"><span data-stu-id="68f33-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="68f33-131">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="68f33-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="68f33-132">Dependendo do tempo de inatividade no telefone e dos intervalos de sondagem, os telefones baixarão e instalarão automaticamente as versões certificadas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="68f33-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="68f33-133">Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) e definindo o _parâmetro EnableDeviceUpdate_ como `false` .</span><span class="sxs-lookup"><span data-stu-id="68f33-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Captura de tela mostrando a implantação de telefones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="68f33-135">Quando um novo firmware estiver disponível e pronto para download e instalação, o telefone notificará o usuário.</span><span class="sxs-lookup"><span data-stu-id="68f33-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="68f33-136">Os telefones Polycom notificarão o usuário e fornecerão uma opção para **Atualizar** ou **Adiar**.</span><span class="sxs-lookup"><span data-stu-id="68f33-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Captura de tela mostrando opções de Atualização e Adiamento.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="68f33-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="68f33-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Captura de tela mostrando a opção SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="68f33-140">Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros.</span><span class="sxs-lookup"><span data-stu-id="68f33-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="68f33-141">Para gerenciamento do sistema de provisionamento de parceiros, incluindo personalização avançada de telefone, consulte guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="68f33-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="68f33-142">Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="68f33-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="68f33-143">Etapa 5 - Configuração e configurações de telefone de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="68f33-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="68f33-144">Você pode configurar as opções e políticas de telefone mais comumente usadas usando Skype for Business gerenciamento em banda Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="68f33-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="68f33-145">Consulte [Set-CsIPPhonePolicy para](/powershell/module/skype/Set-CsIPPhonePolicy) obter detalhes desses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="68f33-145">See [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="68f33-146">Para planejar a infraestrutura de rede, [consulte Skype Operations Framework](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="68f33-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="68f33-147">Etapa 6 - Preparando os usuários para entrar</span><span class="sxs-lookup"><span data-stu-id="68f33-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="68f33-148">Para habilitar os usuários a entrar com êxito em um telefone Skype for Business Online e fazer chamadas, você precisa garantir que os usuários sejam atribuídos às licenças corretas.</span><span class="sxs-lookup"><span data-stu-id="68f33-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="68f33-149">No mínimo, você precisará atribuir uma licença de Sistema de Telefonia e um Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="68f33-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="68f33-150">Para obter informações adicionais, você pode [ver Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e Microsoft Teams licenciamento de complemento e Atribuir Skype for Business e [Microsoft Teams licenças](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="68f33-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="68f33-151">Você pode saber mais sobre Planos de Chamada lendo Sistema de Telefonia [e Planos de Chamada](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="68f33-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="68f33-152">**As opções de login** disponíveis para usuários online são:</span><span class="sxs-lookup"><span data-stu-id="68f33-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="68f33-153">Os usuários **com telefones Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando o logon de telefones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="68f33-155">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando o logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="68f33-157">Para obter detalhes sobre as opções de login com suporte do fabricante, consulte [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="68f33-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="68f33-158">**ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="68f33-159">Por exemplo, eles devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="68f33-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="68f33-161">A autenticação de PIN não é suportada para o Skype for Business Online para telefones IP de parceiros e LPE.</span><span class="sxs-lookup"><span data-stu-id="68f33-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="68f33-162">**Usando um computador** Quando o software Better Together over Ethernet (BToE) é instalado no computador do usuário e habilitado, os usuários podem fazer logoff em seus telefones usando a janela de autenticação em seu Windows Skype for Business App.</span><span class="sxs-lookup"><span data-stu-id="68f33-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="68f33-163">Consulte a Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e [Melhor Juntos sobre Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.</span><span class="sxs-lookup"><span data-stu-id="68f33-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="68f33-164">Os usuários devem usar o nome de usuário e a senha de sua organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="68f33-165">Por exemplo, eles devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="68f33-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="68f33-167">**Usando um Web Sign-in**: Essa é uma nova maneira para os usuários online autenticar usando um navegador da Web padrão.</span><span class="sxs-lookup"><span data-stu-id="68f33-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="68f33-168">Os usuários receberão um conjunto de instruções a seguir quando usarem um navegador para entrar.</span><span class="sxs-lookup"><span data-stu-id="68f33-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="68f33-169">Os usuários **com telefones Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando as instruções polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="68f33-171">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando instruções do Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="68f33-173">O código gerado expirará em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="68f33-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="68f33-174">Quando expirar, o usuário terá que clicar em **Repetir** ou **OK** para gerar um novo código, dependendo do telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="68f33-175">Os usuários **com telefones Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando código Polycom expirado](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="68f33-177">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="68f33-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando código Yealink expirado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="68f33-179">Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome Skype for Business nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="68f33-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Captura de tela mostrando verificação de email](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="68f33-181">Insira o código mostrado no telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-181">Enter the code shown on the phone.</span></span>
    
     ![Captura de tela mostrando a inserção de código na tela de logon](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="68f33-183">Verifique se o site mostra "[Telefone Nome do fabricante] **Skype for Business certificado Telefone**", e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="68f33-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Captura de tela mostrando verificação de nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="68f33-185">Clique nas credenciais do usuário ou clique em **Usar outra conta:**</span><span class="sxs-lookup"><span data-stu-id="68f33-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Captura de tela mostrando opções de credencial](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="68f33-187">Quando a página a seguir é exibida, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="68f33-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Captura de tela mostrando mensagem de confirmação](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="68f33-189">Telefones LPE para Skype for Business online suportam entrada somente por meio de conexão USB.</span><span class="sxs-lookup"><span data-stu-id="68f33-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="68f33-190">**Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação atualmente suportados, incluindo integração Exchange, autenticação moderna com MFA (Autenticação multifatória) e Skype for Business Online e local.</span><span class="sxs-lookup"><span data-stu-id="68f33-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="68f33-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="68f33-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="68f33-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="68f33-192">**Exchange**</span></span> <br/> |<span data-ttu-id="68f33-193">**Telefone Sign-In método**</span><span class="sxs-lookup"><span data-stu-id="68f33-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="68f33-194">**Skype for Business acesso**</span><span class="sxs-lookup"><span data-stu-id="68f33-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="68f33-195">**Exchange Acesso com Auth Moderno e MFA desabilitado**</span><span class="sxs-lookup"><span data-stu-id="68f33-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="68f33-196">**Exchange Acesso com a Auth Moderna e MFA habilitada**</span><span class="sxs-lookup"><span data-stu-id="68f33-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="68f33-197">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-197">Online</span></span>  <br/> |<span data-ttu-id="68f33-198">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-198">Online</span></span>  <br/> |<span data-ttu-id="68f33-199">Web Sign-in</span><span class="sxs-lookup"><span data-stu-id="68f33-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="68f33-200">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-200">Yes</span></span>  <br/> |<span data-ttu-id="68f33-201">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-201">Yes</span></span>  <br/> |<span data-ttu-id="68f33-202">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-202">Yes</span></span>  <br/> |
|<span data-ttu-id="68f33-203">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-203">Online</span></span>  <br/> |<span data-ttu-id="68f33-204">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-204">Online</span></span>  <br/> |<span data-ttu-id="68f33-205">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="68f33-205">Username/Password</span></span>  <br/> |<span data-ttu-id="68f33-206">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-206">Yes</span></span>  <br/> |<span data-ttu-id="68f33-207">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-207">Yes</span></span>  <br/> |<span data-ttu-id="68f33-208">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-208">No</span></span>  <br/> |
|<span data-ttu-id="68f33-209">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-209">Online</span></span>  <br/> |<span data-ttu-id="68f33-210">Local</span><span class="sxs-lookup"><span data-stu-id="68f33-210">On-premises</span></span>  <br/> |<span data-ttu-id="68f33-211">Web Sign-in</span><span class="sxs-lookup"><span data-stu-id="68f33-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="68f33-212">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-212">Yes</span></span>  <br/> |<span data-ttu-id="68f33-213">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-213">No</span></span>  <br/> |<span data-ttu-id="68f33-214">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-214">No</span></span>  <br/> |
|<span data-ttu-id="68f33-215">Online</span><span class="sxs-lookup"><span data-stu-id="68f33-215">Online</span></span>  <br/> |<span data-ttu-id="68f33-216">Local</span><span class="sxs-lookup"><span data-stu-id="68f33-216">On-Premises</span></span>  <br/> |<span data-ttu-id="68f33-217">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="68f33-217">Username/Password</span></span>  <br/> |<span data-ttu-id="68f33-218">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-218">Yes</span></span>  <br/> |<span data-ttu-id="68f33-219">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-219">Yes</span></span>  <br/> |<span data-ttu-id="68f33-220">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-220">No</span></span>  <br/> |
|<span data-ttu-id="68f33-221">Local</span><span class="sxs-lookup"><span data-stu-id="68f33-221">On-premises</span></span>  <br/> |<span data-ttu-id="68f33-222">Online/local</span><span class="sxs-lookup"><span data-stu-id="68f33-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="68f33-223">Autenticação PIN</span><span class="sxs-lookup"><span data-stu-id="68f33-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="68f33-224">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-224">Yes</span></span>  <br/> |<span data-ttu-id="68f33-225">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-225">No</span></span>  <br/> |<span data-ttu-id="68f33-226">Não</span><span class="sxs-lookup"><span data-stu-id="68f33-226">No</span></span>  <br/> |
|<span data-ttu-id="68f33-227">Local</span><span class="sxs-lookup"><span data-stu-id="68f33-227">On-premises</span></span>  <br/> |<span data-ttu-id="68f33-228">Online/local</span><span class="sxs-lookup"><span data-stu-id="68f33-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="68f33-229">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="68f33-229">Username/Password</span></span>  <br/> |<span data-ttu-id="68f33-230">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-230">Yes</span></span>  <br/> |<span data-ttu-id="68f33-231">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-231">Yes</span></span>  <br/> |<span data-ttu-id="68f33-232">Não disponível</span><span class="sxs-lookup"><span data-stu-id="68f33-232">N/A</span></span>  <br/> |
|<span data-ttu-id="68f33-233">Local</span><span class="sxs-lookup"><span data-stu-id="68f33-233">On-premises</span></span>  <br/> |<span data-ttu-id="68f33-234">Online/local</span><span class="sxs-lookup"><span data-stu-id="68f33-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="68f33-235">Entrar por computador (BTOE)</span><span class="sxs-lookup"><span data-stu-id="68f33-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="68f33-236">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-236">Yes</span></span>  <br/> |<span data-ttu-id="68f33-237">Sim</span><span class="sxs-lookup"><span data-stu-id="68f33-237">Yes</span></span>  <br/> |<span data-ttu-id="68f33-238">Não disponível</span><span class="sxs-lookup"><span data-stu-id="68f33-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="68f33-239">**Telefone recursos** O conjunto de recursos pode variar ligeiramente com base no parceiro de telefone IP.</span><span class="sxs-lookup"><span data-stu-id="68f33-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="68f33-240">Para obter o conjunto de recursos completo e para obter mais informações sobre os recursos para cada fabricante de telefone, consulte Obter telefones [para Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="68f33-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="68f33-241">**Telefone-Lock** é um recurso introduzido recentemente em Skype for Business certificados que é usado para proteger um telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="68f33-242">Se habilitado, os usuários serão solicitados a criar um PIN após a autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="68f33-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="68f33-243">Depois de criados, os telefones serão travados quando o tempo de ociosidade definido expirar, um usuário bloqueará manualmente seu telefone ou sincronizará o bloqueio de telefone com o bloqueio do computador usando o Telefone Emparelhamento.</span><span class="sxs-lookup"><span data-stu-id="68f33-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="68f33-244">Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone assinará o usuário ou exigirá o código de um administrador para desbloquear o telefone, mas isso variará dependendo do parceiro de telefone.</span><span class="sxs-lookup"><span data-stu-id="68f33-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="68f33-245">O PIN do usuário deve ter entre 6 e 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="68f33-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="68f33-246">Você pode desabilitar Phone-Lock para sua organização (que está habilitada por padrão), alterar o tempo de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto estão bloqueados ou não usando configurações de banda interna.</span><span class="sxs-lookup"><span data-stu-id="68f33-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="68f33-247">Consulte [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) para obter mais detalhes sobre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="68f33-247">See [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="68f33-248">Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e Melhor Juntos sobre Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="68f33-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="68f33-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="68f33-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="68f33-250">BToE é um mecanismo de dor de telefone para telefones IP parceiros que emparelha o telefone de um usuário com seu Windows Skype for Business aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68f33-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="68f33-251">BToE permite que os usuários:</span><span class="sxs-lookup"><span data-stu-id="68f33-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="68f33-252">Entre no telefone IP usando seu aplicativo Skype for Business desktop (usando um computador)</span><span class="sxs-lookup"><span data-stu-id="68f33-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="68f33-253">Sincronizar Phone-Lock com bloqueio de computador</span><span class="sxs-lookup"><span data-stu-id="68f33-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="68f33-254">Clique para chamar</span><span class="sxs-lookup"><span data-stu-id="68f33-254">Click to call</span></span>
    
<span data-ttu-id="68f33-255">O BToE pode ser configurado para operar em dois modos:  *Automático*  (padrão) e *Manual*  .</span><span class="sxs-lookup"><span data-stu-id="68f33-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="68f33-256">Ele também pode ser habilitado (padrão)/desabilitado para usuários que Skype for Business configurações em banda.</span><span class="sxs-lookup"><span data-stu-id="68f33-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="68f33-257">Ao operar no *modo Manual,* os usuários terão que dar uma etapa adicional para emparelhar seu telefone com seu Windows aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68f33-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="68f33-258">**Para implantar o BToE aos usuários**</span><span class="sxs-lookup"><span data-stu-id="68f33-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="68f33-259">Conexão seu computador para o telefone usando a porta do computador.</span><span class="sxs-lookup"><span data-stu-id="68f33-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Captura de tela mostrando conexão com um computador](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="68f33-261">Baixe e instale o software BToE mais recente do site do fabricante nos links abaixo.</span><span class="sxs-lookup"><span data-stu-id="68f33-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="68f33-262">Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administrador, como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="68f33-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="68f33-263">Para saber mais sobre como usar o Configuration Manager, consulte [Pacotes e programas no Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="68f33-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="68f33-264">Site de download de software do Polycom BToE</span><span class="sxs-lookup"><span data-stu-id="68f33-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="68f33-265">Yealink BToE Software Download</span><span class="sxs-lookup"><span data-stu-id="68f33-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="68f33-266">AudioCodes BToE Software Downloads</span><span class="sxs-lookup"><span data-stu-id="68f33-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="68f33-267">A configuração do servidor para BToE é definida como **Habilitado e** **Modo Automático** por padrão.</span><span class="sxs-lookup"><span data-stu-id="68f33-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="68f33-268">Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span><span class="sxs-lookup"><span data-stu-id="68f33-268">To change those settings, see [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span></span>
    
> [!NOTE]
> <span data-ttu-id="68f33-269">No momento, o BToE não tem suporte em plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="68f33-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="68f33-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="68f33-270">Related topics</span></span>
[<span data-ttu-id="68f33-271">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68f33-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="68f33-272">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="68f33-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="68f33-273">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="68f33-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
