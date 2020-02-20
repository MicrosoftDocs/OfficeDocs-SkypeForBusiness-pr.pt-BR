---
title: Instalar e configurar opções de disponibilidade para o Skype for Business Server
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
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Leia sobre como instalar e configurar opções de disponibilidade no Skype for Business Server.
ms.openlocfilehash: 5078041401c710a249470ed6d3871f38a98a7420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113114"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="a4c04-103">Instalar e configurar opções de disponibilidade para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4c04-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="a4c04-104">Leia sobre como instalar e configurar opções de disponibilidade no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4c04-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="a4c04-105">Opções de disponibilidade é uma nova política de voz introduzida na atualização cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera.</span><span class="sxs-lookup"><span data-stu-id="a4c04-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="a4c04-106">As chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="a4c04-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="a4c04-107">Se as opções de disponibilidade estiverem habilitadas para a organização, todos os usuários da empresa, tanto os usuários do Enterprise Voice quanto os do não Enterprise Voice, poderão usar as seguintes opções de configuração:</span><span class="sxs-lookup"><span data-stu-id="a4c04-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="a4c04-108">Ocupado no ocupado-em que as novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="a4c04-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="a4c04-109">Caixa postal em ocupado-na qual as novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.</span><span class="sxs-lookup"><span data-stu-id="a4c04-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="a4c04-110">Independentemente de como as opções de disponibilidade são configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências.</span><span class="sxs-lookup"><span data-stu-id="a4c04-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="a4c04-111">Para obter mais informações sobre o recurso opções de disponibilidade, consulte [planejar opções de disponibilidade para o Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="a4c04-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="a4c04-112">Instalar</span><span class="sxs-lookup"><span data-stu-id="a4c04-112">Install</span></span>

<span data-ttu-id="a4c04-113">Verifique se você tem a versão mais recente do Skype for Business Server instalada e se você instalou o patch mais recente.</span><span class="sxs-lookup"><span data-stu-id="a4c04-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="a4c04-114">Para fazer isso, primeiro pare todos os serviços e, em seguida, execute o instalador de atualização do Skype for Business Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a4c04-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="a4c04-115">Execute o comando Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="a4c04-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="a4c04-116">Execute o instalador instalador skypeserverupdateinstaller. exe em cada servidor de front-end em um pool.</span><span class="sxs-lookup"><span data-stu-id="a4c04-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="a4c04-117">Execute o instalador instalador skypeserverupdateinstaller. exe em cada servidor de filial persistente (SBS), se você quiser garantir suporte para failover no SBS.</span><span class="sxs-lookup"><span data-stu-id="a4c04-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="a4c04-118">O instalador implantará a versão mais recente do aplicativo opções de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a4c04-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="a4c04-119">No entanto, o aplicativo não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a4c04-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="a4c04-120">Para habilitar o aplicativo, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a4c04-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="a4c04-121">Execute o cmdlet [set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente opções de disponibilidade, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a4c04-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="a4c04-122">Em seguida, se o site tiver uma política de voz, você deverá habilitar opções de disponibilidade para a política de voz da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a4c04-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="a4c04-123">Primeiro, execute [Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar o nome do site:</span><span class="sxs-lookup"><span data-stu-id="a4c04-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="a4c04-124">Use o valor Identity (por exemplo: site: Redmond1) recuperado de Get-CsSite para recuperar a política de voz do site da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a4c04-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="a4c04-125">Se houver uma política de voz para o site, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a4c04-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="a4c04-126">Em seguida, execute o cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para adicionar opções de disponibilidade à lista de aplicativos de servidor, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a4c04-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="a4c04-127">Você deve substituir% FQDN% pelo nome de domínio totalmente qualificado de um pool específico.</span><span class="sxs-lookup"><span data-stu-id="a4c04-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="a4c04-128">Em seguida, execute o cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para atualizar as funções RBAC (controle de acesso baseado em função) para os cmdlets de opções de disponibilidade, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="a4c04-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="a4c04-129">Por fim, inicie os serviços do Windows do Skype for Business Server em todos os servidores front-end em todos os pools em que as opções de disponibilidade foram instaladas e habilitadas executando o comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="a4c04-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="a4c04-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="a4c04-130">Configure</span></span>

<span data-ttu-id="a4c04-131">Para configurar opções de disponibilidade, use o cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a4c04-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="a4c04-132">Por exemplo, o comando a seguir configura as opções de disponibilidade para o usuário "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="a4c04-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="a4c04-133">Nessa configuração, qualquer chamada para "Ken Myer" retornará um sinal de ocupado quando já estiver em uma chamada:</span><span class="sxs-lookup"><span data-stu-id="a4c04-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="a4c04-134">No próximo exemplo, o comando configura as opções de disponibilidade para o usuário "clara Barbosa".</span><span class="sxs-lookup"><span data-stu-id="a4c04-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="a4c04-135">Nessa configuração, novas chamadas de entrada para "clara Barbosa" serão encaminhadas para a caixa postal quando ela já estiver em uma chamada:</span><span class="sxs-lookup"><span data-stu-id="a4c04-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="a4c04-136">Você pode recuperar as informações de configuração sobre as opções de disponibilidade usando o cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a4c04-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="a4c04-137">O exemplo a seguir retorna a configuração de opções de disponibilidade para "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="a4c04-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="a4c04-138">Você pode remover as opções de disponibilidade usando o cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a4c04-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="a4c04-139">O comando a seguir remove as opções de disponibilidade para "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="a4c04-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="a4c04-140">Para obter informações detalhadas sobre os cmdlets usados para configurar opções de disponibilidade, consulte o conteúdo de referência técnica para [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="a4c04-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="a4c04-141">Habilitar o registro em log</span><span class="sxs-lookup"><span data-stu-id="a4c04-141">Enable logging</span></span>

<span data-ttu-id="a4c04-142">Para habilitar o registro em log para opções de disponibilidade usando o serviço de registro em log centralizado, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a4c04-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="a4c04-143">Verificar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="a4c04-143">Verify and troubleshoot</span></span>

<span data-ttu-id="a4c04-144">Após instalar as opções de disponibilidade, você pode verificar se a instalação foi bem-sucedida usando o cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar a lista de aplicativos do servidor.</span><span class="sxs-lookup"><span data-stu-id="a4c04-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="a4c04-145">Se as opções de disponibilidade estiverem instaladas corretamente, a saída do cmdlet deverá mostrar a configuração opções de disponibilidade da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a4c04-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="a4c04-146">Você também pode usar o Visualizador de eventos do Windows para verificar se a instalação das opções de disponibilidade foi bem-sucedida e se o Skype for Business Server carregou com êxito as opções de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="a4c04-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="a4c04-147">Para verificar as opções de disponibilidade, abra o **Visualizador de eventos\> -logs de aplicativos e serviços-\> Skype (ou Lync) Server** e procure por ID de evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="a4c04-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
