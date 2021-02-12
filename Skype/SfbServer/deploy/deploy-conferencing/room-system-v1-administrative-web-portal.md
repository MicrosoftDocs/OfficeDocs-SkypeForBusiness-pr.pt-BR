---
title: Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: O Portal da Web Administrativo do Skype for Business Server Skype Room Systems v1 (SRS v1, anteriormente conhecido como Sistema de Salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o Portal da Web Administrativo do SRS v1 para monitorar a saúde do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a saúde da sala de conferência.
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804531"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="d5b5c-105">Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d5b5c-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="d5b5c-106">O Portal da Web Administrativo do Skype for Business Server Skype Room Systems v1 (SRS v1, anteriormente conhecido como Sistema de Salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="d5b5c-107">Os administradores podem usar o Portal da Web Administrativo do SRS v1 para monitorar a saúde do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="d5b5c-108">Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a saúde da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="d5b5c-109">Para usar esse recurso, o Portal da Web Administrativo do SRS v1 precisa ser implantado em cada Servidor Front-End do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="d5b5c-110">Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="d5b5c-111">Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e que têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="d5b5c-112">Depois que o Portal da Web Administrativo do SRS v1 é implantado no servidor, os administradores podem verificar o status dos dispositivos SRS v1 fazendo logo login no site em seus próprios computadores ou laptops.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5b5c-113">Baixe o Portal da Web Administrativo [do Microsoft Skype Room Systems v1 para Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="d5b5c-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="d5b5c-114">Neste tópico:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-114">In this topic:</span></span>

- [<span data-ttu-id="d5b5c-115">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="d5b5c-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="d5b5c-116">Instalar o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="d5b5c-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="d5b5c-117">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="d5b5c-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="d5b5c-118">Configurar seu ambiente para o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="d5b5c-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="d5b5c-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="d5b5c-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="d5b5c-120">Para usar o Portal da Web Administrativo do SRS v1, você precisará instalar ou configurar os seguintes pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5b5c-121">Se o servidor estiver configurado com autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status do SRS no portal administrativo.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="d5b5c-122">Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou insinue o computador SRS no domínio.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="d5b5c-123">Instale as Atualizações Cumulativas do Skype for Business Server na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="d5b5c-124">Para obter a atualização ou ver o que está incluído nele, consulte Atualizações para [o Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d5b5c-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="d5b5c-125">Crie um usuário do Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="d5b5c-126">O Portal da Web Administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="d5b5c-127">O nome de usuário nos exemplos determinados é LRSApp.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="d5b5c-128">Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="d5b5c-129">Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Segurança.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="d5b5c-130">Os usuários habilitados para SIP que são adicionados a esse grupo serão autorizados a ver a lista de salas e executar determinados comandos, como coletar logs.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="d5b5c-131">Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="d5b5c-132">Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Security.SIP. Os usuários habilitados para SIP adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="d5b5c-133">Para incluir suporte para gerenciamento em massa de salas do Skype, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![Lista de grupos de administração com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="d5b5c-135">Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="d5b5c-136">Crie o grupo com Escopo de Grupo como Global e Tipo de Grupo como Segurança.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="d5b5c-137">Os usuários habilitados para SIP adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="d5b5c-138">Adicione LRSFullAccessAdminGroup como membro do LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![Página Membros das Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="d5b5c-140">Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="d5b5c-141">Adicione esse usuário a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![Página Membros das Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="d5b5c-143">Instale [ASP.NET MVC 4 para Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1.](https://go.microsoft.com/fwlink/p/?LinkId=323967)</span><span class="sxs-lookup"><span data-stu-id="d5b5c-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="d5b5c-144">Instalar o Portal da Web Administrativo do SRS v1</span><span class="sxs-lookup"><span data-stu-id="d5b5c-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="d5b5c-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="d5b5c-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="d5b5c-146">Baixe o Portal da Web Administrativo [do Microsoft Skype Room Systems v1 para Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=46906)</span><span class="sxs-lookup"><span data-stu-id="d5b5c-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="d5b5c-147">Para instalar o Portal da Web Administrativo do SRS v1, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="d5b5c-148">Configure a Porta de Aplicativo Confiável executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="d5b5c-149">Para instalar o Portal de Sala de Reunião, baixe **MeetingRoomPortalInstaller.msi** e execute-o como administrador.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="d5b5c-150">Abra o Web.config arquivo no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="d5b5c-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="d5b5c-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="d5b5c-152">No arquivo Web.Config, altere PortalUserName para o nome de usuário criado na Etapa 2, na seção " Configurar seu ambiente para o Portal da Web Administrativo do[SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):</span><span class="sxs-lookup"><span data-stu-id="d5b5c-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="d5b5c-153">Como o Portal de Administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do portal.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="d5b5c-154">Se esse usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo de Web.Config:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="d5b5c-155">Se a porta usada for diferente de 5061, adicione a seguinte linha no Web.Config arquivo:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="d5b5c-156">Verificar a instalação do Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="d5b5c-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="d5b5c-157">Para verificar a instalação do Portal da Web Administrativo do SRS v1, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="d5b5c-158">Em um servidor front-end, navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="d5b5c-159">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d5b5c-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="d5b5c-160">Você não deve ver erros, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync Room System Admin Portal Sign In screen](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="d5b5c-162">Se você não vir erros, tente acessar a SEGUINTE URL de qualquer outro computador na topologia:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="d5b5c-163">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d5b5c-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="d5b5c-164">Para acessar a página, você precisará adicionar os registros DNS conforme descrito em " Registros DNS necessários para entrada automática do[cliente".](https://go.microsoft.com/fwlink/p/?LinkId=318056)</span><span class="sxs-lookup"><span data-stu-id="d5b5c-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="d5b5c-165">Usar o Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="d5b5c-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="d5b5c-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="d5b5c-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="d5b5c-167">Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas do SRS entrando no Portal da Web Administrativo do SRS v1 a partir de um navegador.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="d5b5c-168">Entrar</span><span class="sxs-lookup"><span data-stu-id="d5b5c-168">Sign in</span></span>

1. <span data-ttu-id="d5b5c-169">Navegue até a seguinte URL:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-169">Browse to the following URL:</span></span>

    <span data-ttu-id="d5b5c-170">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="d5b5c-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="d5b5c-171">Insira as credenciais da conta LRSSupport ou de uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync Room System Admin Portal Sign In screen](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="d5b5c-173">Página de Resumo do Portal da Web Administrativo do SRS</span><span class="sxs-lookup"><span data-stu-id="d5b5c-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="d5b5c-174">A página de resumo fornece as seguintes informações para todas as salas do SRS implantadas no servidor:</span><span class="sxs-lookup"><span data-stu-id="d5b5c-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="d5b5c-175">**Tag** O nome personalizado que o administrador fornece à sala.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="d5b5c-176">A marca pode ser definida no portal clicando no nome da sala.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="d5b5c-177">**Health** O status de saúde da sala, que é derivado do status de Saúde Agregada da sala, que é mostrado na seção De saúde da página Configurações da Sala.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="d5b5c-178">**Próxima Reunião** A data e a hora em que a próxima reunião está agendada.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="d5b5c-179">**Versão do SRS, Fabricante, Modelo** Esses valores são predefinidos no SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="d5b5c-180">Dependendo do fabricante, esses campos podem ser deixados em branco.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="d5b5c-181">**Última atualização** Exibe a última vez que a página da Web foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System Admin Portal Summary View](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="d5b5c-183">Você só verá o menu Gerenciamento em Massa se for parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="d5b5c-184">Informações da Sala SRS</span><span class="sxs-lookup"><span data-stu-id="d5b5c-184">SRS Room Information</span></span>

<span data-ttu-id="d5b5c-185">A seção Informações da Sala do portal permite que você veja e configure salas SRS individuais.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="d5b5c-186">Ele contém quatro seções: Configurações, Detalhes, Log e Saúde.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="d5b5c-187">Configurações</span><span class="sxs-lookup"><span data-stu-id="d5b5c-187">Settings</span></span>

<span data-ttu-id="d5b5c-188">Na seção Configurações, você pode definir a senha, a marca da sala e os níveis de volume padrão da sala.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="d5b5c-189">Se você definir essas configurações, as alterações serão replicadas somente depois que você reiniciar o console do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="d5b5c-190">Você só verá as configurações de Atualizações do Sistema para dispositivos SRS usando a versão 15.12 e posterior.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Configurações da sala do Portal de Administração do Sistema de Sala do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="d5b5c-192">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d5b5c-192">Details</span></span>

<span data-ttu-id="d5b5c-193">A seção Detalhes fornece um resumo somente leitura das configurações da sala SRS, incluindo: a hora da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações padrão de alto-falante, microfone e toque; versão; URI do SIP; número de telas e detalhes sobre cada tela; status e atividade.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System Admin Portal Detail View](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="d5b5c-195">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="d5b5c-195">Troubleshooting</span></span>

<span data-ttu-id="d5b5c-196">A seção Solução de Problemas pode ser usada remotamente para coletar logs e salvá-los em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="d5b5c-197">Você também pode reiniciar o console do SRS (interface do usuário do SRS) ou reiniciar todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="d5b5c-198">Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação concedidas à conta da máquina do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="d5b5c-199">Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="d5b5c-200">Atualizar a página lhe dará o status mais recente.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="d5b5c-201">Integridade</span><span class="sxs-lookup"><span data-stu-id="d5b5c-201">Health</span></span>

<span data-ttu-id="d5b5c-202">A seção Health fornece uma indicação visual da saúde da conexão do Skype for Business Server, do dispositivo de áudio, do dispositivo de vídeo, do estado de resiliência e do dispositivo de tela.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System Admin Portal Room Health](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="d5b5c-204">Observações adicionais sobre o Portal da Web Administrativo</span><span class="sxs-lookup"><span data-stu-id="d5b5c-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="d5b5c-205">As alterações de configuração são aplicadas somente depois que o sistema SRS é reiniciado.> Se a senha da conta LRSApp expirar, você não poderá ver o status das salas.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="d5b5c-206">Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando estiver próximo de expirar.> O portal da Web administrativo do SRS é suportado apenas para implantações locais.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="d5b5c-207">Gerenciamento em massa</span><span class="sxs-lookup"><span data-stu-id="d5b5c-207">Bulk management</span></span>

<span data-ttu-id="d5b5c-208">O gerenciamento em massa de salas SRS é um recurso projetado para administradores avançados de IT, para simplificar seu fluxo de trabalho e habilita-los com uma ferramenta conveniente de economia de tempo para gerenciar remotamente várias salas em massa.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="d5b5c-209">Para ver essa funcionalidade, o usuário precisa ser provisionado como membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="d5b5c-210">Não há limite para o número de salas do SRS que você pode selecionar para gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="d5b5c-211">No entanto, você pode executar apenas uma operação de gerenciamento em massa por vez.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="d5b5c-212">Para executar uma operação de gerenciamento em massa, selecione as salas que deseja monitorar e clique no menu Gerenciamento em massa.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="d5b5c-213">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="d5b5c-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="d5b5c-214">Por que não consigo entrar no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="d5b5c-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="d5b5c-215">Ao abrir, você poderá ver a página de login, mas quando digitar suas credenciais, não https://localhost/lrs poderá entrar.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="d5b5c-216">Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal da Web administrativo.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="d5b5c-217">Por que não consigo ver o SRS v1 no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="d5b5c-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="d5b5c-218">Certifique-se de que você tenha contas do SRS em sua implantação e que elas sejam criadas de acordo com as recomendações de implantação do Portal da Web Administrativo do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="d5b5c-219">Certifique-se de que as contas do SRS sejam provisionadas usando Enable-CsMeetingRoom, não Enable-CsUser, no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="d5b5c-220">Se você criou contas do SRS e não pode ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta Log do Skype for Business Server com o componente **MeetingPortal** selecionado e envie-os para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="d5b5c-221">Se você criou contas do SRS e não pode ver as contas no portal da Web administrativo, colete os logs do cliente usando o Fiddler e copie o log do console das ferramentas de desenvolvimento do navegador e envie-as para o contato de suporte do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="d5b5c-222">Você também pode modificar o valor do nível de rastreamento no Web.config obter um log mais detalhado.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="d5b5c-223">Por que não consigo ver o status do SRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="d5b5c-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="d5b5c-224">Certifique-se de que a conta de usuário LRSApp seja habilitada para SIP.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="d5b5c-225">Se você ainda estiver com problemas, colete o arquivo **Trace.log** no sistema SRS de D:\Tracing\LRSAdminLogs e envie-o para o contato de suporte \, do SRS.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="d5b5c-226">Por que não consigo ver os menus de gerenciamento em massa do SRS no portal da Web administrativo?</span><span class="sxs-lookup"><span data-stu-id="d5b5c-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="d5b5c-227">Certifique-se de que a conta de usuário LRSApp seja habilitada para SIP e faça parte do grupo de segurança LRSPowerUserAdminsGroup.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="d5b5c-228">O portal da Web administrativo do SRS v1 funciona com as Salas do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="d5b5c-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="d5b5c-229">Não.</span><span class="sxs-lookup"><span data-stu-id="d5b5c-229">No.</span></span>


