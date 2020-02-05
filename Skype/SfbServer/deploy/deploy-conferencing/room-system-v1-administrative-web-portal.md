---
title: Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Os sistemas de salas Skype v1 do Skype for Business Server v1 (SRS v1, anteriormente conhecido como sistema de sala do Lync) é um portal da Web que as organizações podem usar para manter seus sistemas de salas de conferência do Skype. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: 558baac64bdb1e21ed710cb4dafb063ce75a62de
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768514"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="3bff6-105">Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bff6-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="3bff6-106">Os sistemas de salas Skype v1 do Skype for Business Server v1 (SRS v1, anteriormente conhecido como sistema de sala do Lync) é um portal da Web que as organizações podem usar para manter seus sistemas de salas de conferência do Skype.</span><span class="sxs-lookup"><span data-stu-id="3bff6-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="3bff6-107">Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="3bff6-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="3bff6-108">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="3bff6-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="3bff6-109">Para usar esse recurso, o portal da Web administrativo do SRS v1 precisa ser implantado em cada servidor front-end do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bff6-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="3bff6-110">Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="3bff6-111">Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bff6-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="3bff6-112">Depois que o portal da Web administrativo do SRS v1 é implantado no servidor, os administradores podem verificar o status dos dispositivos SRS v1 ao fazer logon no site de seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="3bff6-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bff6-113">Baixe o [portal da Web administrativo Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="3bff6-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="3bff6-114">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="3bff6-114">In this topic:</span></span>

- [<span data-ttu-id="3bff6-115">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="3bff6-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="3bff6-116">Instalar o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="3bff6-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="3bff6-117">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="3bff6-118">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="3bff6-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="3bff6-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="3bff6-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="3bff6-120">Para usar o Portal da Web Administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="3bff6-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bff6-p104">Se o servidor estiver configurado com a autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não tenha ingressado no domínio, haverá falha na autenticação Kerberos e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou com autenticação NTLM e TLS-DSK (sem Kerberos), ou ingresse o computador com SRS no domínio.</span><span class="sxs-lookup"><span data-stu-id="3bff6-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="3bff6-123">Instale as atualizações cumulativas do Skype for Business Server na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bff6-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="3bff6-124">Para obter a atualização ou ver o que está incluído nele, confira [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="3bff6-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="3bff6-125">Crie um usuário do Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="3bff6-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="3bff6-126">O portal da Web administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bff6-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="3bff6-127">O nome de usuário nos exemplos fornecidos é LRSApp.</span><span class="sxs-lookup"><span data-stu-id="3bff6-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="3bff6-128">Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="3bff6-p106">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a este grupo serão autorizados a ver a lista de salas e a executar determinados comandos, como coletar logs.</span><span class="sxs-lookup"><span data-stu-id="3bff6-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="3bff6-131">Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="3bff6-p107">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para o gerenciamento em massa de salas do Skype, consulte a etapa 5. </span><span class="sxs-lookup"><span data-stu-id="3bff6-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Lista de grupos de administradores com função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="3bff6-135">Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="3bff6-136">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança.</span><span class="sxs-lookup"><span data-stu-id="3bff6-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="3bff6-137">Os usuários habilitados para SIP que são adicionados a este grupo têm autorização para usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3bff6-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="3bff6-138">Adicione LRSFullAccessAdminGroup como um membro de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Página de membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="3bff6-140">Crie um usuário do Active Directory compatível com SIP com o nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="3bff6-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="3bff6-141">Adicione este usuário ao LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Página de membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="3bff6-143">Instale o [ASP.NET MVC 4 para Visual Studio 2010 SP1 e Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="3bff6-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="3bff6-144">Instalar o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="3bff6-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="3bff6-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="3bff6-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="3bff6-146">Baixe o [portal da Web administrativo Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="3bff6-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="3bff6-147">Para instalar o portal da Web administrativo do SRS v1, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3bff6-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="3bff6-148">Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="3bff6-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="3bff6-149">Para instalar o portal da sala de reunião, baixe o **MeetingRoomPortalInstaller. msi** e, em seguida, execute-o como administrador.</span><span class="sxs-lookup"><span data-stu-id="3bff6-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="3bff6-150">Abra o arquivo Web. config do seguinte local:</span><span class="sxs-lookup"><span data-stu-id="3bff6-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="3bff6-151">% Program Files%\Skype for Business Server 2015 \ Web Components\Meeting sala Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="3bff6-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="3bff6-152">No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2 na seção "[configurar seu ambiente para o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="3bff6-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="3bff6-153">Como o portal de administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="3bff6-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="3bff6-154">Se esse usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="3bff6-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="3bff6-155">Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="3bff6-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="3bff6-156">Verificar a instalação do portal da Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="3bff6-157">Para verificar a instalação do portal da Web administrativo do SRS v1, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3bff6-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="3bff6-158">Em um servidor front-end, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="3bff6-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="3bff6-159">https://\<FE-servidor\>/lRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="3bff6-160">Você não verá nenhum erro, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="3bff6-160">You should not see any errors, as shown in the following image:</span></span>

     ![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="3bff6-162">Se você não vir nenhum erro, tente acessar a seguinte URL a partir de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="3bff6-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="3bff6-163">https://\<FE-servidor\>/lRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="3bff6-164">Para acessar a página, você precisará adicionar os registros DNS conforme descrito em "[registros de DNS necessários para a entrada automática do cliente](https://go.microsoft.com/fwlink/p/?LinkId=318056)".</span><span class="sxs-lookup"><span data-stu-id="3bff6-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="3bff6-165">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="3bff6-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="3bff6-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="3bff6-167">Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas SRS ao entrar no portal da Web administrativo do SRS V1 a partir de um navegador.</span><span class="sxs-lookup"><span data-stu-id="3bff6-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="3bff6-168">Entrar</span><span class="sxs-lookup"><span data-stu-id="3bff6-168">Sign in</span></span>

1. <span data-ttu-id="3bff6-169">Acesse a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="3bff6-169">Browse to the following URL:</span></span>

    <span data-ttu-id="3bff6-170">https://\<FE-servidor\>/lRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="3bff6-171">Insira as credenciais para a conta LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="3bff6-173">Página de resumo do portal de Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="3bff6-174">A página Resumo fornece as seguintes informações para todas as salas SRS implantadas no servidor:</span><span class="sxs-lookup"><span data-stu-id="3bff6-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="3bff6-175">**Marca de formatação** O nome personalizado que o administrador fornece à sala.</span><span class="sxs-lookup"><span data-stu-id="3bff6-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="3bff6-176">A marca pode ser definida no portal clicando no nome da sala.</span><span class="sxs-lookup"><span data-stu-id="3bff6-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="3bff6-177">**Integridade** do O status de integridade da sala, que é derivado do status de integridade da agregação da sala, que é mostrado na seção integridade da página de configurações da sala.</span><span class="sxs-lookup"><span data-stu-id="3bff6-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="3bff6-178">**Próxima reunião** A data e a hora em que a próxima reunião está agendada.</span><span class="sxs-lookup"><span data-stu-id="3bff6-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="3bff6-179">**Versão do SRS, fabricante, modelo** Esses valores são predefinidos no SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="3bff6-180">Dependendo do fabricante, esses campos podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="3bff6-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="3bff6-181">**Última atualização** Exibe a última vez que a página da Web foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="3bff6-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Exibição resumida do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="3bff6-183">Você só verá o menu gerenciamento em massa se fizer parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="3bff6-184">Informações da sala de SRS</span><span class="sxs-lookup"><span data-stu-id="3bff6-184">SRS Room Information</span></span>

<span data-ttu-id="3bff6-185">A seção informações da sala do portal permite que você visualize e configure salas individuais de SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="3bff6-186">Ele contém quatro seções: configurações, detalhes, registro em log e integridade.</span><span class="sxs-lookup"><span data-stu-id="3bff6-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="3bff6-187">Configurações</span><span class="sxs-lookup"><span data-stu-id="3bff6-187">Settings</span></span>

<span data-ttu-id="3bff6-188">Na seção Configurações, você pode definir a senha, a marca de sala e os níveis de volume padrão da sala.</span><span class="sxs-lookup"><span data-stu-id="3bff6-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="3bff6-189">Se você definir essas configurações, as alterações serão replicadas somente após a reinicialização do console do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="3bff6-190">Você só verá as configurações de atualizações do sistema para dispositivos SRS usando o Release 15,12 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="3bff6-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Configurações da sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="3bff6-192">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3bff6-192">Details</span></span>

<span data-ttu-id="3bff6-193">A seção detalhes fornece um resumo somente leitura das configurações da sala de SRS, incluindo: o tempo da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações de alto-falante, microfone e toque padrão; versões URI SIP; número de telas e detalhes sobre cada tela; status e atividade.</span><span class="sxs-lookup"><span data-stu-id="3bff6-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Visão detalhada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="3bff6-195">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3bff6-195">Troubleshooting</span></span>

<span data-ttu-id="3bff6-196">A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local específico.</span><span class="sxs-lookup"><span data-stu-id="3bff6-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="3bff6-197">Você também pode reiniciar o console do SRS (interface do usuário do SRS) ou reiniciar o sistema inteiro.</span><span class="sxs-lookup"><span data-stu-id="3bff6-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="3bff6-198">Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="3bff6-199">Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs.</span><span class="sxs-lookup"><span data-stu-id="3bff6-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="3bff6-200">A atualização da página dará o status mais recente.</span><span class="sxs-lookup"><span data-stu-id="3bff6-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="3bff6-201">Geral</span><span class="sxs-lookup"><span data-stu-id="3bff6-201">Health</span></span>

<span data-ttu-id="3bff6-202">A seção integridade fornece uma indicação visual da integridade da conexão do servidor do Skype for Business, do dispositivo de áudio, do dispositivo de vídeo, do estado de resiliência e do dispositivo de tela.</span><span class="sxs-lookup"><span data-stu-id="3bff6-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Portal de administração do Lync System da sala integridade](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="3bff6-204">Anotações adicionais sobre o portal administrativo da Web</span><span class="sxs-lookup"><span data-stu-id="3bff6-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="3bff6-205">As alterações de configuração são aplicadas somente após o sistema SRS ser reiniciado. > se a senha da conta LRSApp expirar, você não poderá ver o status das salas.</span><span class="sxs-lookup"><span data-stu-id="3bff6-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="3bff6-206">Configure a senha da conta do LRSAppuser para que ela nunca expire ou atualize a senha quando ela estiver próxima de expiração. > o portal da Web administrativo do SRS só tem suporte para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="3bff6-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="3bff6-207">Gerenciamento em massa</span><span class="sxs-lookup"><span data-stu-id="3bff6-207">Bulk management</span></span>

<span data-ttu-id="3bff6-208">O gerenciamento em massa de salas SRS é um recurso projetado para administradores de ti avançados, simplificar o fluxo de trabalho e habilitá-los com uma ferramenta conveniente que economiza tempo para gerenciar remotamente várias salas de maneira em massa.</span><span class="sxs-lookup"><span data-stu-id="3bff6-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="3bff6-209">Para ver essa funcionalidade, o usuário precisa ser provisionado como membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="3bff6-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="3bff6-210">Não há limite quanto ao número de salas SRS que você pode selecionar para gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="3bff6-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="3bff6-211">No entanto, você só pode executar uma operação de gerenciamento em massa de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3bff6-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="3bff6-212">Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e clique no menu gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="3bff6-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="3bff6-213">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="3bff6-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="3bff6-214">Por que não consigo me conectar ao portal administrativo da Web?</span><span class="sxs-lookup"><span data-stu-id="3bff6-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="3bff6-215">Ao abrir https://localhost/lrs, você poderá ver a página de entrada, mas quando digitar as suas credenciais, não poderá se conectar.</span><span class="sxs-lookup"><span data-stu-id="3bff6-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="3bff6-216">Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal administrativo da Web.</span><span class="sxs-lookup"><span data-stu-id="3bff6-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="3bff6-217">Por que não consigo ver o SRS v1 no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="3bff6-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="3bff6-218">Verifique se você tem contas do SRS em sua implantação e se elas são criadas de acordo com as recomendações de implantação do portal de Web administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="3bff6-219">Certifique-se de que as contas do SRS sejam provisionadas usando enable-CsMeetingRoom, not Enable-CsUser, no servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3bff6-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="3bff6-220">Se você tiver criado contas do SRS e não conseguir ver as contas no portal administrativo da Web, colete os logs do servidor usando a ferramenta de log do Skype for Business Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="3bff6-221">Se você tiver criado contas do SRS e não conseguir ver as contas no portal administrativo da Web, colete os logs do cliente usando o Fiddler e também copie o log do console das ferramentas de desenvolvimento do navegador e envie-os para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="3bff6-222">Você também pode modificar o valor de nível de rastreamento no Web. config para obter um log mais detalhado.</span><span class="sxs-lookup"><span data-stu-id="3bff6-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="3bff6-223">Por que não consigo ver o status do SRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="3bff6-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="3bff6-224">Certifique-se de que a conta de usuário do LRSApp seja compatível com SIP.</span><span class="sxs-lookup"><span data-stu-id="3bff6-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="3bff6-225">Se você ainda estiver com problemas, colete o arquivo **trace. log** no sistema SRS de D:\Tracing\LRSAdminLogs\, e envie-o para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="3bff6-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="3bff6-226">Por que não consigo ver os menus de gerenciamento em massa do SRS no portal administrativo da Web?</span><span class="sxs-lookup"><span data-stu-id="3bff6-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="3bff6-227">Verifique se a conta de usuário do LRSApp está habilitada para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="3bff6-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="3bff6-228">O portal da Web administrativo do SRS v1 funciona com salas do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3bff6-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="3bff6-229">Não.</span><span class="sxs-lookup"><span data-stu-id="3bff6-229">No.</span></span>


