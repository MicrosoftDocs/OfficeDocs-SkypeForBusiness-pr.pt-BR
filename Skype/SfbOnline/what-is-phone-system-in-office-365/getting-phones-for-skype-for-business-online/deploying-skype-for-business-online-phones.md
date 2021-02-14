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
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-lo, se necessário, atribuir licenças e definir configurações para telefones online do Skype for Business
ms.openlocfilehash: 41c6ef53469ab2de3699fd17a2d181477e143fae
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220441"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="50ad6-103">Implantando telefones do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="50ad6-104">Este guia de implantação ajudará você a implantar telefones IP do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="50ad6-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="50ad6-105">Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é um requisito importante para fazer negócios.</span><span class="sxs-lookup"><span data-stu-id="50ad6-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="50ad6-106">Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os dispositivos Skype for Business, incluindo telefones IP, computadores e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="50ad6-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="50ad6-107">Você pode saber mais sobre telefones IP do Skype for Business lendo [Adquirir telefones para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="50ad6-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="50ad6-108">Etapas de implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="50ad6-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="50ad6-109">Etapa 1 - Baixar os guias de administrador do fabricante e os manuais de telefone</span><span class="sxs-lookup"><span data-stu-id="50ad6-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="50ad6-110">Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e os manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="50ad6-111">Para telefones Polycom, consulte a [Biblioteca de Documentação Poly.](https://documents.polycom.com/category/voice)</span><span class="sxs-lookup"><span data-stu-id="50ad6-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="50ad6-112">Para telefones Yealink, consulte [a solução de telefones SIP Yealink Skype for Business HD.](http://www.yealink.com/products_top_2.html)</span><span class="sxs-lookup"><span data-stu-id="50ad6-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="50ad6-113">Para telefones AudioCodes, consulte o Guia de Gerenciamento de [Provisionamento de Audiocodes.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)</span><span class="sxs-lookup"><span data-stu-id="50ad6-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="50ad6-114">Etapa 2 - Certifique-se de que você está comprando ou migrando um telefone IP e firmware com suporte do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="50ad6-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="50ad6-115">Um telefone e firmware compatíveis com o Skype for Business Online também é compatível com o Skype for Business Server, mas o oposto nem sempre é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="50ad6-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="50ad6-116">Para garantir que você está comprando ou provisionando um telefone e firmware com suporte, consulte Obter telefones [para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="50ad6-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="50ad6-117">Etapa 3 : verificar se o firmware correto está instalado e atualizar o firmware, se necessário</span><span class="sxs-lookup"><span data-stu-id="50ad6-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="50ad6-118">Verifique a versão do firmware em seus telefones.</span><span class="sxs-lookup"><span data-stu-id="50ad6-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="50ad6-119">Para:</span><span class="sxs-lookup"><span data-stu-id="50ad6-119">For:</span></span>
  
- <span data-ttu-id="50ad6-120">**Telefones Polycom VVX,** vá **para a Plataforma de** Status de Configurações  >    >  **Principal** do  >    >  **Aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="50ad6-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="50ad6-121">**Telefones Yealink,** vá **para Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="50ad6-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="50ad6-122">**Telefones AudioCodes,** vá para **a versão firmware** de status do dispositivo de  >  **menu** na tela  >   inicial.</span><span class="sxs-lookup"><span data-stu-id="50ad6-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="50ad6-123">Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="50ad6-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="50ad6-124">Veja os links acima para os guias de usuário e manuais de telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="50ad6-125">**Telefones Lync Phone Edition (LPE),** vá para Informações do Sistema de **Menu**  >   na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="50ad6-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="50ad6-126">Etapa 4 - Considerações sobre a atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="50ad6-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="50ad6-127">O firmware polycom antes da versão 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por um "Bloqueio de Telefone" de implementação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="50ad6-128">Atualizar um telefone de 5.4.X.X.X que foi protegido com "Bloqueio de Dispositivo" para 5.5.1.X com "Bloqueio de Telefone" não herdará o código PIN de "Bloqueio de Dispositivo", o que pode deixar o telefone sem segurança.</span><span class="sxs-lookup"><span data-stu-id="50ad6-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="50ad6-129">Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro perfil de dispositivo Polycom para dar aos usuários o controle do tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="50ad6-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="50ad6-130">As atualizações de firmware são gerenciadas pelo Serviço Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="50ad6-131">Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.</span><span class="sxs-lookup"><span data-stu-id="50ad6-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="50ad6-132">Dependendo do tempo de inatividade no telefone e nos intervalos de votação, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="50ad6-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="50ad6-133">Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ como `false` .</span><span class="sxs-lookup"><span data-stu-id="50ad6-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Captura de tela mostrando a implantação de telefones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="50ad6-135">Quando um novo firmware estiver disponível e pronto para download e instalação, o telefone notificará o usuário.</span><span class="sxs-lookup"><span data-stu-id="50ad6-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="50ad6-136">Os telefones Polycom notificarão o usuário e fornecerão a ele uma opção para **atualizar** ou **adiar.**</span><span class="sxs-lookup"><span data-stu-id="50ad6-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![Captura de tela mostrando as opções Atualizar e Adiar.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="50ad6-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate.**</span><span class="sxs-lookup"><span data-stu-id="50ad6-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Captura de tela mostrando a opção SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="50ad6-140">Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros.</span><span class="sxs-lookup"><span data-stu-id="50ad6-140">You can also choose to manage firmware updates using a partner provisioning system.</span></span> <span data-ttu-id="50ad6-141">Para o gerenciamento do sistema de provisionamento de parceiros, incluindo personalização avançada de telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="50ad6-141">For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="50ad6-142">Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="50ad6-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="50ad6-143">Etapa 5 - Configurações de configuração e infraestrutura do telefone</span><span class="sxs-lookup"><span data-stu-id="50ad6-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="50ad6-144">Você pode configurar as opções e políticas de telefone mais usadas usando cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-144">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets.</span></span> <span data-ttu-id="50ad6-145">Consulte [Set-CsIPPhonePolicy para obter](https://technet.microsoft.com/library/mt629497.aspx) detalhes desses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="50ad6-145">See [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="50ad6-146">Para planejamento de infraestrutura de rede, consulte [a Estrutura de Operações do Skype.](https://www.skypeoperationsframework.com/)</span><span class="sxs-lookup"><span data-stu-id="50ad6-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="50ad6-147">Etapa 6 - Preparar-se para que os usuários se inscrevam</span><span class="sxs-lookup"><span data-stu-id="50ad6-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="50ad6-148">Para permitir que os usuários se inscrevam com êxito em um telefone do Skype for Business Online e façam chamadas, você precisa garantir que os usuários têm as licenças corretas atribuídas.</span><span class="sxs-lookup"><span data-stu-id="50ad6-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="50ad6-149">No mínimo, você precisará atribuir uma licença do Sistema de Telefonia e um Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="50ad6-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="50ad6-150">Para obter informações adicionais, você pode ver o licenciamento de complementos do [Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e do Microsoft Teams e atribuir licenças do Skype for Business e do Microsoft [Teams.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="50ad6-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="50ad6-151">Para saber mais sobre planos de chamada, leia o Sistema de Telefonia [e os Planos de Chamada](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="50ad6-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="50ad6-152">**As opções de login** disponíveis para usuários online são:</span><span class="sxs-lookup"><span data-stu-id="50ad6-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="50ad6-153">Os usuários **com telefones Polycom VVX 5XX/6XX verão:**</span><span class="sxs-lookup"><span data-stu-id="50ad6-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando o logon de telefones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="50ad6-155">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="50ad6-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando o logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="50ad6-157">Para obter detalhes sobre as opções de conexão com suporte do fabricante, consulte [Obter telefones para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="50ad6-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="50ad6-158">**ID do Usuário** Usando o teclado virtual ou o teclado virtual do telefone (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-158">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="50ad6-159">Por exemplo, eles devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="50ad6-159">For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="50ad6-161">A autenticação de PIN não é suportada para o Skype for Business Online para telefones IP de parceiros e LPE.</span><span class="sxs-lookup"><span data-stu-id="50ad6-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="50ad6-162">**Usando um computador** Quando o software Better Together over Ethernet (BToE) é instalado no computador do usuário e habilitado, os usuários podem entrar em seus telefones usando a janela de autenticação no aplicativo Windows Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="50ad6-163">Consulte a Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e [Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.</span><span class="sxs-lookup"><span data-stu-id="50ad6-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="50ad6-164">Os usuários devem usar o nome de usuário e a senha da organização para entrar no telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-164">Users are required to use their organization's user name and password to sign in to the phone.</span></span> <span data-ttu-id="50ad6-165">Por exemplo, eles devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="50ad6-165">For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="50ad6-167">**Usando uma Web Sign-in:** essa é uma nova maneira de os usuários online autenticarem usando um navegador da Web padrão.</span><span class="sxs-lookup"><span data-stu-id="50ad6-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="50ad6-168">Os usuários receberão um conjunto de instruções a seguir quando usarem um navegador para entrar.</span><span class="sxs-lookup"><span data-stu-id="50ad6-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="50ad6-169">Os usuários **com telefones Polycom VVX 5XX/6XX verão:**</span><span class="sxs-lookup"><span data-stu-id="50ad6-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando as instruções do Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="50ad6-171">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="50ad6-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando instruções do Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="50ad6-173">O código gerado expirará em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="50ad6-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="50ad6-174">Quando expirar, o usuário terá que clicar em **Repetir** ou **OK** para gerar um novo código, dependendo do telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="50ad6-175">Os usuários **com telefones Polycom VVX 5XX/6XX verão:**</span><span class="sxs-lookup"><span data-stu-id="50ad6-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![Captura de tela mostrando o código Polycom expirado](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="50ad6-177">Os usuários **com telefones Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="50ad6-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Captura de tela mostrando o código Yealink expirado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="50ad6-179">Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome de usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Captura de tela mostrando a verificação de email](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="50ad6-181">Insira o código mostrado no telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-181">Enter the code shown on the phone.</span></span>
    
     ![Captura de tela mostrando a inserção de código na tela de logon](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="50ad6-183">Verifique se o site mostra "[Nome do fabricante do telefone] Telefone Certificado do **Skype for Business"** e clique em **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="50ad6-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![Captura de tela mostrando a verificação de nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="50ad6-185">Clique nas credenciais do usuário ou clique em **Usar outra conta:**</span><span class="sxs-lookup"><span data-stu-id="50ad6-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Captura de tela mostrando as opções de credencial](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="50ad6-187">Quando a página a seguir é exibida, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="50ad6-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![Captura de tela mostrando a mensagem de confirmação](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="50ad6-189">Telefones LPE para Skype for Business Online são suportados apenas por meio de conexão USB.</span><span class="sxs-lookup"><span data-stu-id="50ad6-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="50ad6-190">**Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação com suporte no momento, incluindo Integração do Exchange, Autenticação moderna com MFA (Autenticação Multifa factor) e Skype for Business Online e local.</span><span class="sxs-lookup"><span data-stu-id="50ad6-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50ad6-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="50ad6-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="50ad6-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="50ad6-192">**Exchange**</span></span> <br/> |<span data-ttu-id="50ad6-193">**Método Sign-In telefone**</span><span class="sxs-lookup"><span data-stu-id="50ad6-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="50ad6-194">**Acesso ao Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="50ad6-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="50ad6-195">**Exchange Access com a Auth Moderna e a MFA desabilitadas**</span><span class="sxs-lookup"><span data-stu-id="50ad6-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="50ad6-196">**Exchange Access com a Auth Moderna e MFA habilitada**</span><span class="sxs-lookup"><span data-stu-id="50ad6-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="50ad6-197">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-197">Online</span></span>  <br/> |<span data-ttu-id="50ad6-198">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-198">Online</span></span>  <br/> |<span data-ttu-id="50ad6-199">Entrar na Web</span><span class="sxs-lookup"><span data-stu-id="50ad6-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="50ad6-200">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-200">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-201">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-201">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-202">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-202">Yes</span></span>  <br/> |
|<span data-ttu-id="50ad6-203">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-203">Online</span></span>  <br/> |<span data-ttu-id="50ad6-204">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-204">Online</span></span>  <br/> |<span data-ttu-id="50ad6-205">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="50ad6-205">Username/Password</span></span>  <br/> |<span data-ttu-id="50ad6-206">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-206">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-207">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-207">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-208">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-208">No</span></span>  <br/> |
|<span data-ttu-id="50ad6-209">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-209">Online</span></span>  <br/> |<span data-ttu-id="50ad6-210">Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-210">On-premises</span></span>  <br/> |<span data-ttu-id="50ad6-211">Entrar na Web</span><span class="sxs-lookup"><span data-stu-id="50ad6-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="50ad6-212">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-212">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-213">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-213">No</span></span>  <br/> |<span data-ttu-id="50ad6-214">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-214">No</span></span>  <br/> |
|<span data-ttu-id="50ad6-215">Online</span><span class="sxs-lookup"><span data-stu-id="50ad6-215">Online</span></span>  <br/> |<span data-ttu-id="50ad6-216">Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-216">On-Premises</span></span>  <br/> |<span data-ttu-id="50ad6-217">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="50ad6-217">Username/Password</span></span>  <br/> |<span data-ttu-id="50ad6-218">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-218">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-219">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-219">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-220">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-220">No</span></span>  <br/> |
|<span data-ttu-id="50ad6-221">Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-221">On-premises</span></span>  <br/> |<span data-ttu-id="50ad6-222">Online/Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="50ad6-223">Autenticação de PIN</span><span class="sxs-lookup"><span data-stu-id="50ad6-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="50ad6-224">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-224">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-225">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-225">No</span></span>  <br/> |<span data-ttu-id="50ad6-226">Não</span><span class="sxs-lookup"><span data-stu-id="50ad6-226">No</span></span>  <br/> |
|<span data-ttu-id="50ad6-227">Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-227">On-premises</span></span>  <br/> |<span data-ttu-id="50ad6-228">Online/Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="50ad6-229">Nome de usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="50ad6-229">Username/Password</span></span>  <br/> |<span data-ttu-id="50ad6-230">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-230">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-231">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-231">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-232">Não disponível</span><span class="sxs-lookup"><span data-stu-id="50ad6-232">N/A</span></span>  <br/> |
|<span data-ttu-id="50ad6-233">Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-233">On-premises</span></span>  <br/> |<span data-ttu-id="50ad6-234">Online/Local</span><span class="sxs-lookup"><span data-stu-id="50ad6-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="50ad6-235">Entrar por computador (BTOE)</span><span class="sxs-lookup"><span data-stu-id="50ad6-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="50ad6-236">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-236">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-237">Sim</span><span class="sxs-lookup"><span data-stu-id="50ad6-237">Yes</span></span>  <br/> |<span data-ttu-id="50ad6-238">Não disponível</span><span class="sxs-lookup"><span data-stu-id="50ad6-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="50ad6-239">**Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro de telefone IP.</span><span class="sxs-lookup"><span data-stu-id="50ad6-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="50ad6-240">Para obter o conjunto completo de recursos e obter mais informações sobre os recursos de cada fabricante de telefone, consulte Obter telefones [para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="50ad6-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="50ad6-241">**O Bloqueio de** Telefone é um recurso introduzido recentemente em telefones certificados pelo Skype for Business que é usado para proteger um telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="50ad6-242">Se habilitado, os usuários serão solicitados a criar um PIN após a autenticação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="50ad6-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="50ad6-243">Depois de criados, os telefones serão travados quando o tempo ocioso definido expirar, o usuário bloqueará manualmente o telefone ou sincronizará o bloqueio do telefone com o bloqueio do computador usando o Emparelhamento de Telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="50ad6-244">Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone desatará o usuário ou exigirá o código de um administrador para desbloquear o telefone, mas isso variará dependendo do parceiro de telefone.</span><span class="sxs-lookup"><span data-stu-id="50ad6-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="50ad6-245">O PIN do usuário deve ter entre 6 e 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="50ad6-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="50ad6-246">Você pode desabilitar o Phone-Lock para sua organização (que é habilitado por padrão), alterar o tempo ocioso e escolher se os usuários podem fazer chamadas telefônicas enquanto estão bloqueados ou não usando configurações de banda.</span><span class="sxs-lookup"><span data-stu-id="50ad6-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="50ad6-247">Consulte [Set-CsUCPhoneConfiguration para](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) obter mais detalhes sobre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="50ad6-247">See [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="50ad6-248">Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="50ad6-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="50ad6-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="50ad6-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="50ad6-250">O BToE é um mecanismo de problema para telefones IP do parceiro que emparelha o telefone de um usuário com o aplicativo Windows Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="50ad6-251">O BToE permite que os usuários:</span><span class="sxs-lookup"><span data-stu-id="50ad6-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="50ad6-252">Entre no telefone IP usando o aplicativo da área de trabalho do Skype for Business (usando um computador)</span><span class="sxs-lookup"><span data-stu-id="50ad6-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="50ad6-253">Sincronizar Phone-Lock com bloqueio de computador</span><span class="sxs-lookup"><span data-stu-id="50ad6-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="50ad6-254">Clique para ligar</span><span class="sxs-lookup"><span data-stu-id="50ad6-254">Click to call</span></span>
    
<span data-ttu-id="50ad6-255">O BToE pode ser configurado para operar em dois modos: *Automático* (padrão) e *Manual.*</span><span class="sxs-lookup"><span data-stu-id="50ad6-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="50ad6-256">Ele também pode ser habilitado (padrão)/desabilitado para usuários que usam as configurações em banda do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="50ad6-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="50ad6-257">Ao operar no *modo Manual,*  os usuários terão que realizar uma etapa adicional para emparelhar o telefone com o aplicativo Windows.</span><span class="sxs-lookup"><span data-stu-id="50ad6-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="50ad6-258">**Para implantar o BToE para os usuários**</span><span class="sxs-lookup"><span data-stu-id="50ad6-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="50ad6-259">Conecte o computador ao telefone usando a porta do computador.</span><span class="sxs-lookup"><span data-stu-id="50ad6-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Captura de tela mostrando a conexão com um computador](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="50ad6-261">Baixe e instale o software BToE mais recente do site do fabricante nos links abaixo.</span><span class="sxs-lookup"><span data-stu-id="50ad6-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="50ad6-262">Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administradores, como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="50ad6-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="50ad6-263">Para saber como usar o Configuration Manager, consulte [Pacotes e programas no Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="50ad6-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="50ad6-264">Site de download de software BToE polycom</span><span class="sxs-lookup"><span data-stu-id="50ad6-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="50ad6-265">Yealink BToE Software Download</span><span class="sxs-lookup"><span data-stu-id="50ad6-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="50ad6-266">AudioCodes BToE Software Downloads</span><span class="sxs-lookup"><span data-stu-id="50ad6-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="50ad6-267">A configuração do servidor para BToE está definida como **Modo** Habilitado e **Automático** por padrão.</span><span class="sxs-lookup"><span data-stu-id="50ad6-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="50ad6-268">Para alterar essas configurações, consulte [Set-CsIPPhonePolicy.](https://technet.microsoft.com/library/mt629497.aspx)</span><span class="sxs-lookup"><span data-stu-id="50ad6-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="50ad6-269">No momento, o BToE não tem suporte em plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="50ad6-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="50ad6-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="50ad6-270">Related topics</span></span>
[<span data-ttu-id="50ad6-271">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50ad6-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="50ad6-272">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="50ad6-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="50ad6-273">Disponibilidade de audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="50ad6-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
