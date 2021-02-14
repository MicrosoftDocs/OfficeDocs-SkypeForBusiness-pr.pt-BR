---
title: Manutenção e operações das Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Leia este tópico para saber mais sobre o gerenciamento de Salas do Microsoft Teams, a próxima geração de Sistemas de Salas do Skype.
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662456"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Manutenção e operações das Salas do Microsoft Teams 
 
Leia este tópico para saber mais sobre o gerenciamento de Salas do Microsoft Teams, a próxima geração de Sistemas de Salas do Skype.
  
O Microsoft Teams Rooms é a solução de conferência mais recente da Microsoft projetada para transformar sua sala de reunião em uma experiência rica e colaborativa. Os usuários aproveitarão sua interface familiar do Microsoft Teams ou do Skype for Business, e os administradores de IT apreciarão um aplicativo de Reunião do Skype do Windows 10 implantado e gerenciado facilmente. As Salas do Microsoft Teams foram projetadas para aproveitar equipamentos existentes, como painéis DOES, para facilitar a instalação e trazer o Microsoft Teams ou o Skype for Business para a sala de reunião.
  
Com configurações adicionais, o gerenciamento remoto é possível usando o Monitor do Microsoft Azure conforme descrito no Plano de Gerenciamento de Salas do Microsoft Teams com o [Monitor do Azure,](azure-monitor-plan.md)Implantar o gerenciamento de salas do Microsoft Teams com o [Monitor do Azure,](azure-monitor-deploy.md)Gerenciar dispositivos de Salas do Microsoft Teams com o [Monitor do Azure.](azure-monitor-deploy.md) Você também pode [gerenciar as configurações do console](xml-config-file.md)de Salas do Microsoft Teams remotamente com um arquivo de configuração XML, que inclui a aplicação de um tema de exibição personalizado. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Coletando logs em Salas do Microsoft Teams
<a name="Logs"> </a>

Para coletar logs, você deve invocar o script de coleção de log que acompanha o aplicativo Salas do Microsoft Teams. No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configurações da tela frontal da sala
<a name="Display"> </a>

Configure a tela frontal da sala para o modo Estendido. Isso garantirá que a interface do usuário do console não seja duplicada nessa exibição quando você ciclou a energia no vídeo.
  
> [!NOTE]
> Se você desejar que uma exibição na frente da sala alternar automaticamente para uma fonte de vídeo ativa (como um console MTR) quando a fonte desperta do modo de espera, certas condições devem ser atendidas. Esse recurso é opcional, mas compatível com o software Salas do Microsoft Teams, fornecido com suporte para o recurso de hardware subjacente. Uma TV de consumidor usada como uma frente de exibição de sala precisa dar suporte ao recurso CONTROLE de Eletrônica do Consumidor (CEC) de HDMI.  Dependendo do encaixe ou do console selecionado (que pode não dar suporte ao CEC, consulte a documentação de suporte do fabricante), um controlador como [um HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) doTexron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron pode ser necessário para habilitar o comportamento desejado. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Redefinição de Salas do Microsoft Teams (Restauração de Fábrica)
<a name="Reset"> </a>

Se o Microsoft Teams Rooms não estiver funcionando bem, executar uma redefinição de fábrica pode ajudar. Para fazer isso, use a ferramenta [de recuperação da Sala do Microsoft Teams](recovery-tool.md) e siga as instruções de restauração de fábrica.

> [!NOTE]
> Há um problema conhecido em que as Salas do Microsoft Teams podem se tornar inutilizáveis se a opção Manter meus arquivos – Remove **Aplicativos** e configurações, mas mantém a opção de arquivos pessoais selecionada durante o processo de Redefinição do Windows. Não *use* essa opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|Grupo de trabalho |Não ingresso em domínio|Ingresso em domínio|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Área de trabalho remota  <br/> PowerShell Remoto  <br/> |Área de trabalho remota (requer mais configuração)  <br/> Powershell remoto (requer mais configuração)  <br/> Configuration Manager  <br/> |
|Atualização do sistema operacional  <br/> |Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configuração de contas do Skype  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
|Acesso aos logs  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurando a política de grupo para salas do Microsoft Teams
<a name="GroupPolicy"> </a>

Esta seção aborda as configurações do sistema das que as Salas do Microsoft Teams dependem para funcionar corretamente. Ao ingressar em Salas do Microsoft Teams em um domínio, certifique-se de que sua política de grupo não substitua as configurações na tabela a seguir.
  

|Configuração|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite que o Microsoft Teams Rooms seja inicializado  <br/> |
|Power Management - \> No AC, desligue a tela após 10 minutos  <br/> Power Management - \> No AC, nunca coloque o sistema no sleep  <br/> |Permite que as Salas do Microsoft Teams desliguem as exibições anexadas e despertam automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou meios equivalentes de desabilitar a expiração de senha na conta local. Se isso não ocorrer, a conta do Skype poderá falhar ao fazer logon reclamando sobre uma senha expirada. Observe que isso afeta todas as contas locais no computador e, portanto, a falha ao definir isso também fará com que a conta administrativa na caixa expire também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
A transferência de arquivos usando Políticas de Grupo é discutida em [Configurar um Item de Arquivo.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

> [!NOTE]
> Quando o dispositivo Microsoft Teams Rooms é compatível com a próxima versão do sistema operacional Windows 10, o dispositivo é atualizado automaticamente para a próxima versão por meio do Windows Update. O dispositivo Microsoft Teams Rooms não deve ser atualizado para a próxima versão do Windows 10 manualmente ou habilitando as políticas de grupo do Windows Update for Business (WUFB), "Selecione o nível de preparação do Windows para as atualizações que você deseja receber" e "Selecione quando as versões prévias e atualizações de recursos são recebidas" por meio do GPO. Um dispositivo com essas políticas de grupo habilitado é conhecido por ter problemas com a atualização do sistema operacional Windows 10 pelo aplicativo Salas do Microsoft Teams.

## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para ver exemplos de script):
  
- Obter dispositivos conectados
- Obter o status do aplicativo
- Obter informações do sistema
- Reiniciar o sistema
- Recuperar logs
- Transferir arquivos (requer um domínio ingressados em Salas do Microsoft Teams)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa habilitar o PowerShell remoto para seu ambiente no sistema Salas do Microsoft Teams para executar as operações abaixo. Consulte a documentação **[em Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entre como Administrador em um dispositivo Microsoft Teams Rooms.
2. Abra um prompt de comando elevado do PowerShell.
3. Insira o seguinte comando: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Abra a Política de Segurança Local e adicione o grupo de *segurança Administradores* às Configurações de Segurança Local. Atribuição de Direitos de Usuário de Políticas Locais acessa este computador  >    >    >  **a partir da rede.**

Para executar uma operação de gerenciamento:
  
1. Entre em um computador com credenciais de conta que tenham permissão para executar comandos do PowerShell em um dispositivo de Salas do Microsoft Teams.
2. Abra um prompt de comando normal do PowerShell no computador.
3. Copie o texto do comando da tabela abaixo e o colará no prompt.
4. Substitua  `<Device fqdn>` os campos por valores FQDN apropriados ao seu ambiente.
5. Substitua pelo nome do arquivo e o caminho local do arquivo  *\<path\>*  de configuração SkypeSettings.xml mestre (ou imagem do tema).
    
Para obter dispositivos anexados
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obter o status de aplicativos
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obter informações do sistema
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Reiniciar o sistema
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Recuperar logs
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Pressionar um arquivo de configuração XML (ou um gráfico de tema)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, as Salas do Microsoft Teams tenta se conectar à Windows Store para obter a versão mais recente do software Salas do Microsoft Teams, para que o dispositivo exigirá acesso regular à Internet. Antes de entrar em contato com a Microsoft com problemas de suporte, certifique-se de que o dispositivo Salas do Microsoft Teams está carregado com a versão mais recente do aplicativo.
  
Por padrão, as Salas do Microsoft Teams se conectam ao Windows Update para recuperar atualizações de firmware do sistema operacional e do dispositivo periférico USB e as instala fora do horário comercial configurado. Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.
  
Se quiser gerenciar as atualizações manualmente e não conseguir seguir o procedimento normal para a [Microsoft Store for Business](https://businessstore.microsoft.com/store) distribuir aplicativos [offline,](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)você pode adquirir o arquivo APPX apropriado e dependências do [kit](https://go.microsoft.com/fwlink/?linkid=851168) de implantação (nas instruções para Configurar um console de Salas do [Microsoft Teams)](console.md)que pode ser usado com o Configuration Manager. O lançamento do kit de implantação fica atrasado na versão da loja, portanto, ele pode nem sempre corresponder ao build disponível mais recente.
  
### <a name="to-update-using-powershell"></a>Para atualizar usando o Powershell

1. Extraia o pacote da [instalação MSI](https://go.microsoft.com/fwlink/?linkid=851168) para um compartilhamento que o dispositivo pode acessar.
2. Execute o seguinte script destinado aos dispositivos microsoft teams Rooms, alterando \<share\> para o compartilhamento de dispositivos conforme apropriado:
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como instalar manualmente um certificado de AC particular, exigem a colocação do dispositivo Surface Pro no modo de Administração. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Alternar para o Modo de Administração e voltar quando o aplicativo Salas do Microsoft Teams estiver em execução

1. Desligue todas as chamadas em andamento e retorne para a tela inicial.
2. Selecione o ícone De engrenagem e o menu (as opções são **Configurações,** **Acessibilidade** e **Reiniciar Dispositivo).**
3. Selecione **Configurações**.
4. Digite a senha do administrador. A tela Configuração será exibida.  Se o dispositivo não for de domínio ingressado, a conta administrativa local (nome de usuário "Administrador") será usada por padrão. A senha padrão dessa conta é 'sfb', altere a senha assim que possível. Se o computador estiver ingressado em domínio, você poderá entrar com uma conta de domínio apropriadamente privilegiado. 
5. Selecione **Configurações do Windows** na coluna esquerda.
6. Escolha **Vá para Entrada como Admin**.
7. Digite a senha do administrador. Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows. 
8. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
9. Execute as tarefas administrativas necessárias.
10. Saia da conta de Administrador.
11. Retorne às Salas do Microsoft Teams selecionando o ícone de conta de usuário no lado esquerdo da tela e selecionando **Skype.**
    
    Se o usuário do **Skype** não estiver  listado, talvez seja preciso selecionar outro usuário e inserir **.\skype** como o nome de usuário e entrar.
    
Agora, o console está novamente em seu modo de operação normal. O procedimento a seguir exige que você anexe um teclado ao dispositivo se um ainda não estiver anexado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Alternar para o Modo de Administração e voltar quando o aplicativo Salas do Microsoft Teams falhar

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows. 
2. Faça logon no desktop usando as credenciais administrativas.
3. Execute as tarefas administrativas necessárias.
4. Reinicie o computador quando terminar.

    > [!NOTE]
    > Esse método não faz logoff do usuário do Skype ou termina o aplicativo de forma elegante, mas você o usaria se o aplicativo não estivesse respondendo e o outro método não estivesse disponível. 

   O console é reiniciado em seu modo de operação normal, executando o aplicativo Salas do Microsoft Teams. Você pode remover o teclado, se ele foi anexado para permitir que você execute este procedimento.
   ## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
   <a name="TS"> </a>

- Os convites de reunião podem não aparecer quando enviados além dos limites do domínio (por exemplo, entre duas empresas). Nesses casos, os administradores de IT devem decidir se permitem que usuários externos agendem uma reunião.
- As Salas do Microsoft Teams não são suportadas por redirecionamentos de Descoberta Automática do Exchange por meio do Exchange 2010.
- Em geral, é uma boa prática que os administradores de IT desabilitem os pontos de extremidade de áudio que eles não pretendem usar.
- Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, às vezes, o problema é resolvido reiniciando o sistema salas do Microsoft Teams.
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
    
