---
title: Preparar seu Ambiente
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Saiba como preparar sua infraestrutura para a implantação de Salas do Microsoft Teams para que você possa tirar proveito de todos os recursos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 81aa41895f11b65c9406bd30311f2fcb974949a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117419"
---
# <a name="prepare-your-environment"></a><span data-ttu-id="c1a4d-103">Preparar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="c1a4d-103">Prepare your environment</span></span>

<span data-ttu-id="c1a4d-104">Esta seção contém uma visão geral das etapas necessárias para preparar seu ambiente para que você possa usar todos os recursos das Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-104">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Microsoft Teams Rooms.</span></span>
  
1. <span data-ttu-id="c1a4d-105">Preparar uma conta de dispositivo para cada console do Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-105">Prepare a device account for each Microsoft Teams Rooms console.</span></span> <span data-ttu-id="c1a4d-106">Confira [Implantar salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-106">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
    
2. <span data-ttu-id="c1a4d-107">Verifique se existe uma conexão de rede/Internet para o dispositivo usar. </span><span class="sxs-lookup"><span data-stu-id="c1a4d-107">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
   <span data-ttu-id="c1a4d-108">Ele deve ser capaz de receber um endereço IP usando DHCP.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-108">It must be able to receive an IP address by using DHCP.</span></span> <span data-ttu-id="c1a4d-109">(As Salas do Microsoft Teams não podem ser configuradas com um endereço IP estático na primeira inicialização da unidade, mas, posteriormente, um endereço IP estático para o dispositivo pode ser configurado no dispositivo ou no comutamento upstream ou roteador).)</span><span class="sxs-lookup"><span data-stu-id="c1a4d-109">(Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup, but afterwards, a static IP address for the device could be configured on the device or on the upstream switch or router.)</span></span>

   <span data-ttu-id="c1a4d-110">Ele deve ter essas portas abertas (além de abrir as portas normais para mídia):</span><span class="sxs-lookup"><span data-stu-id="c1a4d-110">It must have these ports open (in addition to opening the normal ports for media):</span></span>
   - <span data-ttu-id="c1a4d-111">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="c1a4d-111">HTTPS: 443</span></span>
   - <span data-ttu-id="c1a4d-112">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="c1a4d-112">HTTP: 80</span></span>

   <span data-ttu-id="c1a4d-113">Se sua rede é executada através de um proxy, você também precisa do endereço de proxy ou de informações do script.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-113">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
   > [!IMPORTANT]
   > <span data-ttu-id="c1a4d-114">As Salas do Microsoft Teams não suportam a autenticação de proxy, pois podem interferir nas operações regulares da sala.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-114">Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of the room.</span></span> <span data-ttu-id="c1a4d-115">Verifique se as Salas do Microsoft Teams foram isentas da autenticação de proxy antes de entrar em produção.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-115">Ensure that Microsoft Teams Rooms have been exempted from proxy authentication before going into production.</span></span>
  
3. <span data-ttu-id="c1a4d-116">Para aprimorar sua experiência, a Microsoft coleta dados.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-116">In order to improve your experience, Microsoft collects data.</span></span> <span data-ttu-id="c1a4d-117">Para permitir que a Microsoft colete dados, permita estes sites:</span><span class="sxs-lookup"><span data-stu-id="c1a4d-117">To allow Microsoft to collect data, allow these sites:</span></span>

   - <span data-ttu-id="c1a4d-118">Ponto de extremidade do cliente de telemetria: https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="c1a4d-118">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
   - <span data-ttu-id="c1a4d-119">Ponto de extremidade das configurações de telemetria: https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="c1a4d-119">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="c1a4d-120">Criar e testar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c1a4d-120">Create and test a device account</span></span>

<span data-ttu-id="c1a4d-121">Uma  *conta de dispositivo*  é uma conta que o cliente salas do Microsoft Teams usa para acessar recursos do Exchange, como calendário, e para habilitar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-121">A  *device account*  is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="c1a4d-122">Confira [Implantar salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-122">See [Deploy Microsoft Teams Rooms](rooms-deploy.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="c1a4d-123">Verificar a disponibilidade da rede</span><span class="sxs-lookup"><span data-stu-id="c1a4d-123">Check network availability</span></span>

<span data-ttu-id="c1a4d-124">Para funcionar corretamente, o dispositivo salas do Microsoft Teams deve ter acesso a uma rede com fio que atenda a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="c1a4d-124">In order to function properly, the Microsoft Teams Rooms device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="c1a4d-125">Acessar a instância do Active Directory ou do Azure Active Directory (Azure AD), bem como o servidores Microsoft Exchange e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-125">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>

- <span data-ttu-id="c1a4d-126">Acesso a um servidor que pode fornecer um endereço IP usando DHCP.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-126">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="c1a4d-127">As Salas do Microsoft Teams não podem ser configuradas com um endereço IP estático na primeira inicialização da unidade.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-127">Microsoft Teams Rooms cannot be configured with a static IP address at the first unit startup.</span></span>

- <span data-ttu-id="c1a4d-128">Acessar as portas HTTP 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-128">Access to HTTP ports 80 and 443.</span></span>

- <span data-ttu-id="c1a4d-129">Portas TCP e UDP configuradas conforme descrito em Requisitos de porta e protocolo para servidores para implementações locais do Skype for Business Server, ou [URLs do Microsoft 365 e Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) e intervalos de endereços IP para o Microsoft Teams ou implementações online do Skype for Business. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)</span><span class="sxs-lookup"><span data-stu-id="c1a4d-129">TCP and UDP ports configured as described in [Port and protocol requirements for servers](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) for on-premise Skype for Business Server implementations, or [Microsoft 365 and Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Microsoft Teams or Skype for Business online implementations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1a4d-130">Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária. </span><span class="sxs-lookup"><span data-stu-id="c1a4d-130">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a4d-131">As atualizações de software para Salas do Microsoft Teams são baixadas automaticamente da Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-131">Software updates for Microsoft Teams Rooms are automatically downloaded from the Microsoft Store for Business.</span></span> <span data-ttu-id="c1a4d-132">Consulte [Pré-requisitos da Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business) e Educação para verificar se o console de sala poderá acessar a loja e a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-132">See [Prerequisites for Microsoft Store for Business and Education](/microsoft-store/prerequisites-microsoft-store-for-business) to verify that the room console will be able to access the store and self-update.</span></span>
  
### <a name="certificates"></a><span data-ttu-id="c1a4d-133">Certificados</span><span class="sxs-lookup"><span data-stu-id="c1a4d-133">Certificates</span></span>

<span data-ttu-id="c1a4d-134">O dispositivo salas do Microsoft Teams usa certificados para Serviços Web do Exchange, Microsoft Teams ou Skype for Business, uso da rede e autenticação.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-134">Your Microsoft Teams Rooms device uses certificates for Exchange Web Services, Microsoft Teams or Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="c1a4d-135">Se os servidores relacionados usarem certificados públicos, o que ocorre com as implantações online e com algumas implantações locais, o administrador não precisará realizar nenhuma ação adicional para instalar os certificados.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-135">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="c1a4d-136">Por outro lado, se a autoridade de certificação for uma AC privada (típica em implantações locais), o dispositivo deverá confiar na AC, o que significa ter a AC e a cadeia de certificados de AC instaladas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-136">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="c1a4d-137">Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-137">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="c1a4d-138">Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows. </span><span class="sxs-lookup"><span data-stu-id="c1a4d-138">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c1a4d-139">Os certificados podem ser necessários para que as Salas do Microsoft Teams usem o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-139">Certificates may be required in order to have Microsoft Teams Rooms use Skype for Business Server.</span></span>
  
### <a name="proxy"></a><span data-ttu-id="c1a4d-140">Proxy</span><span class="sxs-lookup"><span data-stu-id="c1a4d-140">Proxy</span></span>

<span data-ttu-id="c1a4d-141">As Salas do Microsoft Teams foram projetadas para herdar configurações de Proxy do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-141">Microsoft Teams Rooms is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="c1a4d-142">Acesse o sistema operacional Windows da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c1a4d-142">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="c1a4d-143">Na interface do usuário do Microsoft Teams Rooms, clique no ícone de engrenagem Configurações onde você será solicitado a solicitar a senha local do Administrador no dispositivo (a senha padrão é **sfb**).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-143">In the Microsoft Teams Rooms UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is **sfb**).</span></span>
2. <span data-ttu-id="c1a4d-144">Toque em **Configurações seguidas** tocando no botão Ir para **o Windows** e, em  seguida, tocando no botão ir para Admin **Sign In** e, em seguida, clicando no botão Administrador (se o computador estiver ingressado no domínio, escolha Outro Usuário, em **seguida,** use .\admin como o nome do usuário).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-144">Tap on **Settings** followed by tapping on the **Go to Windows** button and then tapping on the **go to Admin Sign In** button and then clicking the **Administrator** button (if the computer is domain joined choose **Other User,** then use .\admin as the user name).</span></span>
3. <span data-ttu-id="c1a4d-145">Na caixa **Pesquisar o tipo inferior** esquerdo do Windows no regedit (pressione a tela ou clique com o botão direito do mouse e escolha Executar como **administrador**).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-145">In the **Search Windows** box bottom left type in regedit (either long press the screen or right click and choose **Run as administrator**).</span></span>
4. <span data-ttu-id="c1a4d-146">Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-146">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
       
5. <span data-ttu-id="c1a4d-147">Clique em Arquivo e escolha **Carregar Hive.**</span><span class="sxs-lookup"><span data-stu-id="c1a4d-147">Click on File and then choose **Load Hive.**</span></span>
6. <span data-ttu-id="c1a4d-148">Navegue até **a pasta C:\Users\Skype** e digite na caixa Nome do arquivo NTUSER.dat e pressione o botão abrir</span><span class="sxs-lookup"><span data-stu-id="c1a4d-148">Browse to the **C:\Users\Skype** folder and type in the File name box NTUSER.dat and press the open button</span></span>

7. <span data-ttu-id="c1a4d-149">Você será solicitado a ter um nome de chave para seu Hive recém-carregado; digite no Skype (agora você deve ver as configurações do Registro para o Usuário do Skype).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-149">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
 
8. <span data-ttu-id="c1a4d-150">Abra a chave do Skype e navegue até HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings, em seguida, verifique se essas configurações são inseridas:</span><span class="sxs-lookup"><span data-stu-id="c1a4d-150">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    <span data-ttu-id="c1a4d-151">Se ProxyServer não existir, talvez seja necessário adicionar essa chave como uma cadeia de caracteres. Altere xx.xx.xx.xx:8080 para o ip/host e a porta de seu servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-151">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
 
    <span data-ttu-id="c1a4d-152">Se o cliente estiver usando um arquivo PAC, a configuração se pareceria com o exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="c1a4d-152">If the customer is using a PAC file the configuration would look like the example below:</span></span>

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. <span data-ttu-id="c1a4d-153">Ao concluir suas alterações, realce a chave do Usuário do Skype (pasta raiz do Skype) e opte por descarregar o Hive do menu de arquivos do Registro (será solicitada sua confirmação; selecione **Sim**).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-153">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes**).</span></span>
    
10. <span data-ttu-id="c1a4d-154">Agora, você pode fechar o editor do Registro e digitar logoff na caixa de pesquisa do Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-154">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
11. <span data-ttu-id="c1a4d-155">Voltando à tela de entrada, escolha o usuário **Skype**.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-155">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="c1a4d-156">Se todas as etapas anteriores foram bem-sucedidas, o dispositivo salas do Microsoft Teams entrará com êxito.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-156">If all the previous steps were successful, the Microsoft Teams Rooms device will sign-in successfully.</span></span>
    
<span data-ttu-id="c1a4d-157">Consulte o [artigo Segurança](./security.md#network-security) de Rede para obter detalhes completos sobre FQDNs, portas e intervalos de endereços IP necessários para salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-157">See the [Network Security](./security.md#network-security) article for full details on FQDNs, ports, and IP address ranges required for Microsoft Teams Rooms.</span></span>
  
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="c1a4d-158">Criar pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="c1a4d-158">Create provisioning packages</span></span>

<span data-ttu-id="c1a4d-159">Você usará pacotes de provisionamento para autenticar Exchange Server, Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-159">You will use provisioning packages to authenticate to Exchange Server, Microsoft 365, or Office 365.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="c1a4d-160">Gerenciamento de grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="c1a4d-160">Admin group management</span></span>

<span data-ttu-id="c1a4d-161">Após o ingresso no domínio, você pode usar a Política de Grupo ou o Gerenciamento de Computador Local para definir um Grupo de Segurança como administrador local, da mesma forma como faria com um computador Windows em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-161">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="c1a4d-162">Qualquer membro desse grupo de segurança pode inserir as respectivas credenciais e desbloquear as configurações.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-162">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1a4d-163">Se seu dispositivo de Salas do Microsoft Teams perder confiabilidade com o domínio (por exemplo, se você remover as Salas do Microsoft Teams do domínio após terem sido agregadas a ele), você não poderá autenticar esse dispositivo e abrir Configurações.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-163">If your Microsoft Teams Rooms device loses trust with the domain (for example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="c1a4d-164">A solução é fazer logon com a conta de Administrador local.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-164">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="c1a4d-165">Contas locais</span><span class="sxs-lookup"><span data-stu-id="c1a4d-165">Local accounts</span></span>

### <a name="microsoft-teams-rooms-local-user-account"></a><span data-ttu-id="c1a4d-166">Conta de usuário local das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-166">Microsoft Teams Rooms Local User Account</span></span>

<span data-ttu-id="c1a4d-167">A Conta de Dispositivo normalmente não usa senha.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-167">The Device Account does not typically use a password.</span></span> <span data-ttu-id="c1a4d-168">É possível atribuir a ela uma senha, mas há consequências, inclusive a possibilidade de o usuário ser bloqueado e não poder usar o aplicativo de console quando a senha expirar.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-168">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="c1a4d-169">Portanto, o administrador deve tomar cuidado para a senha não expirar.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-169">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="c1a4d-170">"Administrador" - Conta do Administrador Local</span><span class="sxs-lookup"><span data-stu-id="c1a4d-170">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="c1a4d-171">A senha padrão do Microsoft Teams Rooms é definida como "sfb".</span><span class="sxs-lookup"><span data-stu-id="c1a4d-171">Microsoft Teams Rooms default password is set to "sfb".</span></span> <span data-ttu-id="c1a4d-172">A senha pode ser alterada localmente, indo para Configurações do Windows Vá para o Windows ou no arquivo AutoUnattend.xml (use o gerenciador de Imagem do Sistema do Windows do ADK para fazer a alteração no \> arquivo xml).</span><span class="sxs-lookup"><span data-stu-id="c1a4d-172">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c1a4d-173">Certifique-se de alterar a senha das Salas do Microsoft Teams assim que possível.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-173">Be sure to change the Microsoft Teams Rooms password as soon as possible.</span></span> 
  
<span data-ttu-id="c1a4d-174">A senha do Administrador Local também pode ser gerenciada por meio da configuração de uma política de grupo em que os administradores do domínio se tornam administradores locais.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-174">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="c1a4d-175">A senha do Administrador local não é incluída como opção durante a Instalação.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-175">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="c1a4d-176">Conta do computador</span><span class="sxs-lookup"><span data-stu-id="c1a4d-176">Machine Account</span></span>

<span data-ttu-id="c1a4d-177">Assim como qualquer dispositivo Windows, o Nome do Computador pode ser renomeado clicando com o botão direito do mouse em **Configurações** \> **Sobre** \> **Renomear PC**.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-177">Much like any Windows device, the Machine Name can be renamed by right-clicking in **Settings** \> **About** \> **Rename PC**.</span></span>
  
<span data-ttu-id="c1a4d-178">Se você quiser renomear o computador depois de insinuá-lo em um domínio, use **Renomear-Computador**, um comando do PowerShell, seguido pelo novo nome do computador.</span><span class="sxs-lookup"><span data-stu-id="c1a4d-178">If you would like to rename the computer after joining it to a domain, use **Rename-Computer**, a PowerShell command, followed by the computer's new name.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c1a4d-179">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1a4d-179">Related topics</span></span>

[<span data-ttu-id="c1a4d-180">Planejar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-180">Plan Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="c1a4d-181">Requisitos das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-181">Microsoft Teams Rooms requirements</span></span>](requirements.md)
  
[<span data-ttu-id="c1a4d-182">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-182">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="c1a4d-183">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-183">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="c1a4d-184">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1a4d-184">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="c1a4d-185">Pré-requisitos para a Microsoft Store para Empresas e Educação</span><span class="sxs-lookup"><span data-stu-id="c1a4d-185">Prerequisites for Microsoft Store for Business and Education</span></span>](/microsoft-store/prerequisites-microsoft-store-for-business)