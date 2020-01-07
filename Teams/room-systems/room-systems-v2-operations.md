---
title: Manutenção e operações de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Leia este tópico para saber mais sobre o gerenciamento de salas do Microsoft Teams, a próxima geração de sistemas de sala do Skype.
ms.openlocfilehash: 4e1c554d5ae21d845fed9a543875feb631e0e264
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952724"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Manutenção e operações de salas do Microsoft Teams 
 
Leia este tópico para saber mais sobre o gerenciamento de salas do Microsoft Teams, a próxima geração de sistemas de sala do Skype.
  
Salas do Microsoft Teams é a solução de conferência mais recente da Microsoft projetada para transformar sua sala de reunião em uma experiência avançada e colaborativa. Os usuários gostarão da interface familiar do Microsoft Teams ou do Skype for Business, e os administradores de ti apreciarão um aplicativo de reunião do Skype com facilidade de implantação e gerenciamento do Windows 10. As salas do Microsoft Teams foram projetadas para aproveitar o equipamento existente, como painéis LCD, para facilitar a instalação e trazer o Microsoft Teams ou o Skype for Business para a sua sala de reuniões.
  
Com configurações adicionais, o gerenciamento remoto é possível usando o Microsoft Azure monitor, conforme descrito em [planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-plan.md), [implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md), [gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-deploy.md). Você também pode [gerenciar as configurações do console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md), que inclui a aplicação de um tema de exibição personalizado. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Coletando logs em salas do Microsoft Teams
<a name="Logs"> </a>

Para coletar logs, você deve invocar o script de coleta de log que acompanha o aplicativo salas do Microsoft Teams. No modo Admin, inicie um prompt de comandos com privilégios elevados e emita o seguinte comando:
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Os logs serão exibidos como um arquivo ZIP em c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Configurações da tela frontal da sala
<a name="Display"> </a>

Configure a tela frontal da sala para o modo Estendido. Isso garantirá que a interface do usuário do console não seja duplicada naquele vídeo quando você desligar o monitor.
  
> [!NOTE]
> Se você quiser uma exibição do lado da sala para alternar automaticamente para uma fonte de vídeo ativa (como um console do MTR) quando a origem é ativada do modo de espera, determinadas condições devem ser atendidas. Esse recurso é opcional, mas suportado pelo software de salas Microsoft Teams, desde que o hardware subjacente seja compatível com o recurso. Uma TV para consumidor usada como uma frontal da exibição de sala precisa dar suporte ao recurso de controle de eletrônicos do consumidor (CEC) de HDMI.  Dependendo do Dock ou console selecionado (que pode não ser compatível com o CEC, confira a documentação de suporte do fabricante), um controlador como um controlador [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) do Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron pode ser necessário para habilitar o comportamento desejado. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Redefinição de salas do Microsoft Teams (restauração de fábrica)
<a name="Reset"> </a>

Se as salas do Microsoft Teams não estiverem funcionando bem, executar uma redefinição de fábrica pode ajudar. Para fazer isso, use a [ferramenta de recuperação de sala do Microsoft Teams](recovery-tool.md) e siga as instruções de restauração de fábrica.

> [!NOTE]
> Há um problema conhecido em que as salas do Microsoft Teams podem ficar inúteis se a opção **manter meus arquivos-remove meus arquivos-remove aplicativos e configurações, mas mantém a opção arquivos pessoais** selecionada durante o processo de redefinição do Windows. Não *Use essa* opção.
  
## <a name="supported-remote-options"></a>Opções remotas com suporte
<a name="RemoteOptions"> </a>

A tabela a seguir resume as operações remotas possíveis e os métodos que você pode usar para executá-las.
  

|Grupo de trabalho |Não ingresso em domínio|Ingresso em domínio|
|:-----|:-----|:-----|
|Reiniciar  <br/> |Área de trabalho remota  <br/> PowerShell Remoto  <br/> |Área de trabalho remota (requer configuração adicional)  <br/> PowerShell remoto (requer configuração adicional)  <br/> SCCM  <br/> |
|Atualização do sistema operacional  <br/> |Se forem necessárias regras mais restritivas, veja as seguintes URLs de lista de permissões:  <br/> |Windows Update  <br/> WSUS  <br/> |
|Atualização de aplicativos  <br/> |Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuração de contas do Skype  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
|Acesso aos logs  <br/> |Sem suporte no momento  <br/> |Sem suporte no momento  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configurando a política de grupo para salas do Microsoft Teams
<a name="GroupPolicy"> </a>

Esta seção abrange as configurações do sistema das quais as salas do Microsoft Teams dependem para funcionar corretamente. Ao ingressar em salas do Microsoft Teams em um domínio, verifique se a política de grupo não substitui as configurações na tabela a seguir.
  

|Configuração|Permite|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permite que salas do Microsoft Teams sejam inicializadas  <br/> |
|Gerenciamento de energia\> -em AC, desligar a tela após 10 minutos  <br/> Gerenciamento de energia\> -em AC, nunca coloque o sistema em suspensão  <br/> |Permite que as salas do Microsoft Teams desativem exibições anexadas e ativadas automaticamente  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou uma maneira equivalente de desabilitar a expiração de senha na conta local. Deixar de fazer isso fará com que a conta do Skype falhe ao fazer logon com uma senha expirada. Observe que isso afeta todas as contas locais do computador e, portanto, não definir isso também fará com que a conta administrativa na caixa acabe de expirar também.  <br/> |Permite que a conta do Skype esteja sempre conectada  <br/> |
   
A transferência de arquivos usando políticas de grupo é discutida em [configurar um item de arquivo](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).

> [!NOTE]
> Quando o dispositivo de salas do Microsoft Teams é compatível com a próxima versão do Windows 10 OS, o dispositivo é atualizado automaticamente para a próxima versão por meio do Windows Update. O dispositivo de salas do Microsoft Teams não deve ser atualizado manualmente para o próximo lançamento do Windows 10 ou por meio da habilitação das políticas de grupo do Windows Update for Business (WUFB) "selecionar o nível de preparação do Windows para as atualizações que você deseja receber" e "selecionar quando versões prévias e As atualizações de recursos são recebidas "através de um GPO. Um dispositivo com essas políticas de grupo habilitada é conhecido por ter problemas com o aplicativo de salas do Microsoft Teams para a atualização do Windows 10.

## <a name="remote-management-using-powershell"></a>Gerenciamento remoto usando o PowerShell
<a name="RemotePS"> </a>

Você pode executar as seguintes operações de gerenciamento remotamente usando o PowerShell (consulte a tabela abaixo para obter exemplos de script):
  
- Obter dispositivos conectados
- Obter o status do aplicativo
- Obter informações do sistema
- Reiniciar o sistema
- Recuperar logs
- Transferir arquivos (requer salas do Microsoft Teams associadas a um domínio)
    
> [!NOTE]
> Essa funcionalidade está desativada por padrão. Você precisa habilitar o PowerShell remoto para seu ambiente no sistema de salas do Microsoft Teams para executar as operações abaixo. Consulte a documentação sobre **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** para obter informações sobre como habilitar o PowerShell remoto.
  
Por exemplo, você pode habilitar o PowerShell Remoto da seguinte maneira:
  
1. Entre como administrador em um dispositivo de salas do Microsoft Teams.
2. Abra um prompt de comando elevado do PowerShell.
3. Insira o seguinte comando: Enable-PSRemoting -force

Para executar uma operação de gerenciamento:
  
1. Entre em um computador com credenciais de conta que têm permissão para executar comandos do PowerShell em um dispositivo de salas do Microsoft Teams.
2. Abra um prompt de comando normal do PowerShell no computador.
3. Copie o texto do comando da tabela abaixo e cole-o no prompt.
4. Substituir `<Device fqdn>` os campos pelos valores de FQDN apropriados para o seu ambiente.
5. Substituir * \<caminho\> * com o nome do arquivo e o caminho local do arquivo de configuração Master SkypeSettings. XML (ou imagem do tema).
    
Para obter dispositivos conectados
  
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

Enviar um arquivo de configuração XML (ou um elemento gráfico) do tema
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Atualizações de software
<a name="SWupdate"> </a>

Por padrão, as salas do Microsoft Teams tentam se conectar à Windows Store para obter a versão mais recente do software de salas do Microsoft Teams, para que o dispositivo exija acesso regular à Internet. Antes de entrar em contato com a Microsoft com problemas de suporte, verifique se o dispositivo de salas do Microsoft Teams está carregado com a versão mais recente do aplicativo.
  
Por padrão, as salas do Microsoft Teams se conectam ao Windows Update para recuperar atualizações do sistema operacional e do firmware do dispositivo periférico USB e as instalam fora do horário comercial configurado. Para configurar o horário comercial, entre na conta de administrador e execute o aplicativo Configurações.
  
Se você quiser gerenciar as atualizações manualmente e não conseguir seguir o procedimento normal para a [Microsoft Store para empresas](https://businessstore.microsoft.com/store) [distribuir aplicativos offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), você pode adquirir o arquivo Appx e as dependências apropriados do [Kit de implantação](https://go.microsoft.com/fwlink/?linkid=851168) (nas instruções para [configurar um console de salas do Microsoft Teams](console.md)) que podem ser usados com o SCCM. A versão do kit de implantação está atrasada atrás do lançamento da loja, portanto, talvez nem sempre corresponda à versão mais recente disponível.
  
### <a name="to-update-using-powershell"></a>Para atualizar usando o PowerShell

1. Extraia o pacote do [MSI](https://go.microsoft.com/fwlink/?linkid=851168) de instalação para um compartilhamento que o dispositivo possa acessar.
2. Execute o script a seguir direcionando os dispositivos de sala do \<Microsoft\> Teams, alterando o compartilhamento para o compartilhamento de dispositivo conforme apropriado:
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Modo de administração e gerenciamento de dispositivo
<a name="AdminMode"> </a>

Algumas funções de gerenciamento, como instalar manualmente um certificado de autoridade de certificação privado, exigem colocar o dispositivo Surface pro no modo de administração. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Alternar para o modo de administrador e voltar quando o aplicativo salas do Microsoft Teams estiver em execução

1. Desligue as chamadas em andamento e retorne à tela inicial.
2. Selecione o ícone de engrenagem e exibir o menu (opções são **configurações**, **acessibilidade**e **reinicialização do dispositivo** ).
3. Selecione **Configurações**.
4. Digite a senha do administrador. A tela Configuração será exibida.  Se o dispositivo não for associado ao domínio, a conta administrativa local (nome de usuário "administrador") será usada por padrão. A senha padrão desta conta é ' SFB ', altere a senha o mais rápido possível. Se o computador for associado a um domínio, você poderá entrar com uma conta de domínio apropriadamente privilegiada. 
5. Selecione **configurações do Windows** na coluna à esquerda.
6. Escolha **Vá para Entrada como Admin**.
7. Digite a senha do administrador. Isso faz com que o aplicativo seja desativado e leva você até a tela de logon do Windows. 
8. Faça logon no desktop usando as credenciais administrativas. Você terá os privilégios necessários para gerenciar o dispositivo.
9. Execute as tarefas administrativas necessárias.
10. Saia da conta de Administrador.
11. Retorne a salas do Microsoft Teams selecionando o ícone de conta de usuário no lado esquerdo da tela e, em seguida, selecionando **Skype**.
    
    Se o usuário do **Skype** não estiver listado, talvez seja necessário selecionar **outro usuário** , digitar **.\skype** como o nome de usuário e entrar.
    
O console agora está novamente em seu modo de operação normal. O procedimento a seguir exige que você anexe um teclado ao dispositivo, caso ele ainda não esteja conectado. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Alternar para o modo de administrador e voltar quando o aplicativo salas do Microsoft Teams falha

1. Pressione a tecla do Windows cinco vezes em uma sucessão rápida. Isso levará você para a tela de logon do Windows. 
2. Faça logon no desktop usando as credenciais administrativas.
3. Execute as tarefas administrativas necessárias.
4. Reinicie o computador quando tiver terminado.

    > [!NOTE]
    > Esse método não registra o usuário do Skype ou encerra o aplicativo normalmente, mas você o usaria se o aplicativo não estivesse respondendo e o outro método não estivesse disponível. 

   O console é reiniciado em seu modo de operação normal, executando o aplicativo salas do Microsoft Teams. Você pode remover o teclado, se ele estiver associado, para permitir que você execute este procedimento.
   ## <a name="troubleshooting-tips"></a>Dicas para solução de problemas
   <a name="TS"> </a>

- Os convites de reunião podem não ser exibidos quando enviados entre os limites do domínio (por exemplo, entre duas empresas). Nesses casos, os administradores de ti devem decidir se desejam permitir que usuários externos agendem uma reunião.
- As salas do Microsoft Teams não dão suporte a redirecionamentos de descoberta automática do Exchange via Exchange 2010.
- Em geral, é uma boa prática para os administradores de ti desabilitarem pontos de extremidade de áudio que eles não pretendam usar.
- Caso seja exibida uma imagem espelhada na visualização da sala, o administrador de TI pode corrigir isso desligando e ligando a câmera ou invertendo a orientação da imagem com o controle remoto da câmera.
- Sabe-se que pode ocorrer a perda do acesso à tela touch do console. Nesses casos, o problema também é resolvido ao reiniciar o sistema de salas do Microsoft Teams.
- Sabe-se que pode ocorrer a perda do áudio local ao conectar um computador ao console via entrada com fio. Nesses casos, reiniciar o computador pode resolver o problema de reprodução do áudio local.
    
