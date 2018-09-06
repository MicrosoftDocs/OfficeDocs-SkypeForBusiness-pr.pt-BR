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
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: Aprenda as etapas de implantação para obter o firmware correto, atualize-o se necessário, atribua licenças e defina configurações para os telefones do Skype for Business Online
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780058"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="effa5-103">Implantar telefones do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="effa5-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="effa5-104">Este guia de implantação ajudará você a implantar os telefones IP do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="effa5-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="effa5-p101">Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, o que é importante para fazer negócios. Os usuários com números de telefone podem fazer chamadas de voz em todos os dispositivos com o Skype for Business incluindo telefones IP, PCs e dispositivos móveis. Você pode saber mais sobre os telefones IP do Skype for Business consultando Obter telefones para o Skype for Business Online.[ ](getting-phones-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="effa5-p101">In all types of businesses, having a phone number allows users to make and get voice calls and it is an important requirement to do business. Users that have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by seeing, [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="effa5-108">Etapas de implantação para telefones IP</span><span class="sxs-lookup"><span data-stu-id="effa5-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="effa5-109">Etapa 1 - Baixe os guias de administrador do fabricante e manuais do telefone</span><span class="sxs-lookup"><span data-stu-id="effa5-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="effa5-110">Antes de iniciar, é recomendável baixar os guias de administração do fabricante e dos manuais do usuário do telefone.</span><span class="sxs-lookup"><span data-stu-id="effa5-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="effa5-111">Para telefones Polycom, consulte o [Guia de implantação Polycom]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span><span class="sxs-lookup"><span data-stu-id="effa5-111">For Polycom phones, see the http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="effa5-112">Para telefones Yealink, consulte [Solução para telefones SIP HD Yealink para Skype for Business](http://www.yealink.com/products_top_2.html).</span><span class="sxs-lookup"><span data-stu-id="effa5-112">For Yealink phones, see [Yealink Skype for Business® HD IP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="effa5-113">Para telefones AudioCodes, consulte o [Guia de Gerenciamento de Provisionamento Audiocodes ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span><span class="sxs-lookup"><span data-stu-id="effa5-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="effa5-114">Etapa 2 - Certifique-se de que você está adquirindo ou migrando um telefone IP e firmware compatíveis com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="effa5-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="effa5-p102">Um telefone e um firmware compatíveis com o Skype for Business Online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é verdade. Para ter certeza de que está comprando ou provisionando um telefone e firmware compatíveis, consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="effa5-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) guide.</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="effa5-117">Etapa 3 - Verificar se o firmware certo foi instalado e atualizá-lo, se necessário</span><span class="sxs-lookup"><span data-stu-id="effa5-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="effa5-p103">Verifique a versão do firmware do seu telefone. No caso de:</span><span class="sxs-lookup"><span data-stu-id="effa5-p103">To check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="effa5-120">**Telefones Polycom VVX**, vá para **Configurações** > **Status** > **Plataforma** > **Aplicativo** > **Principal**.</span><span class="sxs-lookup"><span data-stu-id="effa5-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="effa5-121">**Telefones Yealink**, vá para **Status** na tela do telefone principal.</span><span class="sxs-lookup"><span data-stu-id="effa5-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="effa5-122">**Telefones AudioCodes**, acesse **Menu** > **Status do Dispositivo** > **Versão do firmware** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="effa5-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="effa5-p104">Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante. Veja os links acima para acessar os guias de usuário e os manuais de telefone.</span><span class="sxs-lookup"><span data-stu-id="effa5-p104">For remote access to phone details refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="effa5-125">**Telefones Lync Phone Edition (LPE)**, vá para **Menu** > **Informações do Sistema** na tela inicial.</span><span class="sxs-lookup"><span data-stu-id="effa5-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="effa5-126">Etapa 4 - Considerações sobre atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="effa5-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="effa5-p105">O firmware da Polycom anterior à versão 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que foi substituído pelo "Bloqueio de telefone" implementado no Skype for Business. A atualização de um telefone versão 5.4.X.X que era protegido pelo "Bloqueio de Dispositivo" para a versão 5.5.1.X com o "Bloqueio de Telefone" não herdará o código PIN do "Bloqueio de Dispositivo", o que pode deixar o telefone desprotegido. Para os usuários que têm o "Bloqueio de Dispositivo" ativado, é necessário habilitar o seguinte parâmetro do Perfil de Dispositivo Polycom para ter controle do momento da atualização (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="effa5-p105">Polycom firmware prior to 5.5.1.X had a manufacturer specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock". Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock", which can leave the phone unsecured. For users who have activated "Device-Lock", you need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="effa5-p106">As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado no servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade do telefone e dos intervalos de sondagem, as versões certificadas atuais serão baixadas e instaladas automaticamente. Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ como `false`.</span><span class="sxs-lookup"><span data-stu-id="effa5-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![Implementar telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="effa5-p107">Quando um novo firmware está disponível e pronto para download e instalação, o telefone notifica o usuário. Os telefones Polycom notificam o usuário e oferecem as opções **Atualizar** ou **Adiar**.</span><span class="sxs-lookup"><span data-stu-id="effa5-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update**, or **Postpone**.</span></span>
  
![Implementar telefones.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="effa5-138">Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.</span><span class="sxs-lookup"><span data-stu-id="effa5-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![Implementar telefones.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="effa5-p108">Você também pode optar por gerenciar as atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros incluindo a personalização avançada do telefone, consulte os guias de administração do fabricante.</span><span class="sxs-lookup"><span data-stu-id="effa5-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="effa5-142">[!CUIDADO] Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiro) para evitar loops de atualização.</span><span class="sxs-lookup"><span data-stu-id="effa5-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="effa5-143">Etapa 5 - Configuração e infraestrutura do telefone</span><span class="sxs-lookup"><span data-stu-id="effa5-143">Step 5 - Configure and infrastructure phone settings</span></span>

<span data-ttu-id="effa5-p109">Você pode configurar as opções e as políticas do telefone usadas com mais frequência usando os cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.</span><span class="sxs-lookup"><span data-stu-id="effa5-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="effa5-146">Para o planejamento da infraestrutura de rede, consulte [Estrutura das operações do Skype](https://www.skypeoperationsframework.com/).</span><span class="sxs-lookup"><span data-stu-id="effa5-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/) andDeploy, Migrate, and Roll Out.</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="effa5-147">Etapa 6 - Preparação para entrada dos usuários</span><span class="sxs-lookup"><span data-stu-id="effa5-147">Step 6 - Preparing for users to sign-in</span></span>

<span data-ttu-id="effa5-p110">Para habilitar os usuários a entrarem com sucesso em um telefone do Skype for Business Online e fazer chamadas, você precisa verificar se licenças corretas foram atribuídas. No mínimo, será necessário atribuir uma licença do Plano de Telefonia e um Plano de Chamadas. Para obter mais informações, consulte [Licenças Complementares do Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e[Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="effa5-p110">To enable users to successfully sign-on to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum you will need to assign a Skype for Business Cloud PBX license and a PSTN Calling plan. For additional information you can see [Skype for Business add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) .</span></span>
  
<span data-ttu-id="effa5-151">Você pode encontrar mais informações sobre Planos de Chamadas em [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="effa5-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="effa5-152">As **opções de logon** que estão disponíveis para os usuários online são:</span><span class="sxs-lookup"><span data-stu-id="effa5-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="effa5-153">Os usuários com telefones **Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-153">For those users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Implementar telefones.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="effa5-155">Os usuários com os telefones **Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-155">For those users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="effa5-157">Para obter detalhes sobre as opções entrada aceitas pelo fabricante, consulte [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="effa5-157">For details on sign-in options supported by manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="effa5-p111">**ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome e a senha do usuário de sua organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como *amosm@contoso.com*  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="effa5-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="effa5-161">[!OBSERVAçãO] A autenticação de PIN não é aceita no Skype for Business Online para telefones LPE e telefones IP de parceiros.</span><span class="sxs-lookup"><span data-stu-id="effa5-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="effa5-p112">**Ao usar um PC** com o software Better Together over Ethernet (BToE) instalado e habilitado, os usuários podem fazer logon no telefone usando a janela de autenticação do aplicativo Skype for Business para Windows. Consulte[Etapa 7 (opcional) - Se você tem emparelhamento de dispositivo e Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.</span><span class="sxs-lookup"><span data-stu-id="effa5-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log into their phone using the authentication window on their Windows Skype for Business App. See[Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="effa5-p113">[!OBSERVAçãO] Os usuários devem usar o nome de usuário e senha da organização para fazer logon no telefone. Por exemplo, os usuários devem usar o formato UPN como  *amosm@contoso.com*  para seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="effa5-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![Implementar telefones.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="effa5-p114">**Usar entrada via Web**: Essa é uma nova maneira de os usuários online autenticarem usando um navegador padrão. Eles receberão um conjunto de instruções para usar um navegador para entrar.</span><span class="sxs-lookup"><span data-stu-id="effa5-p114">**Using a** Web Sign-in: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign-in.</span></span>
    
  - <span data-ttu-id="effa5-169">Os usuários com telefones **Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-169">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Implementar telefones.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="effa5-171">Os usuários com os telefones **Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-171">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Logon de telefone Yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="effa5-p115">O código gerado expira em 15 minutos. Após expirar, o usuário terá que clicar em **Tentar novamente** ou **OK** para gerar um novo código dependendo do telefone.</span><span class="sxs-lookup"><span data-stu-id="effa5-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code depending on the phone.</span></span>
    
  - <span data-ttu-id="effa5-175">Os usuários com telefones **Polycom VVX 5XX/6XX** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-175">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![Código PIN expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="effa5-177">Os usuários com os telefones **Yealink T48G/T46G** verão:</span><span class="sxs-lookup"><span data-stu-id="effa5-177">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Logon de telefones Yealink.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="effa5-179">Usando um navegador, navegue até o endereço exibido no telefone e digite o nome do usuário do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="effa5-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![Implementar telefones.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="effa5-181">Digite o código mostrado no telefone.</span><span class="sxs-lookup"><span data-stu-id="effa5-181">Enter the code shown on the phone.</span></span>
    
     ![Implementar telefones.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="effa5-183">Verifique se o site mostra o "Telefone [nome do fabricante do telefone] **certificado pelo Skype for Business**", e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="effa5-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**", and click **Continue**.</span></span>
    
     ![Implementar telefones.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="effa5-185">Clique nas credenciais do usuário ou clique em **Usar outra conta**:</span><span class="sxs-lookup"><span data-stu-id="effa5-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![Implementar telefones.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="effa5-187">Quando a página seguinte for exibida, é seguro fechar o navegador.</span><span class="sxs-lookup"><span data-stu-id="effa5-187">Once below page is displayed, it is safe to close the browser.</span></span>
    
     ![Implementar telefones.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="effa5-189">[!OBSERVAçãO] Os telefones LPE para Skype for Business Online permitem logon somente por meio de compartilhamento USB.</span><span class="sxs-lookup"><span data-stu-id="effa5-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="effa5-190">**Implantações suportadas** A tabela abaixo mostra os tipos de autenticação permitidos para os modelos de implantação aceitos atualmente incluindo a Integração com o Exchange, Autenticação moderna com o MFA (Multi-factor Authentication, Autenticação Multifator) e o Skype for Business Online e locais.</span><span class="sxs-lookup"><span data-stu-id="effa5-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="effa5-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="effa5-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="effa5-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="effa5-192">**Exchange**</span></span> <br/> |<span data-ttu-id="effa5-193">**Método de entrada de telefone**</span><span class="sxs-lookup"><span data-stu-id="effa5-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="effa5-194">**Acesso ao Skype For Business**</span><span class="sxs-lookup"><span data-stu-id="effa5-194">**Skype For Business Access**</span></span> <br/> |<span data-ttu-id="effa5-195">**Acesso do Exchange com Autenticação Multifator e MFA desabilitados**</span><span class="sxs-lookup"><span data-stu-id="effa5-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="effa5-196">**Acesso do Exchange com Autenticação Multifator e MFA habilitados**</span><span class="sxs-lookup"><span data-stu-id="effa5-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="effa5-197">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-197">Online</span></span>  <br/> |<span data-ttu-id="effa5-198">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-198">Online</span></span>  <br/> |<span data-ttu-id="effa5-199">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="effa5-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="effa5-200">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-200">Yes</span></span>  <br/> |<span data-ttu-id="effa5-201">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-201">Yes</span></span>  <br/> |<span data-ttu-id="effa5-202">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-202">Yes</span></span>  <br/> |
|<span data-ttu-id="effa5-203">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-203">Online</span></span>  <br/> |<span data-ttu-id="effa5-204">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-204">Online</span></span>  <br/> |<span data-ttu-id="effa5-205">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="effa5-205">Username/Password</span></span>  <br/> |<span data-ttu-id="effa5-206">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-206">Yes</span></span>  <br/> |<span data-ttu-id="effa5-207">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-207">Yes</span></span>  <br/> |<span data-ttu-id="effa5-208">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-208">No</span></span>  <br/> |
|<span data-ttu-id="effa5-209">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-209">Online</span></span>  <br/> |<span data-ttu-id="effa5-210">Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-210">On-premises</span></span>  <br/> |<span data-ttu-id="effa5-211">Entrada da Web</span><span class="sxs-lookup"><span data-stu-id="effa5-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="effa5-212">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-212">Yes</span></span>  <br/> |<span data-ttu-id="effa5-213">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-213">No</span></span>  <br/> |<span data-ttu-id="effa5-214">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-214">No</span></span>  <br/> |
|<span data-ttu-id="effa5-215">Online</span><span class="sxs-lookup"><span data-stu-id="effa5-215">Online</span></span>  <br/> |<span data-ttu-id="effa5-216">Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-216">On-Premises</span></span>  <br/> |<span data-ttu-id="effa5-217">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="effa5-217">Username/Password</span></span>  <br/> |<span data-ttu-id="effa5-218">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-218">Yes</span></span>  <br/> |<span data-ttu-id="effa5-219">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-219">Yes</span></span>  <br/> |<span data-ttu-id="effa5-220">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-220">No</span></span>  <br/> |
|<span data-ttu-id="effa5-221">Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-221">On-premises</span></span>  <br/> |<span data-ttu-id="effa5-222">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="effa5-223">Autenticação por PIN</span><span class="sxs-lookup"><span data-stu-id="effa5-223">Pin Authentication</span></span>  <br/> |<span data-ttu-id="effa5-224">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-224">Yes</span></span>  <br/> |<span data-ttu-id="effa5-225">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-225">No</span></span>  <br/> |<span data-ttu-id="effa5-226">Não</span><span class="sxs-lookup"><span data-stu-id="effa5-226">No</span></span>  <br/> |
|<span data-ttu-id="effa5-227">Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-227">On-premises</span></span>  <br/> |<span data-ttu-id="effa5-228">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="effa5-229">Nome do usuário/Senha</span><span class="sxs-lookup"><span data-stu-id="effa5-229">Username/Password</span></span>  <br/> |<span data-ttu-id="effa5-230">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-230">Yes</span></span>  <br/> |<span data-ttu-id="effa5-231">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-231">Yes</span></span>  <br/> |<span data-ttu-id="effa5-232">N/D</span><span class="sxs-lookup"><span data-stu-id="effa5-232">N/A</span></span>  <br/> |
|<span data-ttu-id="effa5-233">Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-233">On-premises</span></span>  <br/> |<span data-ttu-id="effa5-234">Online/Locais</span><span class="sxs-lookup"><span data-stu-id="effa5-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="effa5-235">Entrada via PC (BTOE)</span><span class="sxs-lookup"><span data-stu-id="effa5-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="effa5-236">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-236">Yes</span></span>  <br/> |<span data-ttu-id="effa5-237">Sim</span><span class="sxs-lookup"><span data-stu-id="effa5-237">Yes</span></span>  <br/> |<span data-ttu-id="effa5-238">N/D</span><span class="sxs-lookup"><span data-stu-id="effa5-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="effa5-p116">**Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro do telefone IP. Para o conjunto completo e para saber mais sobre os recursos de cada fabricante de telefone, consulte [Obter telefones do Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="effa5-p116">**Phone features** The feature-set may slightly vary based on the IP phone partner. For complete feature set, see[Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) for more information on the features for each phone manufacturer.</span></span>
    
- <span data-ttu-id="effa5-p117">**Bloqueio de telefone** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business usado para proteção. Se habilitado, os usuários precisam criar um PIN após a autenticação bem-sucedida. Após criado, os telefones são bloqueados após o limite de tempo ocioso definido, manualmente pelo usuário, ao sincronizar o bloqueio do telefone com o bloqueio do PC usando o Emparelhamento de Telefone. Se o PIN de bloqueio de telefone incorreto for inserido várias vezes, o telefone desconectará o usuário ou exigirá um código de administrador para o desbloqueio, mas isso varia dependendo do parceiro de telefonia. O PIN do usuário deve ter entre 6 e 15 dígitos.</span><span class="sxs-lookup"><span data-stu-id="effa5-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successfully authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require a administrator's code to unlock the phone, but this will vary from depending on the phone Partner. The user's PIN should be between 6-15 digits.</span></span>
    
    <span data-ttu-id="effa5-p118"> Você pode desabilitar o bloqueio do telefone para a sua organização (é habilitado por padrão), alterar o limite de tempo ocioso e decidir se os usuários podem ou não fazer chamadas telefônicas enquanto estiverem bloqueados ou usando as configurações inband. Consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) para obter mais detalhes sobre essas configurações.</span><span class="sxs-lookup"><span data-stu-id="effa5-p118">You can disable Phone-Lock for your organization that is enabled by default, change the idle-timeout and choose if users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="effa5-248">Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivo e Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="effa5-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="effa5-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="effa5-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="effa5-p119">O BToE é um mecanismo de emparelhamento para telefones IP de parceiros que emparelha o telefone do usuário com o aplicativo do Skype for Business para Windows. Ele habilita os usuários a:</span><span class="sxs-lookup"><span data-stu-id="effa5-p119">BToE is a phone paining mechanism for Partner IP phones that pairs user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="effa5-252">Entrar no telefone IP usando o aplicativo Skype for Business para área de trabalho (usando um PC)</span><span class="sxs-lookup"><span data-stu-id="effa5-252">Sign-into their IP phone using their Skype for Business desktop app (using a PC).</span></span>
    
- <span data-ttu-id="effa5-253">Sincronizar o bloqueio de telefone com o bloqueio de PC</span><span class="sxs-lookup"><span data-stu-id="effa5-253">Synchronize phone-lock with PC lock.</span></span>
    
- <span data-ttu-id="effa5-254">Clicar para telefonar</span><span class="sxs-lookup"><span data-stu-id="effa5-254">Click to call.</span></span>
    
<span data-ttu-id="effa5-p120">O BToE pode ser configurado para operar em 2 modos;  *Automático* (padrão) e *Manual*. Ele também pode ser habilitado (padrão) ou desabilitado para usuários com configurações inband do Skype for Business. Ao operar no modo *Manual*, os usuários precisam executar um passo adicional para emparelhar o telefone com o aplicativo do Windows.</span><span class="sxs-lookup"><span data-stu-id="effa5-p120">BToE can be configured to operate in 2 modes;  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="effa5-258">**Para implantar o BToE para os usuários**</span><span class="sxs-lookup"><span data-stu-id="effa5-258">\*\*\*\* To deploy BToE to users</span></span>
  
1. <span data-ttu-id="effa5-259">Conecte o PC deles ao telefone usando a porta do PC.</span><span class="sxs-lookup"><span data-stu-id="effa5-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![Implementar telefones.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="effa5-p121">Baixe e instale o software BToE mais recente do site do fabricante usando os links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração como o SCCM (System Center Configuration Manager). Para obter ajudar sobre como usar o SCCM, consulte [Pacotes e programas no System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="effa5-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="effa5-264">Site para download do software BToE Polycom</span><span class="sxs-lookup"><span data-stu-id="effa5-264">Polycom BToE Software Download site:</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="effa5-265">Download de software BToE Yealink</span><span class="sxs-lookup"><span data-stu-id="effa5-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="effa5-266">Downloads de software BToE AudioCodes</span><span class="sxs-lookup"><span data-stu-id="effa5-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="effa5-267">Por padrão, a configuração de servidor para BToE é definida como **Ativado** e **Modo automático**.</span><span class="sxs-lookup"><span data-stu-id="effa5-267">The server setting for BToE is set to Enabled and Auto mode by default, to change those settings, seeSet-CsIPPhonePolicy.</span></span> <span data-ttu-id="effa5-268">Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="effa5-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="effa5-269">O BToE não é permitido atualmente nas plataformas Mac e VDI.</span><span class="sxs-lookup"><span data-stu-id="effa5-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="effa5-270">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="effa5-270">Related topics</span></span>
[<span data-ttu-id="effa5-271">Obter números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="effa5-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="effa5-272">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="effa5-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="effa5-273">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="effa5-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
