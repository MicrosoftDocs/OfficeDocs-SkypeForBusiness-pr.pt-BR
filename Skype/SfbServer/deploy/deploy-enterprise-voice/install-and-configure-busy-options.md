---
title: Instalar e configurar Opções de Ocupado para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Leia sobre como instalar e configurar Opções de Ocupado no Skype for Business Server.
ms.openlocfilehash: 5e0dde157fc39ab7c24ddd297e858ce5a06e888f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835909"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalar e configurar Opções de Ocupado para Skype for Business Server

Leia sobre como instalar e configurar Opções de Ocupado no Skype for Business Server.

Opções de Ocupado é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada são tratadas quando um usuário já está em uma chamada ou conferência ou tem uma chamada colocada em espera. Chamadas novas ou de entrada podem ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.

Se Opções de Ocupado estiver habilitada para a organização, todos os usuários no Enterprise, usuários Enterprise Voice usuários não Enterprise Voice, poderão usar as seguintes opções de configuração:

- Ocupado em Ocupado - Em que novas chamadas de entrada serão rejeitadas com um sinal de ocupado se o usuário estiver ocupado.

- Caixa postal em Ocupado - Em que novas chamadas de entrada serão encaminhadas para a caixa postal se o usuário estiver ocupado.

Independentemente de como suas opções de ocupado estão configuradas, os usuários em uma chamada ou conferência ou aqueles com uma chamada em espera não são impedidos de iniciar novas chamadas ou conferências.

Para obter mais informações sobre o recurso Opções de Ocupado, consulte [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalar

Certifique-se de ter a versão mais recente do Skype for Business Server instalada e se você instalou o patch mais recente. Para fazer isso, primeiro pare todos os serviços e execute o Skype for Business Server instalador de atualização da seguinte forma:

1. Execute o Stop-CsWindowsService comando.

2. Execute o SkypeServerUpdateInstaller.exe instalador em cada servidor Front-End em um pool.

3. Execute o SkypeServerUpdateInstaller.exe instalador em cada SBS (Servidor de FilialVivível), se quiser garantir o suporte para failover no SBS.

O instalador implantará a versão mais recente do aplicativo Opções de Ocupado. No entanto, o aplicativo não está habilitado por padrão. Para habilitar o aplicativo, execute as seguintes etapas:

1. Execute o cmdlet [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente Opções de Ocupado, conforme mostrado no exemplo a seguir:

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Em seguida, se o site tiver uma política de voz, você deverá habilitar Opções de Ocupado para a política de voz da seguinte forma:

    Primeiro, execute [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) para recuperar o nome do site:

   ```powershell
   Get-CsSite
   ```

    Use o valor Identity (por exemplo: Site:Redmond1) recuperado do Get-CsSite para recuperar a política de voz do site da seguinte forma:

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se existir uma política de voz para o site, execute o seguinte comando:

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Em seguida, execute o cmdlet [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) para adicionar Opções de Ocupado à lista de aplicativos de servidor, conforme mostrado no exemplo a seguir:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Você deve substituir %FQDN% pelo nome de domínio totalmente qualificado de um pool específico.

4. Em seguida, execute o cmdlet [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) para atualizar as funções de controle de acesso baseado em função (RBAC) para os cmdlets Opções de Ocupado, conforme mostrado no exemplo a seguir:

   ```powershell
   Update-CsAdminRole
   ```

5. Por fim, inicie os serviços Skype for Business Server Windows em todos os servidores Front-End em todos os pools em que opções de ocupado foram instaladas e habilitadas executando o comando [Start-CsWindowsService:](/powershell/module/skype/start-cswindowsservice?view=skype-ps)

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurar

Para configurar Opções de Ocupado, use o cmdlet [Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Por exemplo, o comando a seguir configura opções de ocupado para o usuário "Ken Myer". Nesta configuração, qualquer chamada para "Ken Myer" retornará um sinal de ocupado quando ele já estiver em uma chamada:

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

No próximo exemplo, o comando configura opções de ocupado para o usuário "Chrystal Velasquez". Nesta configuração, novas chamadas de entrada para "Chrystal Velasquez" serão encaminhadas para a caixa postal quando ela já estiver em uma chamada:

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Você pode recuperar informações de configuração sobre Opções de Ocupado usando o cmdlet [Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) O exemplo a seguir retorna a configuração Opções de Ocupado para "KenMyer@Contoso.com":

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Você pode remover Opções de Ocupado usando o cmdlet [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) O comando a seguir remove Opções de Ocupado para "Ken Myer":

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obter informações detalhadas sobre os cmdlets que você usa para configurar Opções de Ocupado, consulte o conteúdo de referência técnica para [Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitar o log

Para habilitar o log para Opções de Ocupado usando o Serviço de Log Centralizado, especifique o seguinte:

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificar e solucionar problemas

Depois de instalar Opções de Ocupado, você pode verificar se a instalação foi bem-sucedida usando o cmdlet [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) para recuperar a lista de aplicativos de servidor. Se Opções de Ocupado estiver instalada corretamente, a saída do cmdlet deverá mostrar a configuração opções de ocupado da seguinte maneira:

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

Você também pode usar Windows Visualizador de Eventos para verificar se a instalação de Opções de Ocupado foi bem-sucedida e que Skype for Business Server opções de ocupado carregadas com êxito. Para verificar Opções de Ocupado, abra o Visualizador de Eventos - Logs de Aplicativos e Serviços **\> - Skype \> (ou Lync) Server** e pesquise a ID do Evento = 30253.