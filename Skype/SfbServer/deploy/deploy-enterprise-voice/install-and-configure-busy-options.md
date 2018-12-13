---
title: Instalar e configurar Opções de Disponibilidade no Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Leia sobre como instalar e configurar opções de disponibilidade no Skype para Business Server.
ms.openlocfilehash: a5fdd117f2c812bba69978a7d2943321b940bcc4
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240656"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Instalar e configurar Opções de Disponibilidade no Skype for Business Server

Leia sobre como instalar e configurar opções de disponibilidade no Skype para Business Server.

O recurso Opções de Disponibilidade é uma nova política de voz introduzida na Atualização Cumulativa de julho de 2016 que permite configurar como as chamadas de entrada serão tratadas quando o usuário já estiver em uma chamada ou em conferência ou tiver colocado uma chamada em espera. As chamadas novas ou de entrada poderão ser rejeitadas com um sinal de ocupado ou encaminhadas para a caixa postal.

Se o recurso Opções de Disponibilidade estiver habilitado para a organização, todos os usuários da empresa, tanto os usuários Enterprise Voice quanto os não Enterprise Voice, poderão usar as seguintes opções de configuração:

- Sinal de Ocupado quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão rejeitadas com um sinal de ocupado.

- Caixa Postal quando Ocupado - Se o usuário estiver ocupado, as novas chamadas de entrada serão encaminhadas para a caixa postal.

Qualquer que seja a maneira de configurar as opções de disponibilidade, os usuários em uma chamada ou em conferência (ou aqueles com uma chamada em espera) não serão impedidos de iniciar novas chamadas ou conferências.  

Para obter mais informações sobre o recurso Opções de Disponibilidade, veja [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Instalar 

Verifique se você tem a versão mais recente do Skype para Business Server instalado e que você instalou o patch mais recente. Para fazer isso, primeiro, interrompa todos os serviços e, em seguida, execute o Skype do instalador da atualização Business Server da seguinte maneira:

1. Execute o comando Stop-CsWindowsService.

2. Execute o instalador SkypeServerUpdateInstaller.exe em cada servidor front-end de um pool.

3. Execute o instalador SkypeServerUpdateInstaller.exe em cada SBS (Servidor de Ramificação Persistente), se deseja assegurar suporte para failover no SBS.

O instalador implantará a versão mais recente de Opções de Disponibilidade. No entanto, o aplicativo não é habilitado por padrão. Para habilitá-lo, faça o seguinte:

1. Execute o cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) para habilitar globalmente opções ocupado, conforme mostrado no exemplo a seguir:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Em seguida, se o site tiver uma política de voz em vigor, você deverá habilitar Opções de Disponibilidade para a política de voz da seguinte maneira:

    Primeiro, execute [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) para recuperar o nome do site:

   ```
   Get-CsSite
   ```

    Use o valor de identidade (por exemplo: Site: Redmond1) recuperada do Get-CsSite para recuperar a política de voz do site da seguinte maneira:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Se o site tiver uma política de voz, execute o seguinte comando:

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Em seguida, execute o cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) , para adicionar as opções de ocupado à lista de aplicativos de servidor, conforme mostrado no exemplo a seguir:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Você deve substituir % FQDN % com o nome de domínio totalmente qualificado de um pool específico.

4. Em seguida, execute o cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) para atualizar as funções RBAC (controle) de acesso baseado em função para os cmdlets ocupado opções, conforme mostrado no exemplo a seguir:

   ```
   Update-CsAdminRole
   ```

5. Finalmente, inicie o Skype para serviços corporativos de servidor Windows em todos os servidores de Front-End em todos os pools onde opções ocupado foi instalada e habilitada executando o comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurar

Para configurar Opções de Disponibilidade, use o cmdlet [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  

Por exemplo, o comando a seguir configura as opções de disponibilidade para o usuário "Carlos Lima". Nessa configuração, qualquer chamada para "Carlos Lima" receberá um sinal de ocupado quando ele já estiver em uma chamada:

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

No exemplo a seguir, o comando configura as opções de disponibilidade para a usuária "Clara Barbosa". Nessa configuração, as novas chamadas de entrada para "Clara Barbosa" serão encaminhadas para a caixa postal quando ela já estiver em uma chamada:

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Você pode recuperar as informações de configuração de Opções de Disponibilidade usando o cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx). O exemplo a seguir retorna a configuração de opções de disponibilidade para "KenMyer@Contoso.com":

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Você pode remover o recurso Opções de Disponibilidade usando o cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). O comando a seguir remove o recurso Opções de Disponibilidade para "Carlos Lima":

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Para obter informações detalhadas sobre os cmdlets que você pode usar para configurar as opções de disponibilidade, consulte o conteúdo de referência técnica para [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Habilitar log

Para habilitar o log de Opções de Disponibilidade usando o Serviço de Log Centralizado, especifique o seguinte:

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Verificar e solucionar problemas

Depois de instalar opções ocupado, você pode verificar se a instalação foi bem-sucedida, usando o cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) , para recuperar a lista de aplicativos para servidores. Se Opções de Disponibilidade estiver instalado adequadamente, a saída do cmdlet deverá mostrar a configuração de Opções de Disponibilidade, como a seguir:

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

Você também pode usar o Visualizador de eventos do Windows para verificar se a instalação de opções ocupado foi bem-sucedida e que o Skype para Business Server carregada com êxito as opções ocupado. Para verificar as opções de ocupado, abra **Visualizador de eventos -\> Logs de aplicativo e serviços -\> Skype (ou Lync) Server** e procure a ID do evento = 30253.
