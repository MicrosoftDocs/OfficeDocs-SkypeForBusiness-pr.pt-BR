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
description: O Skype for Business Server o Skype Room Systems V1 (SRS v1, anteriormente conhecido como sistema de salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045894"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="cba70-105">Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cba70-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="cba70-106">O Skype for Business Server o Skype Room Systems V1 (SRS v1, anteriormente conhecido como sistema de salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="cba70-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="cba70-107">Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="cba70-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="cba70-108">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="cba70-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="cba70-109">Para usar esse recurso, o portal da Web administrativo do SRS v1 precisa ser implantado em todos os servidores front-end do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cba70-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="cba70-110">Este guia fornece instruções para os administradores sobre como instalar e configurar o portal da Web administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="cba70-111">Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e que têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cba70-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="cba70-112">Depois que o portal da Web administrativo do SRS v1 é implantado no servidor, os administradores podem verificar os dispositivos de status SRS v1 fazendo logon no site de seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="cba70-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cba70-113">Baixe o [portal da Web administrativo do Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="cba70-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="cba70-114">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="cba70-114">In this topic:</span></span>

- [<span data-ttu-id="cba70-115">Configurar seu ambiente para o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="cba70-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="cba70-116">Instalar o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="cba70-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="cba70-117">Usar o portal da Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="cba70-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="cba70-118">Configurar seu ambiente para o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="cba70-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="cba70-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="cba70-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="cba70-120">Para usar o portal da Web administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="cba70-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cba70-121">Se o servidor estiver configurado com autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status do SRS no portal administrativo.</span><span class="sxs-lookup"><span data-stu-id="cba70-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="cba70-122">Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou Ingresse o computador SRS no domínio.</span><span class="sxs-lookup"><span data-stu-id="cba70-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="cba70-123">Instale as atualizações cumulativas do Skype for Business Server na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cba70-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="cba70-124">Para obter a atualização ou ver o que está incluído nele, consulte [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="cba70-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="cba70-125">Criar um usuário do Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="cba70-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="cba70-126">O portal da Web administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cba70-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="cba70-127">O nome de usuário nos exemplos fornecidos é LRSApp.</span><span class="sxs-lookup"><span data-stu-id="cba70-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="cba70-128">Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="cba70-129">Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança.</span><span class="sxs-lookup"><span data-stu-id="cba70-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="cba70-130">Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a ver a lista de salas e executar certos comandos, como coletar logs.</span><span class="sxs-lookup"><span data-stu-id="cba70-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="cba70-131">Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="cba70-132">Criar o grupo com escopo de grupo como global e tipo de grupo como Security. SIP habilitados para usuários que são adicionados a este grupo são autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="cba70-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="cba70-133">Para incluir suporte para gerenciamento em massa de salas do Skype, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="cba70-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Lista de grupos de administração com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="cba70-135">Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="cba70-136">Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança.</span><span class="sxs-lookup"><span data-stu-id="cba70-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="cba70-137">Os usuários habilitados para SIP que são adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="cba70-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="cba70-138">Adicione LRSFullAccessAdminGroup como membro de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Página Membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="cba70-140">Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="cba70-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="cba70-141">Adicione este usuário ao LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Página Membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="cba70-143">Instale o [ASP.NET MVC 4 para o Visual Studio 2010 SP1 e o Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="cba70-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="cba70-144">Instalar o portal da Web administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="cba70-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="cba70-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="cba70-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="cba70-146">Baixe o [portal da Web administrativo do Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="cba70-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="cba70-147">Para instalar o portal da Web administrativo do SRS v1, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="cba70-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="cba70-148">Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="cba70-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="cba70-149">Para instalar o portal de sala de reunião, baixe o **MeetingRoomPortalInstaller. msi** e, em seguida, execute-o como administrador.</span><span class="sxs-lookup"><span data-stu-id="cba70-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="cba70-150">Abra o arquivo Web. config no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="cba70-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="cba70-151">% Program programas%\skype for Business Server 2015 \ Web Components\Meeting sala Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="cba70-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="cba70-152">No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2, abaixo da seção "[configurar seu ambiente para o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="cba70-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="cba70-153">Como o portal de administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="cba70-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="cba70-154">Se este usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="cba70-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="cba70-155">Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="cba70-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="cba70-156">Verificar a instalação do portal da Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="cba70-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="cba70-157">Para verificar a instalação do portal da Web administrativo do SRS v1, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cba70-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="cba70-158">Em um servidor front-end, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="cba70-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="cba70-159">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="cba70-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="cba70-160">Você não verá nenhum erro, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="cba70-160">You should not see any errors, as shown in the following image:</span></span>

     ![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="cba70-162">Se você não vir nenhum erro, tente acessar a seguinte URL de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="cba70-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="cba70-163">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="cba70-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="cba70-164">Para acessar a página, você precisará adicionar os registros DNS, conforme descrito em "[registros DNS necessários para entrada automática de cliente](https://go.microsoft.com/fwlink/p/?LinkId=318056)".</span><span class="sxs-lookup"><span data-stu-id="cba70-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="cba70-165">Usar o portal da Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="cba70-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="cba70-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="cba70-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="cba70-167">Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas do SRS entrando no portal da Web administrativo do SRS V1 a partir de um navegador.</span><span class="sxs-lookup"><span data-stu-id="cba70-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="cba70-168">Entrar</span><span class="sxs-lookup"><span data-stu-id="cba70-168">Sign in</span></span>

1. <span data-ttu-id="cba70-169">Navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="cba70-169">Browse to the following URL:</span></span>

    <span data-ttu-id="cba70-170">https:// \<fe-server\> /lRS</span><span class="sxs-lookup"><span data-stu-id="cba70-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="cba70-171">Insira as credenciais para a conta LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="cba70-173">Página de resumo do portal da Web administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="cba70-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="cba70-174">A página de resumo fornece as seguintes informações para todas as salas do SRS implantadas no servidor:</span><span class="sxs-lookup"><span data-stu-id="cba70-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="cba70-175">**Marca** O nome personalizado que o administrador fornece à sala.</span><span class="sxs-lookup"><span data-stu-id="cba70-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="cba70-176">A marca pode ser definida no portal clicando no nome da sala.</span><span class="sxs-lookup"><span data-stu-id="cba70-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="cba70-177">**Health** O status de integridade da sala, que é derivado do status de integridade de agregação da sala, que é mostrado na seção integridade da página Configurações da sala.</span><span class="sxs-lookup"><span data-stu-id="cba70-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="cba70-178">**Próxima reunião** A data e a hora em que a próxima reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="cba70-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="cba70-179">**Versão do SRS, fabricante, modelo** Esses valores são predefinidos no SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="cba70-180">Dependendo do fabricante, esses campos podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="cba70-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="cba70-181">**Última atualização** Exibe a última vez em que a página da Web foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="cba70-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Exibição resumida do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="cba70-183">Você só verá o menu de gerenciamento em massa se fizer parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="cba70-184">Informações de sala do SRS</span><span class="sxs-lookup"><span data-stu-id="cba70-184">SRS Room Information</span></span>

<span data-ttu-id="cba70-185">A seção informações de sala do portal permite que você visualize e configure salas individuais do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="cba70-186">Ele contém quatro seções: configurações, detalhes, registro em log e integridade.</span><span class="sxs-lookup"><span data-stu-id="cba70-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="cba70-187">Configurações</span><span class="sxs-lookup"><span data-stu-id="cba70-187">Settings</span></span>

<span data-ttu-id="cba70-188">Na seção Configurações, é possível definir a senha, a marca de sala e os níveis de volume padrão para a sala.</span><span class="sxs-lookup"><span data-stu-id="cba70-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="cba70-189">Se você definir essas configurações, as alterações serão replicadas somente depois que você reiniciar o console do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="cba70-190">Você verá apenas as configurações de atualizações do sistema para dispositivos SRS usando a versão 15,12 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="cba70-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Configurações de sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="cba70-192">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cba70-192">Details</span></span>

<span data-ttu-id="cba70-193">A seção detalhes fornece um resumo somente leitura das configurações da sala SRS, incluindo: o horário da última atualização; próxima reunião; últimas atualizações, manutenção e calibração; configurações de alto-falante, MIC e campainha padrão; Version URI DO SIP; número de telas e detalhes sobre cada tela; status e atividade.</span><span class="sxs-lookup"><span data-stu-id="cba70-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Exibição detalhada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="cba70-195">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="cba70-195">Troubleshooting</span></span>

<span data-ttu-id="cba70-196">A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="cba70-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="cba70-197">Você também pode reiniciar o console do SRS (interface de usuário do SRS) ou reiniciar todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="cba70-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="cba70-198">Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="cba70-199">Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs.</span><span class="sxs-lookup"><span data-stu-id="cba70-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="cba70-200">A atualização da página fornecerá o status mais recente.</span><span class="sxs-lookup"><span data-stu-id="cba70-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="cba70-201">Integridade</span><span class="sxs-lookup"><span data-stu-id="cba70-201">Health</span></span>

<span data-ttu-id="cba70-202">A seção de integridade fornece uma indicação visual da integridade da conexão do Skype for Business Server, dispositivo de áudio, dispositivo de vídeo, estado de resiliência e dispositivo de tela.</span><span class="sxs-lookup"><span data-stu-id="cba70-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Integridade da sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="cba70-204">Observações adicionais sobre o portal da Web administrativo</span><span class="sxs-lookup"><span data-stu-id="cba70-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="cba70-205">As alterações de configuração são aplicadas somente depois que o sistema SRS é reiniciado. > se a senha da conta LRSApp expirar, não será possível ver o status das salas.</span><span class="sxs-lookup"><span data-stu-id="cba70-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="cba70-206">Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando ela estiver prestes a expirar. > o portal da Web administrativo do SRS tem suporte apenas para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="cba70-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="cba70-207">Gerenciamento em massa</span><span class="sxs-lookup"><span data-stu-id="cba70-207">Bulk management</span></span>

<span data-ttu-id="cba70-208">O gerenciamento em massa de salas do SRS é um recurso projetado para administradores de ti avançados, para simplificar o fluxo de trabalho e habilitá-lo com uma ferramenta conveniente que economiza tempo para gerenciar remotamente várias salas de maneira em massa.</span><span class="sxs-lookup"><span data-stu-id="cba70-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="cba70-209">Para ver essa funcionalidade, o usuário precisa ser provisionado como um membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="cba70-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="cba70-210">Não há limite para o número de salas SRS que você pode selecionar para gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="cba70-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="cba70-211">No entanto, você só pode executar uma operação de gerenciamento em massa por vez.</span><span class="sxs-lookup"><span data-stu-id="cba70-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="cba70-212">Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e clique no menu de gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="cba70-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="cba70-213">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="cba70-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="cba70-214">Por que não consigo entrar no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="cba70-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="cba70-215">Ao abrir https://localhost/lrs o, você poderá ver a página de entrada, mas quando digitar suas credenciais, não poderá entrar.</span><span class="sxs-lookup"><span data-stu-id="cba70-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="cba70-216">Nesse caso, você deve abrir https://FQDNofFEserver/SRS o para entrar no portal da Web administrativo.</span><span class="sxs-lookup"><span data-stu-id="cba70-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="cba70-217">Por que não consigo ver o SRS v1 no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="cba70-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="cba70-218">Verifique se você tem contas do SRS em sua implantação e se elas foram criadas de acordo com as recomendações de implantação do portal da Web administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="cba70-219">Verifique se as contas do SRS estão provisionadas usando o Enable-CsMeetingRoom, não o Enable-CsUser, no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cba70-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="cba70-220">Se você tiver criado contas do SRS e não puder ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta de log do Skype for Business Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="cba70-221">Se você tiver criado contas do SRS e não puder ver as contas no portal da Web administrativo, colete os logs do cliente usando Fiddler e também copie o log do console das ferramentas de desenvolvimento do navegador e, em seguida, envie-os para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="cba70-222">Você também pode modificar o valor de nível de rastreamento no Web. config para obter um log mais detalhado.</span><span class="sxs-lookup"><span data-stu-id="cba70-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="cba70-223">Por que não consigo ver o status do SRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="cba70-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="cba70-224">Verifique se a conta de usuário LRSApp está habilitada para SIP.</span><span class="sxs-lookup"><span data-stu-id="cba70-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="cba70-225">Se você ainda estiver com problemas, colete o arquivo **trace. log** no sistema SRS de D:\Tracing\LRSAdminLogs \, e envie-o para seu contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="cba70-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="cba70-226">Por que não consigo ver os menus de gerenciamento em massa do SRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="cba70-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="cba70-227">Verifique se a conta de usuário do LRSApp está habilitada para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="cba70-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="cba70-228">O portal da Web administrativo do SRS v1 funciona com salas do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="cba70-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="cba70-229">Não.</span><span class="sxs-lookup"><span data-stu-id="cba70-229">No.</span></span>


