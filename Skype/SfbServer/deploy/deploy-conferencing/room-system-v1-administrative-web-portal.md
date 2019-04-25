---
title: Implantar o Portal de Web administrativo do SRS v1 no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: O Skype para sistemas de sala Business Server Skype v1 (SRS v1, anteriormente conhecido como o sistema de sala do Lync) administrativas Portal da Web é um portal da web que as organizações podem usar para manter suas salas de conferência de sistemas de sala Skype. Os administradores podem usar o Portal da Web SRS v1 administrativas para monitorar a integridade do dispositivo, por exemplo por meio do monitoramento de dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: b616084016a3b660f4af5bcd3bda6926dfc7e286
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226184"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="e290b-105">Implantar o Portal de Web administrativo do SRS v1 no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e290b-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="e290b-106">O Skype para sistemas de sala Business Server Skype v1 (SRS v1, anteriormente conhecido como o sistema de sala do Lync) administrativas Portal da Web é um portal da web que as organizações podem usar para manter suas salas de conferência de sistemas de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="e290b-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="e290b-107">Os administradores podem usar o Portal da Web SRS v1 administrativas para monitorar a integridade do dispositivo, por exemplo por meio do monitoramento de dispositivos de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e290b-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="e290b-108">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="e290b-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="e290b-109">Para usar esse recurso, o Portal da Web administrativo SRS v1 precisa ser implantado em cada Skype para Business Server servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="e290b-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="e290b-110">Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="e290b-111">Ele foi projetado para administradores que tem conhecimento do Skype para administração de servidor de negócios, e que tenha direitos de usuário de administrador para modificar o Skype para a topologia de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e290b-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="e290b-112">Após o v1 SRS que administrativas Portal da Web é implantado no servidor, os administradores podem verificar os dispositivos do status SRS v1 por logon ao site de seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="e290b-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e290b-113">Baixe o [Microsoft Skype sala v1 de sistemas e Portal da Web administrativo para Skype para Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="e290b-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="e290b-114">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="e290b-114">In this topic:</span></span>

- [<span data-ttu-id="e290b-115">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="e290b-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="e290b-116">Instalar o Portal do SRS v1 Web administrativo</span><span class="sxs-lookup"><span data-stu-id="e290b-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="e290b-117">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="e290b-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="e290b-118">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="e290b-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="e290b-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="e290b-119"></span></span>

<span data-ttu-id="e290b-120">Para usar o Portal da Web Administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e290b-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e290b-p104">Se o servidor estiver configurado com a autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não tenha ingressado no domínio, haverá falha na autenticação Kerberos e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou com autenticação NTLM e TLS-DSK (sem Kerberos), ou ingresse o computador com SRS no domínio.</span><span class="sxs-lookup"><span data-stu-id="e290b-p104">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal. To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="e290b-123">Instale o Skype para atualizações cumulativas do Business Server no Skype para a topologia de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e290b-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="e290b-124">Para obter a atualização ou consulte o que está incluído com ele, consulte [atualizações para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="e290b-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="e290b-125">Crie um usuário do Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="e290b-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="e290b-126">O Portal da Web administrativo SRS v1 usa essas credenciais para consultar informações do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e290b-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="e290b-127">O nome de usuário nos exemplos fornecidos é LRSApp.</span><span class="sxs-lookup"><span data-stu-id="e290b-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="e290b-128">Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="e290b-p106">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a este grupo serão autorizados a ver a lista de salas e a executar determinados comandos, como coletar logs.</span><span class="sxs-lookup"><span data-stu-id="e290b-p106">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="e290b-131">Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="e290b-p107">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para o gerenciamento em massa de salas do Skype, consulte a etapa 5. </span><span class="sxs-lookup"><span data-stu-id="e290b-p107">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room. To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Lista de grupos de administração com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="e290b-135">Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="e290b-136">Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança.</span><span class="sxs-lookup"><span data-stu-id="e290b-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="e290b-137">Os usuários habilitados para SIP adicionados a este grupo estão autorizados a usar todas as funcionalidades de portal de administração incluindo gerenciamento de massa do Skype para salas de negócios.</span><span class="sxs-lookup"><span data-stu-id="e290b-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="e290b-138">Adicione LRSFullAccessAdminGroup como membro do LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Página LRSSupportAdminGroup propriedades membros](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="e290b-140">Crie um usuário habilitados para SIP Active Directory com o nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="e290b-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="e290b-141">Adicione este usuário à LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Página LRSSupportAdminGroup propriedades membros](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="e290b-143">Instale o [ASP.NET MVC 4 para o Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span><span class="sxs-lookup"><span data-stu-id="e290b-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="e290b-144">Instalar o Portal do SRS v1 Web administrativo</span><span class="sxs-lookup"><span data-stu-id="e290b-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="e290b-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="e290b-145"></span></span>

<span data-ttu-id="e290b-146">Baixe o [Microsoft Skype sala v1 de sistemas e Portal da Web administrativo para Skype para Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span><span class="sxs-lookup"><span data-stu-id="e290b-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="e290b-147">Para instalar o Portal da Web SRS v1 administrativa, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e290b-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="e290b-148">Configure a porta de aplicativos confiáveis executando o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="e290b-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="e290b-149">Para instalar o Portal de sala de reunião, baixe **MeetingRoomPortalInstaller.msi** e, em seguida, executá-lo como um administrador.</span><span class="sxs-lookup"><span data-stu-id="e290b-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="e290b-150">Abra o arquivo Web. config do seguinte local:</span><span class="sxs-lookup"><span data-stu-id="e290b-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="e290b-151">% Programa Files%\Skype para Business Server 2015\Web Components\Meeting sala Portal\Int\Handler\\</span><span class="sxs-lookup"><span data-stu-id="e290b-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\\</span></span>

4. <span data-ttu-id="e290b-152">No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2, sob a seção "[configurar seu ambiente para o Portal da Web administrativo SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="e290b-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="e290b-153">Como o Portal de administração do SRS v1 é um aplicativo confiável, você não precisará fornecer a senha na configuração do portal.</span><span class="sxs-lookup"><span data-stu-id="e290b-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="e290b-154">Se esse usuário estiver usando um registrador diferente que registrador local, você precisa especificar o registrador para ele, adicionando a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="e290b-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="e290b-155">Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:</span><span class="sxs-lookup"><span data-stu-id="e290b-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="e290b-156">Verificar a instalação do Portal da Web administrativo SRS</span><span class="sxs-lookup"><span data-stu-id="e290b-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="e290b-157">Para verificar a instalação do Portal da Web administrativo do SRS v1, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e290b-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="e290b-158">Em um servidor Front-End, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="e290b-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="e290b-159">https://\<servidor fe\>/lrs</span><span class="sxs-lookup"><span data-stu-id="e290b-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="e290b-160">Você não verá quaisquer erros, conforme mostrado na seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="e290b-160">You should not see any errors, as shown in the following image:</span></span>

     ![Tela Lync sala sistema Admin Portal entrar](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="e290b-162">Se você não vir quaisquer erros, tente acessar a seguinte URL de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="e290b-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="e290b-163">https://\<servidor fe\>/lrs</span><span class="sxs-lookup"><span data-stu-id="e290b-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="e290b-164">Para acessar a página, você precisará adicionar os registros DNS conforme descrito em "[necessário registros DNS para o cliente na entrada automática](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span><span class="sxs-lookup"><span data-stu-id="e290b-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="e290b-165">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="e290b-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="e290b-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="e290b-166"></span></span>

<span data-ttu-id="e290b-167">Depois de implantar SRS no servidor, você pode verificar o status de todas as salas SRS por fazer o login no SRS v1 administrativas Portal da Web de um navegador.</span><span class="sxs-lookup"><span data-stu-id="e290b-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="e290b-168">Entrar</span><span class="sxs-lookup"><span data-stu-id="e290b-168">Sign in</span></span>

1. <span data-ttu-id="e290b-169">Navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="e290b-169">Browse to the following URL:</span></span>

    <span data-ttu-id="e290b-170">https://\<servidor fe\>/lrs</span><span class="sxs-lookup"><span data-stu-id="e290b-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="e290b-171">Insira as credenciais para a conta de LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Tela Lync sala sistema Admin Portal entrar](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="e290b-173">Página de resumo Portal SRS Web administrativo</span><span class="sxs-lookup"><span data-stu-id="e290b-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="e290b-174">A página de resumo fornece as seguintes informações para todas as salas SRS implantadas no servidor:</span><span class="sxs-lookup"><span data-stu-id="e290b-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="e290b-175">**Marca** O nome personalizado que o administrador concede à sala.</span><span class="sxs-lookup"><span data-stu-id="e290b-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="e290b-176">A marca pode ser definida no portal clicando no nome da sala.</span><span class="sxs-lookup"><span data-stu-id="e290b-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="e290b-177">**Integridade** O status de integridade da sala, que é derivado do status de integridade agregado da sala, que é mostrado na seção de integridade da página Configurações de sala.</span><span class="sxs-lookup"><span data-stu-id="e290b-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="e290b-178">**Próxima reunião** A data e hora que a próxima reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="e290b-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="e290b-179">**Modelo de versão, fabricante, SRS** Esses valores são predefinidos no SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="e290b-180">Com o fabricante, esses campos podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="e290b-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="e290b-181">**Última atualização** Exibe a última vez em que a página da web foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="e290b-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Exibição de resumo do Portal de administração de sistema de sala do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="e290b-183">Você verá o menu de gerenciamento em massa apenas se você fizer parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="e290b-184">Informações de sala SRS</span><span class="sxs-lookup"><span data-stu-id="e290b-184">SRS Room Information</span></span>

<span data-ttu-id="e290b-185">A seção de informações de sala do portal permite que você exibir e configurar salas SRS individuais.</span><span class="sxs-lookup"><span data-stu-id="e290b-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="e290b-186">Ele contém quatro seções: definições, detalhes, registro em log e integridade.</span><span class="sxs-lookup"><span data-stu-id="e290b-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="e290b-187">Configurações</span><span class="sxs-lookup"><span data-stu-id="e290b-187">Settings</span></span>

<span data-ttu-id="e290b-188">Na seção configurações, você pode definir a senha, a etiqueta de sala e níveis de volume padrão para a sala.</span><span class="sxs-lookup"><span data-stu-id="e290b-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="e290b-189">Se você definir essas configurações, as alterações são replicadas somente depois que você reiniciar o console SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="e290b-190">Você só verá as configurações de atualizações do sistema para dispositivos SRS usando versão 15.12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="e290b-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Configurações de sala do Portal de administração de sistema de sala do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="e290b-192">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e290b-192">Details</span></span>

<span data-ttu-id="e290b-193">Seção detalhes do fornece um resumo de somente leitura das configurações da sala SRS, incluindo: a hora da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações de campainha; microfone e alto-falante do padrão versão; URI DO SIP; número de telas e detalhes sobre cada tela; status e a atividade.</span><span class="sxs-lookup"><span data-stu-id="e290b-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Exibição de detalhes do Portal de administração de sistema de sala do Lync](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="e290b-195">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="e290b-195">Troubleshooting</span></span>

<span data-ttu-id="e290b-196">A seção de solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="e290b-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="e290b-197">Você pode também reinicie o console SRS (interface de usuário SRS) ou todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="e290b-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="e290b-198">Para coletar logs, forneça um caminho de pasta no formato especificado e verifique se a pasta possui permissões de gravação dada à conta do computador SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="e290b-199">Se o tamanho do log é muito grande, pode demorar até 5 minutos para concluir a coleta dos logs.</span><span class="sxs-lookup"><span data-stu-id="e290b-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="e290b-200">Atualizar a página fornecerá a você o status mais recente.</span><span class="sxs-lookup"><span data-stu-id="e290b-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="e290b-201">Integridade</span><span class="sxs-lookup"><span data-stu-id="e290b-201">Health</span></span>

<span data-ttu-id="e290b-202">A seção de integridade, fornece uma indicação visual da integridade do Skype para conexão Business Server, dispositivo de áudio, dispositivo de vídeo, o estado de resiliência e dispositivo de tela.</span><span class="sxs-lookup"><span data-stu-id="e290b-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Integridade de sala do Portal de administração de sistema de sala do Lync](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="e290b-204">Observações adicionais sobre o Portal da Web administrativo</span><span class="sxs-lookup"><span data-stu-id="e290b-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="e290b-205">Alterações de configuração são aplicadas somente depois que o sistema SRS é .> reiniciados se a senha da conta LRSApp expirar, não será possível ver o status das salas.</span><span class="sxs-lookup"><span data-stu-id="e290b-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="e290b-206">Configure a senha da conta LRSAppuser para que ele nunca expira ou não se esqueça de atualizar a senha, quando ele está perto expiration.> o SRS administrativas portal da web é suportado para implantações de locais somente.</span><span class="sxs-lookup"><span data-stu-id="e290b-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="e290b-207">Gerenciamento em massa</span><span class="sxs-lookup"><span data-stu-id="e290b-207">Bulk management</span></span>

<span data-ttu-id="e290b-208">Gerenciamento em massa de salas SRS é um recurso projetado para administradores de TI avançado, para simplificar o seu fluxo de trabalho e habilitá-los com uma ferramenta conveniente de economia de tempo para gerenciar remotamente várias salas de maneira em massa.</span><span class="sxs-lookup"><span data-stu-id="e290b-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="e290b-209">Para ver essa funcionalidade, o usuário precisa ser provisionado como um membro do grupo de segurança especiais, **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="e290b-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="e290b-210">Não há nenhum limite no número de salas SRS que podem ser selecionados para o gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e290b-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="e290b-211">No entanto, você pode executar a operação de gerenciamento em massa de apenas um por vez.</span><span class="sxs-lookup"><span data-stu-id="e290b-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="e290b-212">Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e, em seguida, clique no menu de gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e290b-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="e290b-213">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e290b-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="e290b-214">Por que não posso entrar no portal da web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e290b-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="e290b-215">Quando você abre https://localhost/lrs, será possível ver a página de entrada, mas quando você digitar suas credenciais, você não conseguir entrar.</span><span class="sxs-lookup"><span data-stu-id="e290b-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="e290b-216">Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal da web administrativo.</span><span class="sxs-lookup"><span data-stu-id="e290b-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="e290b-217">Por que não posso ver v1 SRS no portal do web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e290b-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="e290b-218">Verifique se que você tem as contas SRS em sua implantação e o que eles são criados de acordo com as recomendações de implantação do Portal da Web administrativo SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="e290b-219">Verifique se que as contas SRS são provisionadas usando o Enable-CsMeetingRoom não Enable-CsUser, o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e290b-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="e290b-220">Se você tiver criado contas SRS e não pode ver as contas no portal da web administrativo, coletar logs do servidor usando o Skype para ferramenta de log do servidor de negócios com o componente de **MeetingPortal** selecionado e depois enviá-las ao seu contato do suporte SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="e290b-221">Se você tiver criado contas SRS e não pode ver as contas no portal da web administrativo, coletar os logs do cliente usando o Fiddler e também copiar o log do console de ferramentas de desenvolvimento do navegador e depois enviá-las ao seu contato do suporte SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="e290b-222">Você também pode modificar o valor de nível de rastreamento na Web. config para obter um log mais detalhado.</span><span class="sxs-lookup"><span data-stu-id="e290b-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="e290b-223">Por que não posso ver o status da SRS no portal do web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e290b-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="e290b-224">Certifique-se de que a conta de usuário LRSApp está habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="e290b-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="e290b-225">Se você ainda estiver tendo problemas, coletar o arquivo **Trace** no sistema SRS de D:\Tracing\LRSAdminLogs\, e depois enviá-la ao seu contato do suporte SRS.</span><span class="sxs-lookup"><span data-stu-id="e290b-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="e290b-226">Por que eu não podem ver os menus de gerenciamento em massa para SRS no portal do web administrativo?</span><span class="sxs-lookup"><span data-stu-id="e290b-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="e290b-227">Certifique-se de que a conta de usuário LRSApp é habilitado para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="e290b-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="e290b-228">O portal de web administrativo SRS v1 funciona com salas de equipes da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="e290b-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="e290b-229">Não.</span><span class="sxs-lookup"><span data-stu-id="e290b-229">No.</span></span>


