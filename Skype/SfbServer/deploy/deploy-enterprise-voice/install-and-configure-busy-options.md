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
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604208"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalar e configurar opções de disponibilidade para o Skype for Business Server

Leia sobre como instalar e configurar opções de disponibilidade no Skype for Business Server.

Opções de disponibilidade é uma nova política de voz introduzida na atualização cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. As chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.

Se as opções de disponibilidade estiverem habilitadas para a organização, todos os usuários da empresa, tanto os usuários do Enterprise Voice quanto os do não Enterprise Voice, poderão usar as seguintes opções de configuração:

- Ocupado no ocupado-em que as novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.

- Caixa postal em ocupado-na qual as novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.

Independentemente de como as opções de disponibilidade são configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências.

Para obter mais informações sobre o recurso opções de disponibilidade, consulte [planejar opções de disponibilidade para o Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalar

Verifique se você tem a versão mais recente do Skype for Business Server instalada e se você instalou o patch mais recente. Para fazer isso, primeiro pare todos os serviços e, em seguida, execute o instalador de atualização do Skype for Business Server da seguinte maneira:

1. Execute o comando Stop-CsWindowsService.

2. Execute o instalador instalador skypeserverupdateinstaller. exe em cada servidor de front-end em um pool.

3. Execute o instalador instalador skypeserverupdateinstaller. exe em cada servidor de filial persistente (SBS), se você quiser garantir suporte para failover no SBS.

O instalador implantará a versão mais recente do aplicativo opções de disponibilidade. No entanto, o aplicativo não está habilitado por padrão. Para habilitar o aplicativo, execute as seguintes etapas:

1. Execute o cmdlet [set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente opções de disponibilidade, conforme mostrado no exemplo a seguir:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Em seguida, se o site tiver uma política de voz, você deverá habilitar opções de disponibilidade para a política de voz da seguinte maneira:

    Primeiro, execute [Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar o nome do site:

   ```powershell
   Get-CsSite
   ```

    Use o valor Identity (por exemplo: site: Redmond1) recuperado de Get-CsSite para recuperar a política de voz do site da seguinte maneira:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se houver uma política de voz para o site, execute o seguinte comando:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Em seguida, execute o cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) para adicionar opções de disponibilidade à lista de aplicativos de servidor, conforme mostrado no exemplo a seguir:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Você deve substituir% FQDN% pelo nome de domínio totalmente qualificado de um pool específico.

4. Em seguida, execute o cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para atualizar as funções RBAC (controle de acesso baseado em função) para os cmdlets de opções de disponibilidade, conforme mostrado no exemplo a seguir:

   ```powershell
   Update-CsAdminRole
   ```

5. Por fim, inicie os serviços do Windows do Skype for Business Server em todos os servidores front-end em todos os pools em que as opções de disponibilidade foram instaladas e habilitadas executando o comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurar

Para configurar opções de disponibilidade, use o cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Por exemplo, o comando a seguir configura as opções de disponibilidade para o usuário "Ken Myer". Nessa configuração, qualquer chamada para "Ken Myer" retornará um sinal de ocupado quando já estiver em uma chamada:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

No próximo exemplo, o comando configura as opções de disponibilidade para o usuário "clara Barbosa". Nessa configuração, novas chamadas de entrada para "clara Barbosa" serão encaminhadas para a caixa postal quando ela já estiver em uma chamada:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Você pode recuperar as informações de configuração sobre as opções de disponibilidade usando o cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . O exemplo a seguir retorna a configuração de opções de disponibilidade para "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Você pode remover as opções de disponibilidade usando o cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . O comando a seguir remove as opções de disponibilidade para "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obter informações detalhadas sobre os cmdlets usados para configurar opções de disponibilidade, consulte o conteúdo de referência técnica para [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitar o registro em log

Para habilitar o registro em log para opções de disponibilidade usando o serviço de registro em log centralizado, especifique o seguinte:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificar e solucionar problemas

Após instalar as opções de disponibilidade, você pode verificar se a instalação foi bem-sucedida usando o cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar a lista de aplicativos do servidor. Se as opções de disponibilidade estiverem instaladas corretamente, a saída do cmdlet deverá mostrar a configuração opções de disponibilidade da seguinte maneira:

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

Você também pode usar o Visualizador de eventos do Windows para verificar se a instalação das opções de disponibilidade foi bem-sucedida e se o Skype for Business Server carregou com êxito as opções de disponibilidade. Para verificar as opções de disponibilidade, abra o **Visualizador de eventos\> -logs de aplicativos e serviços-\> Skype (ou Lync) Server** e procure por ID de evento = 30253.
