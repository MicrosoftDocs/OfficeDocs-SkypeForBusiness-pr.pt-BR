---
title: Instalar e configurar Opções de Disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Leia sobre como instalar e configurar as opções de ocupação no Skype for Business Server.
ms.openlocfilehash: 45779af0410dcadd1b5fe8e3988905e88acd9213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002511"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="d2d4f-103">Instalar e configurar Opções de Disponibilidade no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d2d4f-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="d2d4f-104">Leia sobre como instalar e configurar as opções de ocupação no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="d2d4f-105">O recurso Opções de Disponibilidade é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada serão tratadas quando o usuário já estiver em uma chamada ou em conferência ou tiver colocado uma chamada em espera.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="d2d4f-106">As chamadas novas ou de entrada poderão ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="d2d4f-107">Se o recurso Opções de Disponibilidade estiver habilitado para a organização, todos os usuários da empresa, tanto os usuários Enterprise Voice quanto os não Enterprise Voice, poderão usar as seguintes opções de configuração:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="d2d4f-108">Sinal de Ocupado quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão rejeitadas com um sinal de ocupado.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="d2d4f-109">Caixa Postal quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="d2d4f-110">Qualquer que seja a maneira de configurar as opções de disponibilidade, os usuários em uma chamada ou em conferência (ou aqueles com uma chamada em espera) não serão impedidos de iniciar novas chamadas ou conferências.  </span><span class="sxs-lookup"><span data-stu-id="d2d4f-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="d2d4f-111">Para obter mais informações sobre o recurso Opções de Disponibilidade, veja [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="d2d4f-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="d2d4f-112">Instalar </span><span class="sxs-lookup"><span data-stu-id="d2d4f-112">Install</span></span>

<span data-ttu-id="d2d4f-113">Verifique se você tem a versão mais recente do Skype for Business Server instalada e se instalou o patch mais recente.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="d2d4f-114">Para fazer isso, primeiro pare todos os serviços e execute o instalador de atualização do Skype for Business Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="d2d4f-115">Execute o comando Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="d2d4f-116">Execute o instalador SkypeServerUpdateInstaller.exe em cada servidor front-end de um pool.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="d2d4f-117">Execute o instalador SkypeServerUpdateInstaller.exe em cada SBS (Servidor de Ramificação Persistente), se deseja assegurar suporte para failover no SBS.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="d2d4f-p103">O instalador implantará a versão mais recente de Opções de Disponibilidade. No entanto, o aplicativo não é habilitado por padrão. Para habilitá-lo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="d2d4f-121">Execute o cmdlet [set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar as opções de ocupado globalmente, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="d2d4f-122">Em seguida, se o site tiver uma política de voz em vigor, você deverá habilitar Opções de Disponibilidade para a política de voz da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="d2d4f-123">Primeiro, execute [Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar o nome do site:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="d2d4f-124">Use o valor Identity (por exemplo: site: Redmond1) recuperado de Get-CsSite para recuperar a política de voz do site da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="d2d4f-125">Se o site tiver uma política de voz, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="d2d4f-126">Em seguida, execute o cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para adicionar opções de ocupado à lista de aplicativos de servidor, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="d2d4f-127">Você deve substituir% FQDN% pelo nome de domínio totalmente qualificado de um pool específico.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="d2d4f-128">Em seguida, execute o cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para atualizar as funções de controle de acesso baseado em função (RBAC) para os cmdlets de opções de ocupado, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="d2d4f-129">Por fim, inicie os serviços do Windows do Skype for Business Server em todos os servidores de front-end em todos os pools onde as opções de ocupação foram instaladas e habilitadas executando o comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="d2d4f-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="d2d4f-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="d2d4f-130">Configure</span></span>

<span data-ttu-id="d2d4f-131">Para configurar Opções de Disponibilidade, use o cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  </span><span class="sxs-lookup"><span data-stu-id="d2d4f-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="d2d4f-p104">Por exemplo, o comando a seguir configura as opções de disponibilidade para o usuário "Carlos Lima". Nessa configuração, qualquer chamada para "Carlos Lima" receberá um sinal de ocupado quando ele já estiver em uma chamada:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="d2d4f-134">No exemplo a seguir, o comando configura as opções de disponibilidade para a usuária "Clara Barbosa".</span><span class="sxs-lookup"><span data-stu-id="d2d4f-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="d2d4f-135">Nessa configuração, as novas chamadas de entrada para "Clara Barbosa" serão encaminhadas para a caixa postal quando ela já estiver em uma chamada:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="d2d4f-136">Você pode recuperar as informações de configuração de Opções de Disponibilidade usando o cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx).</span><span class="sxs-lookup"><span data-stu-id="d2d4f-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="d2d4f-137">O exemplo a seguir retorna a configuração de opções de ocupado para "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="d2d4f-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="d2d4f-138">Você pode remover o recurso Opções de Disponibilidade usando o cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="d2d4f-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="d2d4f-139">O comando a seguir remove o recurso Opções de Disponibilidade para "Carlos Lima":</span><span class="sxs-lookup"><span data-stu-id="d2d4f-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="d2d4f-140">Para obter informações detalhadas sobre os cmdlets que você usa para configurar opções de ocupado, consulte o conteúdo de referência técnica para [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="d2d4f-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="d2d4f-141">Habilitar log</span><span class="sxs-lookup"><span data-stu-id="d2d4f-141">Enable logging</span></span>

<span data-ttu-id="d2d4f-142">Para habilitar o log de Opções de Disponibilidade usando o Serviço de Log Centralizado, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="d2d4f-143">Verificar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="d2d4f-143">Verify and troubleshoot</span></span>

<span data-ttu-id="d2d4f-144">Depois de instalar as opções ocupadas, você pode verificar se a instalação foi bem-sucedida usando o cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar a lista de aplicativos do servidor.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="d2d4f-145">Se Opções de Disponibilidade estiver instalado adequadamente, a saída do cmdlet deverá mostrar a configuração de Opções de Disponibilidade, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="d2d4f-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="d2d4f-146">Você também pode usar o Visualizador de eventos do Windows para verificar se a instalação de opções ocupada foi bem-sucedida e se o Skype for Business Server carregou com êxito as opções ocupadas.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="d2d4f-147">Para verificar as opções de ocupado, abra o **Visualizador de eventos –\> logs\> de aplicativos e serviços-servidor Skype (ou LYNC)** e procure por ID do evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="d2d4f-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
